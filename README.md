## Projeto Lakeflow - Engenharia de Dados com Databricks

### Etapa 1: Fundamentos e Governança (Unity Catalog)

Nesta etapa, foi estruturado a base de segurança do projeto utilizando o Unity Catalog. A governança de dados garante controle de acesso rigoroso e organização desde o primeiro momento.

A hierarquia criada foi:
- Catálogo (projeto_lakeflow): O ambiente principal e isolado de armazenamento do projeto.
- Schema (bronze): O banco de dados para a primeira camada da Arquitetura Medallion, onde os dados brutos são armazenados.
- Volume (dados_brutos): O local seguro e gerenciado para armazenar os arquivos originais não-tabulares (como CSVs ou JSONs) antes de qualquer processamento com o Apache Spark.

### Etapa 2: Tranformação Silver (Limpeza de duplicados e nulos)

Nesta etapa, os dados brutos da camada Bronze foram limpos e validados. 
Foi realizado a deduplicação e o tratamento de valores nulos, preparando a base para análises mais confiáveis.

### Etapa 3: Agregação Gold (Negócios)

Nesta camada final, os dados limpos foram transformados em resumos agregados e métricas focadas em responder a perguntas de negócio. Esta tabela resultante é otimizada para alimentar diretamente relatórios, dashboards e tomadores de decisão.
