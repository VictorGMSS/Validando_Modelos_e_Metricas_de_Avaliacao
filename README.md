# 🚗 Validação de Modelos e Métricas de Avaliação: Identificação de Clientes Inadimplentes

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/VictorGMSS/Machine_Learning_clasificacao_validando_modelos_e_metricas_de_avaliacao/blob/main/metricas_de_avaliacao.ipynb)

Projeto prático desenvolvido durante o curso na **"Alura"**. O objetivo deste repositório é melhorar a identificação de clientes **inadimplentes** de uma empresa de empréstimo de automóveis, aplicando métodos de validação (**hold out** e **validação cruzada**), diferentes **métricas de avaliação** e técnicas de **balanceamento de dados** (oversampling e undersampling) dentro de um **pipeline** de validação.

---

## 🎯 Objetivos do Projeto

* **Validação de Modelos:** Comparar a avaliação nos próprios dados de treino com a divisão em treino, validação e teste (**hold out**) e com a **validação cruzada** (`KFold` e `StratifiedKFold`).
* **Métricas de Desempenho:** Avaliar o modelo com **matriz de confusão**, **acurácia**, **precisão**, **recall**, **F1-score**, **curva ROC (AUC)** e **curva de precisão x recall (AP)**.
* **Escolha da Métrica Adequada:** Identificar qual métrica é mais apropriada ao problema, priorizando o **recall** para detectar o máximo de inadimplentes.
* **Balanceamento de Dados:** Tratar o desbalanceamento das classes com **SMOTE** (oversampling) e **NearMiss** (undersampling).
* **Validação Correta:** Aplicar o balanceamento dentro de um **pipeline** (`imblearn`), evitando vazamento de dados na validação cruzada.
* **Teste Final:** Avaliar o modelo escolhido em dados de teste separados desde o início.

---

## 🗂️ Estrutura do Repositório

* `metricas_de_avaliacao.ipynb`: Notebook principal com todo o pipeline de modelagem, validação, métricas e balanceamento.
* `emp_automovel.csv`: Base de dados de clientes da empresa de empréstimo de automóveis, com a variável alvo `inadimplente`.

---

## 🛠️ Tecnologias e Bibliotecas Utilizadas

* **Python 3**
* **Pandas:** Carregamento e manipulação dos dados.
* **Scikit-Learn:** `DecisionTreeClassifier`, `train_test_split`, `cross_validate`, `KFold`, `StratifiedKFold` e as métricas `confusion_matrix`, `accuracy_score`, `precision_score`, `recall_score`, `f1_score`, `roc_auc_score`, `average_precision_score` e `classification_report`, além de `RocCurveDisplay`, `PrecisionRecallDisplay` e `ConfusionMatrixDisplay` para os gráficos.
* **Imbalanced-Learn:** `SMOTE` (oversampling), `NearMiss` (undersampling) e `Pipeline` (`imbpipeline`) para validar o balanceamento corretamente.

---

## 🚀 Etapas Desenvolvidas no Notebook

1. **Modelo Inicial:** Carregamento da base (`[PREENCHER]` registros) e treino de uma **Árvore de Decisão**, mostrando por que avaliar o modelo nos próprios dados de treino não é uma prática correta.
2. **Validação Hold Out:** Separação dos dados em treino, validação e teste (`15%` para teste, com estratificação) e comparação da acurácia de treino e de validação com `max_depth=10`.
3. **Métricas de Avaliação:** Análise da matriz de confusão e cálculo de acurácia, precisão, recall, F1-score, AUC e AP, além do relatório de classificação.
4. **Validação Cruzada:** Aplicação de `KFold` e `StratifiedKFold` (`5` folds), usando o **recall** como métrica e calculando um intervalo de confiança aproximado (média ± 2 desvios-padrão).
5. **Balanceamento com Oversampling:** Aplicação do **SMOTE** e comparação entre balancear os dados antes da validação cruzada e balancear dentro de um **pipeline**, que é a forma correta.
6. **Balanceamento com Undersampling:** Aplicação do **NearMiss** (versão 3) dentro do pipeline de validação, com recall em validação cruzada de `[PREENCHER]`.
7. **Teste Final:** Treino do modelo com os dados balanceados por undersampling e avaliação nos dados de teste, com relatório de classificação e matriz de confusão (recall no teste: `[PREENCHER]`).

---

## 💻 Como Executar

1. **Via Google Colab (Recomendado):** Clique no botão **"Open in Colab"** no topo deste README para abrir e executar o notebook diretamente no navegador sem precisar configurar ambiente local.
2. **Localmente:**
```bash
git clone https://github.com/VictorGMSS/Machine_Learning_clasificacao_validando_modelos_e_metricas_de_avaliacao.git
cd Machine_Learning_clasificacao_validando_modelos_e_metricas_de_avaliacao
pip install pandas scikit-learn imbalanced-learn jupyter
jupyter notebook metricas_de_avaliacao.ipynb
```

---

## 👨‍💻 Informações pessoais

Victor Gabriel Martins e Souza

* 💼 LinkedIn: [https://www.linkedin.com/in/victorgms](https://www.linkedin.com/in/victorgms)
* 🌐 Portfólio: [https://verxstech.vercel.app](https://verxstech.vercel.app)
