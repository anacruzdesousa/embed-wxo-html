### Step 2 -   Criar arquivo index.html
<br>

## 🛠️ Instruções

<br>

> [!NOTE] 
>Veja a pasta [html-wxo](html-wxo)
<br>

### 1-Faça o download dos arquivos da pasta html-wxo
Vamos editar os arquivos na pasta html-wxo localmente. 
Importante manter os dois arquivos em uma pasta separada de outros arquivos para fazermos o Build da aplicação. 


<br>


### 2-Edite o arquivo index.html 
Veja o arquivo exemplo: [index.html](html-wxo/index.html)

Com base no código retornado no passo anterior e adicione as credenciais no arquivo. 


>Fique atento a identação do arquivo.
<br>


>[!WARNING]
>Importante especificar as configurações de layout e style:

```html
layout: {
        form: "fullscreen-overlay", // ou 'float', 'custom'
        showOrchestrateHeader: true,
        width: "600px", // válido somente se form: 'float'
        height: "600px"
      },
      style: {
        headerColor: "#0052cc",
        userMessageBackgroundColor: "#e0f7fa",
        primaryColor: "#00695c"
      }
```

<br>

> [!NOTE] 
>Caso necessário volte ao [Step1 - ADK](docs/Step1-ADK.md)

<br><br>

### 2- Arquivo Dockerfile. 
Para fazermos o deploy do HTML em uma aplicação serveless no IBM Code Engine é necessario ter um arquivo Dockerfile. 

Veja o arquivo exemplo: [Dockerfile](html-wxo/Dockerfile)
> Neste momento o arquivo está pronto para ser utilizado, não precisa alterar nada, :smile:
<br>

### 3- Mantenha o seu arquivo index.html e Dockerfile na mesma pasta. 

Siga para o [Step 3- Container Registry](docs/Step3-ContainerRegistry.md)
---
