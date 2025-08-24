# Dockerfile
FROM --platform=linux/amd64 node:22
# Instala um servidor HTTP leve
RUN npm install -g http-server

# Cria uma pasta de app
WORKDIR /app

# Copia os arquivos da sua aplicação
COPY . /app

# Expõe a porta 8080
EXPOSE 8080

# Comando para rodar o servidor
CMD ["http-server", "-p", "8080"]
