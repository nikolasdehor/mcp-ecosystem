# Copilot Instructions — mcp-ecosystem

## Project Overview
Repositório de configuração e orquestração de servidores MCP (Model Context Protocol), com Docker/Compose.

## Stack
- **Docker** + **docker-compose** para containers MCP
- Configs em **JSON** (mcp servers config)
- **YAML** para compose e workflows

## Conventions
- JSON válido sem trailing commas; chaves entre aspas
- Configs MCP com `mcpServers`, `command`, `args` bem formados
- Sem secrets em valores literais — env vars
- Dockerfiles: imagens base com tag pinned (sem `:latest`)
- docker-compose: versão fixa, volumes conscientes
- YAML: indentação 2 espaços, sem tabs

## Folder Structure
- `configs/` ou raiz — JSONs de configuração MCP
- `docker/` ou `Dockerfile*` — definições de container
- `docker-compose.yml` — orquestração

## Development
- `docker compose up -d` — sobe stack
- `docker compose logs -f <service>` — logs
- `docker compose down` — para

## Critical Files
- `docker-compose.yml` — orquestração principal
- `configs/*.json` — definições MCP
- `Dockerfile*` — imagens custom
