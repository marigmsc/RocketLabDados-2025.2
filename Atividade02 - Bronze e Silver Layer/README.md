# 🏗️ Atividade 2: Pipeline ETL em Arquitetura Medalhão (Bronze & Silver)

## 📋 Descrição
Nesta etapa, foi construído um pipeline de dados utilizando a arquitetura **Medallion (Bronze/Silver)** com **Databricks/PySpark**. O objetivo foi ingerir dados brutos de e-commerce, enriquecê-los com **dados externos (API de Cotação)** e aplicar regras de qualidade e negócio para refinar a base.

## 🛠 Tecnologias Utilizadas
*  **PySpark (Spark SQL & DataFrames):** Para processamento distribuído de dados.
* **Delta Lake:** Armazenamento otimizado com suporte a ACID e Schema Enforcement.
* **Python (Requests):** Consumo de API externa para enriquecimento de dados.
* **Spark SQL:** Consultas exploratórias e validações.
* **Databricks**

## 🚀 Fluxo de Dados

### 🥉 Camada Bronze 
*Notebook: `Atividade2_Bronze.ipynb`*
1.  **Ingestão de Arquivos:** Leitura de arquivos CSV do dataset Olist.
2.  **Enriquecimento Externo:** Criação de um script em Python para fazer uma requisição na API do **Banco Central**, buscar o histórico de cotação do Dólar e salvar como **tabela Delta.**
3.  **Padronização:** Adição de data de ingestão (`ingestion_timestamp`) e gravação no formato Delta.

### 🥈 Camada Silver 
*Notebook: `Atividade2_Silver.ipynb`*
1.  **Deduplicação:** Uso de `Window Functions` para garantir a unicidade dos registros baseada na **data de ingestão mais recente.**
2.  **Tratamento de Tipos:** Conversão de strings para **timestamps e inteiros.**
3.  **Regras de Negócio:**
    * Tradução de colunas (ex: Status do pedido).
    * Cálculo de novos KPIs (ex: `diferenca_entrega_dias` e flag `entrega_no_prazo`).
4.  **Qualidade de Dados (Data Quality):**
    * Validação de formatos (Regex para UUIDs).
    * Filtros de consistência temporal (datas de resposta não podem ser anteriores à pergunta).
    * **Integridade Referencial:** Verificação de "órfãos" entre Pedidos e Consumidores.
5.  **Enriquecimento Final:** Junção (Join) da tabela de pedidos com a tabela de Cotação do Dólar para criar a coluna `valor_total_pago_usd`.
