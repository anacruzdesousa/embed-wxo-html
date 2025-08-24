### Step 4 - Deploy com IBM Cloud Code Engine
<br>

## 🛠️ Instruções


<br>

> Neste tutorial vamos fazer o deploy do ambiente na região de São Paulo.
> Você pode escolher a região que faça mais sentido para você. 
<br>

### 1 - Selecione o Grupo de Recursos em IBM Cloud
Deve-se selecionar o grupo de recursos de IBM Cloud aonde se encontra sua instancia de Code Engine
```bash
ibmcloud target -g RESOURCE_GROUP_NAME'.
```

Exemplo de como usar esse comando:
```bash
ibmcloud target -g Default
```

### 1 - Criar um projeto no Code Engine

Crie um projeto onde sua aplicação será executada:
```bash
ibmcloud ce project create --name meu-projeto --region br-sao
ibmcloud ce project select --name meu-projeto
```
<br>

Exemplo de como usar esse comando:
```bash
ibmcloud ce project create --name projetohtml --region br-sao
ibmcloud ce project select --name projetohtml
```
<br>

### 2 - Crie um Secret com as credenciais do Container Registry
Você precisa criar um Image Pull Secret no Code Engine com as credenciais para acessar o ICR:
```bash
ibmcloud ce registry create \
  --name <Nome da Chave> \
  --server br.icr.io \
  --username iamapikey \
  --password <YOUR_API_KEY>

```
Exemplo de como usar esse comando:
```bash
ibmcloud ce registry create \
  --name chave-da-ana \
  --server br.icr.io \
  --username iamapikey \
  --password w0f9h2b6-7c91f-91a7-8f2e0a1b2c3d

```

<br>

### 3 - Fazer deploy da aplicação

Vamos fazer o deploy da imagem que subimos no IBM Cloud Container Registry: 
>Se necessário veja o [Step3](Step3-ContainerRegistry.md)

```bash
ibmcloud ce app create \
  --name <nome-da-app> \
  --image br.icr.io/<namespace>/<nome-da-app>:tag \
  --cpu 0.5 \
  --memory 1G \
  --max-scale 1 \
  --min-scale 1 \
  --port 8080 \
  --registry-secret <Sua Chave criada>
```
Exemplo de como usar esse comando:
```bash
ibmcloud ce app create \
  --name wxoembeded \
  --image br.icr.io/ana/html-wxo:latest \
  --cpu 0.5 \
  --memory 1G \
  --max-scale 1 \
  --min-scale 1 \
  --port 8080 \
  --registry-secret chave-da-ana
```
<br>

> [!NOTE]
>No IBM Cloud Code Engine, o parâmetro --min-scale define o número mínimo de instâncias (réplicas) da sua aplicação que ficarão sempre em execução, mesmo que não haja requisições.
> 
> 🔎 Em resumo:
> 
>> --min-scale 0 → Escala para zero quando não há tráfego.
>>
>> Você não paga por CPU/memória quando não está em uso.
>>
>> Mas a primeira requisição depois de inatividade pode demorar mais (cold start).
>> 
>> --min-scale 1 (ou maior) → Garante que sempre exista pelo menos uma instância rodando.
>> 
>> A aplicação responde mais rápido (sem cold start).
>>
>> Você terá custo contínuo, mesmo sem tráfego.

### 4. Acessar a aplicação
Você receberá um endpoint se o comando anterior for executado corretamente. 

Pode copiar e colar em um navegador e vai poder acessar a sua página web com o watsonx Orchestrate embedado.
<img width="2060" height="982" alt="image" src="https://github.com/user-attachments/assets/7d3f051a-35a0-4e5d-baab-89bcc688fa23" />




[Step 5- Acesse sua aplicação](Step5-AcesseApp.md)
