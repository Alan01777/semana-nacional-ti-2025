# Projeto Docker Nginx

Este projeto mostra como configurar um container Nginx com um arquivo de configuração e uma página inicial personalizados. Existem duas formas de fazer isso: usando o Docker pela linha de comando ou usando o Docker Compose.

---
## Cursos no Drive
[link](https://drive.google.com/drive/folders/13aRlsJax-3XXNjdz0f7MBQ4y76OBB1XB?usp=sharing)

## Pré-requisitos

- Instale o [Docker](https://docs.docker.com/get-docker/)
- (Opcional) Instale o [Docker Compose](https://docs.docker.com/compose/install/)

---

## Cenário 1: Usando o Docker pela Linha de Comando

1. **Criar e Executar o Container Nginx**  
   Use o comando abaixo para rodar o container Nginx com os arquivos personalizados:
   ```bash
   docker run -d \
     --name custom-nginx \
     -p 8079:80 \
     -v $(pwd)/Docker/index.html:/usr/share/nginx/html/index.html \
     -v $(pwd)/Docker/nginx.conf:/etc/nginx/nginx.conf \
     nginx:latest
   ```

2. **Acessar a Aplicação**  
   Abra o navegador e acesse `http://localhost:8079` para ver o servidor Nginx.

3. **Parar e Remover o Container**  
   Para parar e remover o container, use:
   ```bash
   docker stop custom-nginx
   docker rm custom-nginx
   ```

---

## Cenário 2: Usando o Docker Compose

1. **Preparar o Ambiente**  
   Certifique-se de que o arquivo `docker-compose.yaml` está na pasta `Docker`.

2. **Iniciar os Serviços**  
   Use o comando abaixo para iniciar o container Nginx:
   ```bash
   cd Docker
   docker compose up -d
   ```

3. **Acessar a Aplicação**  
   Abra o navegador e acesse `http://localhost:8079` para ver o servidor Nginx.

4. **Parar e Remover os Serviços**  
   Para parar e remover os serviços, use:
   ```bash
   docker compose down
   ```

---

## Estrutura de Arquivos

- `Docker/index.html`: Arquivo HTML personalizado para o servidor Nginx.
- `Docker/nginx.conf`: Arquivo de configuração personalizado do Nginx.
- `Docker/docker-compose.yaml`: Arquivo de configuração do Docker Compose.

---

## Observações

- Certifique-se de que os arquivos `index.html` e `nginx.conf` estão na pasta `Docker` junto com o arquivo `docker-compose.yaml`.
- Você pode modificar os arquivos `index.html` e `nginx.conf` para personalizar o servidor Nginx.
