# Projeto_classificacao_de_credito

# 🏦 Classificação de Risco de Crédito Financeiro

## Objetivo Central

Desenvolver um modelo preditivo robusto para a classificação do **score de crédito** de clientes (Ruim, Normal ou Bom), com foco estratégico e crítico na identificação da classe **Alto Risco (Score Ruim)**.

O principal objetivo de negócio é **maximizar o Recall (Revocação) da classe minoritária "Risco Ruim" (Classe 0)**. Ao fazer isso, minimizamos as perdas financeiras decorrentes da concessão de crédito a clientes inadimplentes, priorizando a segurança da instituição financeira.

## 🛠️ Tecnologias e Bibliotecas

| Categoria | Pacote | Descrição |
| :--- | :--- | :--- |
| **Processamento/Análise** | `pandas`, `numpy` | Manipulação e análise de dados. |
| **Modelagem** | `sklearn.ensemble`, `sklearn.neighbors` | Implementação dos modelos Random Forest e K-NN. |
| **Pré-processamento** | `sklearn.preprocessing`, `sklearn.model_selection` | Codificação de variáveis e divisão de dados. |
| **Desbalanceamento** | `imblearn.over_sampling` (`SMOTE`) | Tratamento de classes desbalanceadas. |
| **Otimização** | `sklearn.model_selection` (`GridSearchCV`) | Ajuste fino e otimização de hiperparâmetros. |
| **Avaliação** | `sklearn.metrics` | Geração de métricas de desempenho e relatórios. |

## 🚀 Estratégia de Modelagem

1.  **Pré-processamento:**
    * Agregação de dados para manter a última observação por cliente.
    * Codificação de variáveis categóricas ordinais (Mapeamento Explícito) e nominais (One-Hot Encoding).
2.  **Modelos Baseline:** Treinamento inicial com **Random Forest** e **K-Nearest Neighbors**.
3.  **Tratamento de Desbalanceamento:** Aplicação da técnica **SMOTE** no conjunto de treinamento para criar instâncias sintéticas da classe "Risco Ruim" e melhorar sua representatividade.
4.  **Otimização:** Uso de **GridSearchCV** para encontrar os melhores hiperparâmetros do Random Forest, utilizando o **Recall Ponderado** como métrica de pontuação para guiar a otimização.

## 📈 Principais Resultados

O modelo **Random Forest Otimizado (após SMOTE)** demonstrou o melhor desempenho alinhado ao objetivo de negócio.

| Métrica de Desempenho | Antes da Otimização (Baseline) | Resultado Final (Random Forest Otimizado) |
| :--- | :--- | :--- |
| **Recall da Classe "Risco Ruim" (Classe 0)** | $\approx 57\%$ | $\approx 68\%$ |
| **Ganho Estratégico** | - | **+11 Pontos Percentuais** |

O aumento de 11 pontos percentuais no Recall da classe mais crítica indica uma **melhoria significativa na capacidade do modelo de identificar clientes que, de fato, se tornarão inadimplentes**. O pequeno *trade-off* na Precisão é justificado pelo alto custo de um Falso Negativo no contexto de crédito.
