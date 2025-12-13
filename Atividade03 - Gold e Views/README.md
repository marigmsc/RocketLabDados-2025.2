# 🏆 Atividade 3: Camada Gold & Orquestração

## 📋 Descrição
Esta é a etapa final do pipeline. Aqui, os dados refinados da camada Silver são transformados em tabelas agregadas e métricas de negócio (Camada Gold), prontas para serem consumidas por ferramentas de BI (Power BI, Looker) ou Cientistas de Dados. Além disso, todo o fluxo (Bronze → Silver → Gold) foi orquestrado automatizadamente.

## 🛠 Tecnologias Utilizadas
*  **Spark SQL:** Consultas exploratórias e validações.
*  **PySpark (Spark SQL & DataFrames):** Para processamento distribuído de dados.
* **Databricks e Databricks Workflows (YAML):** Para orquestração e agendamento de tarefas.
* **Modelagem Dimensional:** Criação de visões de negócio focadas em Vendas e Performance.

## 🚀 O que foi desenvolvido

### 🥇 Camada Gold (Business Intelligence)
*Notebook: `Atividade3_Gold.ipynb`*
Algumas das view criadas:
1.  **Vendas Diárias (`dm_vendas_diaria`):** Agregação temporal para análise de tendência de receita.
2.  **Performance por Estado (`dm_vendas_uf`):** Ranking de estados (UF) com maior volume de vendas e valor monetário.
3.  **Top Vendedores (`dm_top_vendedores`):** Identificação dos parceiros com melhor performance.

### ⚙️ Orquestração (Pipeline as Code)
*Arquivo: `pipeline.yaml`*
Implementação de um **Databricks Workflow** que gerencia a dependência entre as tarefas:
1.  `tarefa_bronze`: Ingestão bruta.
2.  `tarefa_silver`: Limpeza e qualidade (depende da Bronze).
3.  `tarefa_gold`: Agregações finais (depende da Silver).
