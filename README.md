


# Bootcamp DBT + Airbyte

Este projeto demonstra uma arquitetura moderna de dados integrando múltiplas fontes (GA4, Facebook, Planilhas Google) utilizando ferramentas open source para ingestão, transformação e orquestração de dados.

## Arquitetura

- **Airbyte:** Responsável pela ingestão dos dados de diferentes fontes e carregamento no banco de dados Postgres.
- **Postgres:** Banco de dados relacional utilizado como data warehouse intermediário.
- **DBT Core:** Ferramenta de transformação de dados (ELT), responsável por modelar, limpar e preparar os dados para análise.
- **Airflow:** Orquestrador de workflows, automatizando o pipeline de ponta a ponta.

![Arquitetura](https://github.com/lvgalvao/bootcamp-aberto-aovivo/blob/main/pics/foto.png?raw=true)

## Como executar o projeto

1. **Clone o repositório**
   ```bash
   cd bootcamp_dbt_airbyte
   ```

2. **Configure as variáveis de ambiente**
   - Crie um arquivo `.env` com as credenciais necessárias para Postgres, Airbyte, e APIs das fontes de dados.

3. **Suba os serviços com Docker Compose**
   ```bash
   docker-compose up -d
   ```

4. **Acesse as interfaces**
   - Airbyte: http://localhost:8000
   - Airflow: http://localhost:8080
   - DBT: via CLI ou dbt Cloud
   - Postgres: via pgAdmin ou outro cliente

5. **Configure as conexões no Airbyte**
   - Adicione as fontes (GA4, Facebook, Planilhas) e destino (Postgres).
   - Execute as sincronizações.

6. **Execute os modelos DBT**
   ```bash
   dbt run
   ```

7. **Orquestre o pipeline com Airflow**
   - Acesse o Airflow e acione o DAG correspondente ao pipeline de dados.

## Estrutura de Pastas

```
bootcamp_dbt_airbyte/
├── dbt/                # Projetos e modelos DBT
├── airbyte/            # Configurações do Airbyte
├── airflow/            # DAGs e configs do Airflow
├── postgres/           # Scripts de inicialização do banco
├── docker-compose.yml  # Orquestração dos serviços
└── README.md           # Este arquivo
```

## Objetivo

Demonstrar, em poucos dias, como construir um pipeline de dados robusto, do zero, utilizando ferramentas modernas e práticas de engenharia de dados.

---

Projeto para fins educacionais e de portfólio feito de acordo com aula do Jornada de Dados (bootcamp DBT)
