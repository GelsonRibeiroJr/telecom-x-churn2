# 📡 Telecom X — Predição de Churn (Parte 2)

Este repositório contém o desenvolvimento de um modelo preditivo de classificação para identificar antecipadamente clientes com alta probabilidade de evasão (Churn) na operadora Telecom X.

---

## 📌 Sumário
* [Objetivo do Projeto](#objetivo)
* [Etapas de Desenvolvimento](#etapas)
* [Análise de Correlação](#correlacao)
* [Performance do Modelo Final](#performance)
* [Principais Insights](#insights)
* [Estratégias de Retenção Sugeridas](#estrategias)
* [Como Executar](#executar)
* [Contato](#contato)
---

## 🎯 Objetivo do Projeto
A missão atual foi construir um pipeline robusto de Machine Learning para prever o cancelamento de serviços antes que ele ocorra, identificando variáveis críticas e apoiando a tomada de decisão estratégica para retenção de receita.

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Bibliotecas:** Pandas, Seaborn, Matplotlib, Scikit-learn
* **Ambiente:** Google Colab / Jupyter Notebook

## 🧠 Etapas de Desenvolvimento
O projeto seguiu as melhores práticas de Ciência de Dados:
1.  **Pré-processamento:** Limpeza e tratamento de categorias redundantes.
2.  **Feature Selection:** Remoção de multicolinearidade e teste estatístico **Qui-Quadrado**.
3.  **Engenharia de Dados:** Aplicação de One-Hot Encoding e Normalização via `StandardScaler`.
4.  **Modelagem:** Comparação entre **Random Forest** e **Regressão Logística**.
5.  **Otimização:** Aplicação de balanceamento de classes (`class_weight="balanced"`).

## 📉 Análise de Correlação
Identificamos a necessidade de remover variáveis como `ChargesDaily` e `ChargesTotal` devido à colinearidade perfeita com as cobranças mensais.

![Matriz de Correlação](Imagens/Matriz_Correlacao.png)

## 📊 Performance do Modelo Final
O modelo selecionado foi a **Regressão Logística Balanceada**, priorizando o **Recall (Sensibilidade)** para capturar o maior número possível de evasões.

* **Recall:** **79%** (identifica quase 8 em cada 10 clientes em churn).
* **Impacto:** Redução expressiva de Falsos Negativos (de 178 para 80).

| Modelo SEM Balanceamento | Modelo COM Balanceamento |
| :---: | :---: |
| ![Matriz Sem Balanceamento](Imagens/Matriz_Sem_Balanceamento.png) | ![Matriz](Imagens/Matriz_Com_Balanceamento.png) |

## 🔍 Principais Insights
A análise de coeficientes e boxplots revelou os maiores gatilhos de evasão:

* **⚠️ Fatores de Risco:** Contratos mensais, Fibra Óptica e faturas elevadas.
* **🛡️ Fatores de Retenção:** Contratos de longo prazo e tempo de permanência (*Tenure*).

![Importância das Variáveis](Imagens/Importancia_Variaveis.png)
![Distribuição de Tenure](Imagens/Boxplot_Tenure.png)

## 💡 Estratégias de Retenção Sugeridas
1.  **Migração Incentivada:** Converter contratos mensais para anuais.
2.  **Fidelização Precoce:** Focar no atendimento nos primeiros 6 meses de contrato.
3.  **Qualidade Técnica:** Investigar a satisfação específica dos usuários de Fibra Óptica.

### 📝 Conclusão e Visão Estratégica
Neste projeto, dei continuidade à etapa de tratamento e análise exploratória realizada na parte um. Nesta fase, avançamos para a modelagem preditiva com o objetivo de identificar clientes com maior risco de evasão, transformando análises descritivas em soluções preditivas orientadas à tomada de decisão.

Os resultados confirmam os insights identificados anteriormente: variáveis financeiras e contratuais são os principais fatores associados ao **Churn**. O tempo de permanência do cliente (**Tenure**), o tipo de contrato e o valor da fatura mensal destacam-se como as variáveis mais relevantes nos modelos que desenvolvi.

Entre as abordagens testadas, embora o *Random Forest* tenha sido avaliado, a **Regressão Logística com ajuste de pesos (Balanced)** apresentou o desempenho mais alinhado ao objetivo de negócio da Telecom X. Este modelo demonstrou maior capacidade de capturar os casos reais de evasão, atingindo um **Recall de 79%** e reduzindo drasticamente os falsos negativos. A análise dos coeficientes permitiu uma interpretação direta do impacto de cada variável, revelando que contratos de curto prazo e o serviço de fibra óptica são pontos críticos de atenção.

**Recomendações Estratégicas:**
* **Retenção Preventiva:** Intensificar o suporte nos primeiros meses de contrato, onde o risco de evasão é mais elevado.
* **Fidelização Contratual:** Incentivar a migração para contratos de longo prazo com benefícios progressivos.
* **Monitoramento Ativo:** Acompanhar de perto clientes com alto valor mensal e usuários de tecnologia de fibra óptica.
* **Eficiência Operacional:** Integrar este modelo preditivo ao processo de tomada de decisão da empresa para possibilitar ações preventivas em tempo real.

## 🚀 Como Executar
1. Clone o repositório.
2. Tenha as bibliotecas instaladas (`pandas`, `seaborn`, `sklearn`) e o arquivo `dados_tratados.csv`.
3. Execute o arquivo `TelecomX_Modelo_Preditivo.ipynb`.

----
## 📭 Contato
Desenvolvido por **Gelson Ribeiro Jr** [LinkedIn](https://www.linkedin.com/in/gelsonribeirojr/) | [GitHub](https://github.com/GelsonRibeiroJr/)
