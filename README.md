# Docker

# Mural de Mensagens XPTO

Esta imagem Docker configura uma aplicação simples de mural de mensagens usando o Nginx para servir uma página da web com um mural interativo. As mensagens são geradas dinamicamente a partir de um conjunto de dados predefinido.

## Execução

### Construir a Imagem Docker

```bash
docker build -t mural-mensagens-xpto .
```

### Executar o Container Docker

```bash
docker run -d -p 8080:80 --name container-mural-xpto mural-mensagens-xpto
```

Acesse a aplicação navegando até `http://localhost:8080` em seu navegador.

## Dockerfile

O Dockerfile utiliza a imagem oficial do Nginx e copia os arquivos de configuração e HTML necessários.

```Dockerfile
FROM nginx:latest
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./html /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

## HTML e CSS

O arquivo `index.html` contém a estrutura HTML e os estilos para o mural de mensagens. As mensagens são geradas dinamicamente usando JavaScript a partir do array `messagesData`.

## JavaScript

O código JavaScript gerencia a interatividade do mural de mensagens, incluindo a geração e resposta de mensagens.

## Dados das Mensagens

O array `messagesData` contém o conjunto inicial de mensagens que são exibidas no mural. Sinta-se à vontade para modificar ou expandir esse conjunto de dados.
