# Container Registry 

Vamos executar a construção da imagem e o registro no IBM Container Registry. 
<br>

## 🛠️ Instruções
<br>

> [!NOTE] 
>Este passo  precisa ser executado dentro da pasta específica onde se encontra o arquivo index.html e o Dockerfile. [Step2](Step2-indexHTML.md)

<br>  

### 1 - Login em ibmcloud
Pelo terminal execute o login em IBMCloud, através do ibmcloud login.
```bash
ibmcloud login
```
<br>

### 2 - Instale os pacotes necessários:
```bash
    ibmcloud plugin install container-registry
```
<br>

### 3 - Faça o login no Container Registry. 
```bash
ibmcloud cr login
```
### 4 - Crie um namespace no Container Registry
```bash
ibmcloud cr namespace-add MY_NAMESPACE
```
<br>

>Garanta que seu namespace foi criado: 
>```bash ibmcloud cr namespace-list -v ```

<br>

Exemplo de como usar esse comando: 
```bash
ibmcloud cr namespace-add ana     
```
<br>

### 5 - Execute o build da imagem. 
Vamos executar o build da imagem do nosso container com base no Dockerfile. 
```bash
docker build -t <nome-da-app> .      
```
<br>

Exemplo de como usar esse comando: 
```bash
docker build -t html-wxo .     
```
<br>

### 6 - Faça a tag da imagem docker criada.
```bash
docker tag <nome-da-app> br.icr.io/<namespace>/<nome-da-app>:tag       
```
<br>

Exemplo de como usar esse comando: 
```bash
docker tag html-wxo br.icr.io/ana/html-wxo:latest    
```
<br>

### 7 - Push da imagem
Faça o push da imagem docker taggeada para o Container Registry.

```bash
docker push br.icr.io/<namespace>/<nome-da-app>:tag       
```
<br>

Exemplo de como usar esse comando: 
```bash
 docker push br.icr.io/ana/html-wxo:latest 
```
<br><br>


> [!NOTE] 
>O Endereço **br.icr.io** é referente ao dominio do container registry para o Brasil, utilize a localização que melhor cabe ao seu ambiente. [Veja a documentação](#https://cloud.ibm.com/docs/Registry?topic=Registry-registry_overview#registry_regions_local)
<br>  

Siga para o [Step 4- Deploy com IBM Cloud Code Engine](Step4-CodeEngine.md)

