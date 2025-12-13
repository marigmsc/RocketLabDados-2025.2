# RocketLabDados-2025.2  
Repositório Dedicado para Disponibilização das Atividades do **Programa Rocket Lab de Dados Visagio 2025.2**

## 🚀 Atividades de Dados – Fork, Download e Execução

Bem-vindo(a)! Este repositório reúne atividades práticas. Para utilizá-las, faça um fork deste repositório, baixe/clone os materiais a partir do seu fork e importe-os no Databricks para executar as tarefas no ambiente. Este projeto demonstra a construção de um **Data Lakehouse** completo, simulando um ambiente produtivo de alta escala. O foco é resolver problemas de negócio utilizando arquitetura medalhão, qualidade de dados e orquestração automatizada.

---
## 🧭 Estrutura do Repositório

O repositório terá, na estrutura, **uma pasta para cada atividade**, contendo todas as informações necessárias para sua realização (**notebook, datasets, etc.**).

```
/
├── README.md                              # Documentação Geral do Portfólio
│
├── Atividade1_Pyspark/                    # Módulo 1: Lógica e Window Functions
│   ├── dados/
│   │   ├── fut_players_data.csv
│   │   ├── metal_bands.csv
│   │   └── pokemon_data.csv
│   ├── Atividade1_Pyspark.ipynb
│   └── README.md                          # Documentação específica da Atividade 1
│
├── Atividade2_ETL_Bronze_Silver/          # Módulo 2: Pipeline ETL (Core)
│   ├── Atividade2_Bronze.ipynb            # Ingestão e API
│   ├── Atividade2_Silver.ipynb            # Limpeza e Qualidade
│   └── README.md                          # Documentação específica da Atividade 2
│
└── Atividade3_Gold_Orquestracao/          # Módulo 3: Analytics e Automação
    ├── Atividade3_Gold.ipynb              # Agregações para BI
    ├── pipeline.yaml                      # Workflow de Orquestração
    └── README.md                          # Documentação específica da Atividade 3
```
---
## 🛠 Tecnologias Utilizadas
* **Databricks** **e** **Databricks Workflow(YAML):** Para orquestração e agendamento de tarefas.
* **Python e PySpark (Spark SQL & DataFrames):** Para processamento distribuído de dados.
* **Window Functions:** Para criar rankings particionados.
* **Delta Lake:** Armazenamento otimizado com suporte a ACID e Schema Enforcement.
* **Python (Requests):** Consumo de API externa para enriquecimento de dados.

---
## 🧠 Competências e Habilidades Demonstradas

### 1. Processamento Distribuído (Big Data)
* **Uso de PySpark:** Implementação de soluções que não dependem da memória local (como Pandas), preparadas para escalar para Terabytes de dados.
* **Otimização:** Uso de operações vetoriais e lazy evaluation do Spark.
### 2. Arquitetura de Dados (Medallion Architecture)
* **Desenho de Camadas:** Implementação prática das camadas **Bronze** (Raw), **Silver** (Clean/Enriched) e Gold (Aggregated).
* **Delta Lake:** Uso do formato Delta para garantir transações ACID e evolução de schema.
* **Orquestração:** Pipeline automatizado definindo dependências de tarefas para garantir a ordem correta de execução.
* **Integração de APIs:** Uso da biblioteca Python requests para enriquecer dados internos com fontes externas (Banco Central).
### 3. Otimização & Big Data
* **Processamento Distribuído:** Códigos escritos nativamente em Spark para escalar horizontalmente.
* **Window Functions:** Substituição de loops ineficientes por funções de janela analítica para **rankings e deduplicações.**
*  **Data Cleaning:** Tratamento de tipos de dados e filtragem de ruídos.
*  **Data Quality:** Implementação de barreiras de qualidade (ex: validação de UUIDs, datas lógicas) que impedem dados "sujos" de chegarem à camada Silver.


