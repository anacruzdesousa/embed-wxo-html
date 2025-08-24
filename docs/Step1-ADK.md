
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
<img width="2672" height="1348" alt="image" src="https://github.com/user-attachments/assets/81b41947-081e-476a-8348-e569985f855b" />


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
<img width="1646" height="566" alt="image" src="https://github.com/user-attachments/assets/0650753c-74ba-4289-b170-e5fbd646804f" />

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

<img width="823" alt="Veja aqui como obter o código crn" src="https://github.com/user-attachments/assets/9c853244-a481-4247-9de9-b6bf69193025">

<br>
Exemplo de código crn:

```bash
crn:v1:bluemix:public:watsonx-orchestrate:us-south:a/587c8924a8c2e0ab:6e92c36c-b90d-4f9a-8a5b-27536c66acd0::
```
<br><br>

> [!IMPORTANT]
> Você receberá o script para ser usado no embed com as credenciais do seu ambiente watsonx Orchestrate:
<img width="2124" height="826" alt="image" src="https://github.com/user-attachments/assets/b322d9cd-f25b-4a42-9ccd-7617134792af" />



Siga para o [Step 2- Criar arquivo index.html](docs/Step2-indexHTML.md)
---

