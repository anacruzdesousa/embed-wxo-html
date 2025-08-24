
### Step1 - ADK
<br>

## 🛠️ Instruções
<br>

### 1-Conecte-se à sua conta IBM Cloud usando o comando:

```bash
orchestrate env add -n <environment-name> -u https://my-service-instance-url --type ibm_iam --activate
```
<br>

Exemplo de como usar esse comando: 

```bash
orchestrate env add -n ambientedaana -u https://api.us-south.watson-orchestrate.cloud.ibm.com/instances/6e92c36c-b89d-4f9a-8a5b-27536c66acd0 --type ibm_iam --activate
```
<br>
---

<br>

### 2-Ative o seu ambiente: 

```bash
orchestrate env activate <environment-name>
```
<br>
Exemplo de como usar esse comando: 

```bash
orchestrate env activate ambientedaana
```
<br><br>

>Você será solicitado a enviar a sua chave da ApiKey.

:warning: Como conseguir o endereço da instância? 
Na página inicial do serviço watsonx Orchestrate em IBM Cloud. 
<img width="1336" alt="image" src="https://github.ibm.com/anapaula-cruz/embed-wxo-html/assets/311491/2b94d459-af88-4d07-a019-182976a28b93">

<br>

---

<br>

### 3-Pegar as credenciais do Orchestrate para o embeded: 

<br>

3.1 - Listar os agentes 

```bash
orchestrate agents list
```

<br>
>Você verá uma lista assim: 
<img width="823" alt="image" src="https://github.ibm.com/anapaula-cruz/embed-wxo-html/assets/311491/11f31ef3-fa19-47e2-87ee-5c37a793414e">
<br>

:warning: Para utilizar o Watsonx Orchestrate embed é necessário fazer o deploy do seu agente.
<br>

3.2 - Pegar as credenciais do agente para realizar o embed.

```bash
orchestrate channels webchat embed --agent-name=<nome-do-agente>
```
<br>

Exemplo de como usar esse comando: 
```bash
orchestrate channels webchat embed --agent-name=agenteabc_5500DY
```
<br><br>
>Você será solicitado a enviar o *crn* da sua instância.

<img width="823" alt="Veja aqui como obter o código crn" src="https://github.ibm.com/anapaula-cruz/embed-wxo-html/assets/311491/c8da731a-51ce-4de5-ad7b-2cd54d0d07cb">
<br>
Exemplo de código crn:

```bash
crn:v1:bluemix:public:watsonx-orchestrate:us-south:a/587c8924a8c2e0ab:6e92c36c-b90d-4f9a-8a5b-27536c66acd0::
```
<br><br>

> [!IMPORTANT]
> Você receberá o script para ser usado no embed com as credenciais do seu ambiente watsonx Orchestrate:
<img width="1062" alt="image" src="https://github.ibm.com/anapaula-cruz/embed-wxo-html/assets/311491/4585635c-1f9d-4369-b2b4-ce9edbc47099">

Siga para o [Step 2- Criar arquivo index.html](docs/Step2-indexHTML.md)
---

