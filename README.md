# Rede Alimenta IA

Plataforma de conexão entre doadores de alimentos excedentes e ONGs, com análise de validade por IA, regras de segurança alimentar e DevSecOps.

## Visão geral

Este repositório foi inicializado para seguir a especificação do projeto, começando pela Fundação e pela Fase 0.

## Estrutura inicial

- `api/` — backend FastAPI
- `ml_service/` — serviço de IA em container separado
- `frontend/` — Streamlit multipágina
- `docs/` — documentação, STRIDE, premissas e plano
- `config/` — parâmetros de negócio
- `.github/workflows/` — CI

## Como executar

1. Crie o ambiente virtual:
   `python -m venv .venv`
2. Instale as dependências:
   `pip install -r requirements.txt`
3. Copie o ambiente local:
   `cp .env.example .env` (ou crie um `.env` com as variáveis necessárias)
   No ambiente local padrão, o projeto usa SQLite em desenvolvimento/testes; para Docker/Postgres, ajuste `DATABASE_URL` para o host `db` do compose.
4. Inicie a API:
   `uvicorn api.app.main:app --reload`
5. Inicie o serviço de IA:
   `uvicorn ml_service.app.api:app --reload --port 8001`
6. Inicie o Streamlit:
   `streamlit run frontend/app.py`

O projeto carrega automaticamente as variáveis do arquivo `.env` em desenvolvimento, preservando valores explícitos do ambiente do shell.

## Observações

- O projeto está em fase inicial do scaffold, conforme a especificação.
- O ambiente local usa PostgreSQL/PostGIS via Docker Compose.
- A autenticação e as regras de negócio de produção serão adicionadas nas fases posteriores.
