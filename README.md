# Instalar os pacotes

    npm install

Executar
    node server.js

Dockerfile
    FROM node
    WORKDIR /app
    COPY ./package*.json ./
    RUN npm install
    COPY . .
    EXPOSE 8080
    CMD ["node", "server.js"]

Criar a imagem
    docker build -t rfahham/conversao-temperatura:v1 .

Executar o container
    docker container run -d -p 8080:8080 rfahham/conversao-temperatura:v1

Subir para o DockerHub
    docker push rfahham/conversao-temperatura:v1