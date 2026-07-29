# 🚀 n8n com Docker Compose

Este repositório contém uma configuração simples e pronta para uso do **[n8n](https://n8n.io/)** (uma poderosa ferramenta de automação de fluxos de trabalho) utilizando o Docker Compose.

## 📋 Pré-requisitos

Antes de começar, você precisará ter instalado em sua máquina:
* [Docker](https://docs.docker.com/get-docker/)
* [Docker Compose](https://docs.docker.com/compose/install/)

## ⚙️ Como executar

1. Clone este repositório para a sua máquina:

bash

    git clone [https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git](https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git)
    cd SEU-REPOSITORIO



3. Inicie o container em segundo plano (detached mode):
bash
  docker compose up -d



4. Acesse a interface web do n8n no seu navegador:
```
    http://localhost:5678
```
 

## 🛠️ Configurações do Arquivo

O arquivo `docker-compose.yml` está configurado com as seguintes características:

* **Persistência de Dados:** Utiliza um volume nomeado (`n8n_data`) mapeado para o diretório `/home/node/.n8n`. Isso garante que seus fluxos, credenciais e configurações não sejam perdidos quando o container for reiniciado ou recriado.
* **Fuso Horário:** Configurado para `America/Sao_Paulo`. Caso você esteja em outra região, basta alterar a variável `GENERIC_TIMEZONE` no arquivo.
* **Reinício Automático:** A diretiva `restart: always` garante que o n8n seja reiniciado automaticamente caso o servidor reinicie ou o container falhe.

## 🛑 Como parar o serviço

Para parar a execução do container sem perder seus dados, execute:

```bash
    docker compose down

```

Se quiser parar o container e **apagar completamente** o volume com todos os seus dados (use com cuidado!), execute:

```bash
    docker compose down -v

```

