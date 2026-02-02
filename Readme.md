# 📊 Segmentação de Clientes com Análise RFM (Python)

## 📌 Visão Geral

Este projeto aplica a **análise RFM (Recency, Frequency, Monetary)** para segmentar clientes com base em seu comportamento de compra.  
O objetivo é demonstrar como dados transacionais podem ser transformados em **insights acionáveis de negócio** utilizando Python.

A análise foi realizada com o **dataset Online Retail II**, disponibilizado pelo **UCI Machine Learning Repository**, amplamente utilizado em estudos de segmentação de clientes no varejo.

---

## 🎯 Objetivos do Projeto

- Realizar limpeza e preparação de dados transacionais  
- Calcular as métricas **Recência, Frequência e Monetário** por cliente  
- Criar scores RFM utilizando quantis  
- Segmentar clientes com base em **regras de negócio interpretáveis**  
- Gerar insights e recomendações para ações de CRM e marketing  

---

## 🗂 Dataset

- **Fonte:** Online Retail II – UCI Machine Learning Repository  
- **Descrição:** Transações de um e-commerce sediado no Reino Unido  
- **Principais colunas utilizadas:**
  - Invoice  
  - InvoiceDate  
  - Customer ID  
  - Quantity  
  - Price  
  - Country  

---

## 🛠 Tecnologias Utilizadas

- **Python**
- **pandas** – manipulação e agregação de dados  
- **matplotlib** – visualizações simples  
- **Jupyter Notebook / VS Code** – ambiente de desenvolvimento  

---

## 🔄 Etapas do Projeto

### 1. Limpeza dos Dados

- Remoção de transações canceladas  
- Remoção de registros sem identificação de cliente  
- Conversão de colunas de data para o formato datetime  
- Criação da variável de valor total por transação (`TotalPrice`)  

---

### 2. Cálculo das Métricas RFM

Para cada cliente foram calculadas as seguintes métricas:

- **Recency (Recência):** número de dias desde a última compra  
- **Frequency (Frequência):** número de compras realizadas  
- **Monetary (Monetário):** valor total gasto  

A data de referência (*lastpurchase_date*) foi definida como a última transação do dataset.

---

### 3. Criação dos Scores RFM

Os scores foram definidos a partir de quantis da distribuição dos dados:

- **R_score:** 4 grupos (quanto mais recente, maior o score)  
- **F_score:** grupos ajustados à distribuição real da frequência  
- **M_score:** 4 grupos (quanto maior o gasto, maior o score)  

Optou-se por **não forçar distribuições artificiais**, respeitando o comportamento real dos clientes.

---

### 4. Segmentação de Clientes

Os clientes foram classificados em segmentos com base em **regras de negócio**, resultando nos seguintes grupos:

- **Champions**  
- **Loyal Customers**  
- **New Customers**  
- **At Risk**  
- **Others**  

As regras foram ajustadas de forma iterativa para evitar a super-representação de segmentos de alto valor e garantir uma segmentação realista.

---

## 📈 Principais Insights

- Os segmentos **Champions** e **Loyal Customers** concentram a maior parte da receita, apesar de representarem uma parcela menor da base de clientes  
- O segmento **At Risk** representa uma oportunidade relevante para campanhas de reativação  
- **New Customers** apresentam baixo histórico de compras, mas alto potencial de crescimento  

---

## 💡 Recomendações de Negócio

- **Champions:** programas VIP, benefícios exclusivos e acesso antecipado a produtos  
- **Loyal Customers:** estratégias de cross-sell e aumento de ticket médio  
- **At Risk:** campanhas de win-back e incentivos direcionados  
- **New Customers:** ações de onboarding e estímulo à segunda compra  
- **Others:** comunicação genérica e monitoramento  

---

## 📁 Estrutura do Repositório

│rfm-analysis/

│├── data/ # Dados brutos ou tratados

├── notebooks/

│└── rfm_analysis.ipynb

├── README.md
