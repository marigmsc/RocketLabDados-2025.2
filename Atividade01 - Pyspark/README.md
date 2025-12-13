# Atividade 1: Processamento de Dados FIFA com PySpark

## 📋 Descrição
Este notebook realiza a ingestão e transformação de um dataset de jogadores de futebol (`fut_players_data.csv`) utilizando **PySpark**. O objetivo principal é aplicar regras de negócio para selecionar os melhores jogadores e formar um "Dream Team" (Time dos Sonhos), classificando-os por **nacionalidade e posição.**

## 🛠 Tecnologias Utilizadas
* **Python**
* **PySpark (Spark SQL & DataFrames):** Para processamento distribuído de dados.
* **Window Functions:** Para criar rankings particionados.
* **Databricks**

## 🚀 O que foi desenvolvido
1.  **Configuração do Ambiente:** Inicialização da `SparkSession`.
2.  **Ingestão de Dados:** Leitura de arquivos CSV com inferência de schema.
3.  **Transformação e Lógica de Negócio:**
    * Uso de **Window Functions** para rankear jogadores baseados no atributo `overall` (nota geral).
    * Particionamento dos dados por `nationality` e `position_group`.
    * Filtragem para extrair apenas os **melhores colocados de cada grupo.**
4.  **Output:** Exibição do "Dream Team" processado (ex: Melhores jogadores do Brasil).