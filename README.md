# 📡 Telecom X — Predição de Churn (Parte 2)

Este repositório contém o desenvolvimento de um modelo preditivo de classificação para identificar antecipadamente clientes com alta probabilidade de evasão (Churn) na operadora Telecom X.

## 🎯 Objetivo do Projeto
Após o sucesso da análise exploratória inicial, a missão atual foi construir um pipeline robusto de Machine Learning para:
* **Prever o cancelamento** de serviços antes que ele ocorra.
* **Identificar variáveis críticas** que influenciam a decisão do cliente de deixar a empresa.
* **Apoiar a tomada de decisão estratégica** com métricas de desempenho precisas para retenção de receita.

## 🧠 Etapas de Desenvolvimento
O projeto seguiu as melhores práticas de Ciência de Dados:
1.  **Pré-processamento:** Limpeza de dados, tratamento de valores nulos e agrupamento de categorias redundantes.
2.  **Feature Selection:** Análise de correlação (removendo multicolinearidade entre cobranças) e teste estatístico **Qui-Quadrado** para ranking de relevância.
3.  **Engenharia de Dados:** Aplicação de One-Hot Encoding e Normalização via `StandardScaler`.
4.  **Modelagem:** Comparação entre **Random Forest** e **Regressão Logística**.
5.  **Otimização:** Aplicação de balanceamento de classes (`class_weight="balanced"`) para lidar com o desequilíbrio da base (aprox. 26% de Churn).

## 📊 Performance do Modelo Final
O modelo vencedor foi a **Regressão Logística Balanceada**, escolhida por sua capacidade superior de detecção do evento de interesse (Churn).

| Métrica | Resultado |
| :--- | :--- |
| **Recall (Sensibilidade)** | **79%** |
| **F1-Score (Classe Churn)** | **0.62** |
| **Acurácia Geral** | **74%** |

O uso do balanceamento permitiu reduzir drasticamente o número de clientes que cancelavam sem serem detectados (Falsos Negativos), caindo de **178 para apenas 80 ocorrências**.


## 🔍 Principais Insights (Importância das Variáveis)
A análise de coeficientes e análises direcionadas (Boxplots) revelou os maiores gatilhos de evasão:

* **⚠️ Fatores de Risco:** Contratos mensais (*Month-to-month*), serviço de Fibra Óptica e faturas mensais elevadas.
* **🛡️ Fatores de Retenção:** Contratos de longo prazo (1 ou 2 anos) e o tempo de permanência do cliente (*Tenure*). Clientes novos apresentam risco significativamente maior.


## 💡 Estratégias de Retenção Sugeridas
Com base nos resultados, propomos:
1.  **Migração de Planos:** Campanhas para converter clientes de contratos mensais para anuais.
2.  **Atenção à Fibra Óptica:** Auditoria de satisfação e qualidade técnica focada nos usuários de fibra.
3.  **Acompanhamento "Boas-Vindas":** Focar esforços de retenção nos primeiros 6 meses de contrato.

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Bibliotecas:** Pandas, Seaborn, Matplotlib, Scikit-learn
* **Ambiente:** Google Colab
* **Versionamento:** GitHub

---
### 🤝 Contato
Desenvolvido por **Gelson Ribeiro Junior** Analista de Dados
