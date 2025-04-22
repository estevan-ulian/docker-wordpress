# Ambiente de Desenvolvimento WordPress com Docker

Este repositório contém um ambiente de desenvolvimento WordPress baseado em Docker com MySQL e phpMyAdmin.

## Estrutura do Projeto

```
.
├── docker-compose.yaml     # Configuração do Docker compose
└── src/                    # Diretório de conteúdo do WordPress equivalente ao /wp-content
    ├── plugins/            # Plugins do WordPress
    ├── themes/             # Temas do WordPress
    └── uploads/            # Uploads de mídia do WordPress
```

## Pré-requisitos

- Docker
- Docker Compose

## Variáveis de Ambiente

Crie um arquivo `.env` no diretório raiz com as seguintes variáveis:

```
CONTAINER_NAME=nome-do-seu-projeto
DATABASE_NAME=wordpress
DATABASE_USER=wordpress_user
DATABASE_PASSWORD=sua_senha
DATABASE_ROOT_PASSWORD=sua_senha_root
```

## Como Começar

1. Clone este repositório (ou copie os arquivos)
2. Crie o arquivo `.env` conforme descrito acima
3. Inicie os containers:
   ```bash
   docker compose up -d
   ```

## Serviços Disponíveis

- WordPress: http://localhost:8080
- phpMyAdmin: http://localhost:8001
- MySQL: localhost:3306

## Desenvolvimento

O diretório `src` é montado como a pasta `wp-content` no WordPress. Quaisquer alterações feitas em temas, plugins ou uploads serão mantidas entre as reinicializações dos containers.

## Parando o Ambiente

Para parar todos os containers:
```bash
docker compose down
```

Para parar e remover todos os dados (incluindo o banco de dados):
```bash
docker compose down -v
```