# 📊 Projeto: Classificação de Risco de Crédito com Machine Learning

**Autor:** Fernando Garcia Rollo Ferreira  
**Curso:** Machine Learning — Trabalho Final  
**Objetivo:** Construir um modelo supervisionado para prever se um cliente é bom ou mau pagador, simulando um cenário real de análise de risco bancário.

---

## 🧠 Problema Atacado

Instituições financeiras precisam identificar o risco de crédito de novos clientes antes de aprovar financiamentos.  
Este projeto utiliza Machine Learning para prever se um cliente será:

- **1 = Bom pagador**
- **2 = Mau pagador**

A análise correta evita perdas financeiras e contribui para uma concessão de crédito mais segura e eficiente.

---

## 📂 Base de Dados

- **Dataset:** German Credit Data  
- **Fonte:** UCI Machine Learning Repository  
- **Instâncias:** 1000  
- **Atributos:** 20 preditores (numéricos e categóricos)  
- **Alvo:** `CreditRisk` (1 ou 2)

Escolhida por ser amplamente utilizada em estudos financeiros e representar bem o problema de crédito real.

---

## 🧪 Metodologia Aplicada

### 📁 Etapas do pipeline

1. **Carregamento dos dados**
2. **Análise Exploratória (EDA)**
   - Histograma de classes
   - Heatmap de correlação
   - Distribuição estatística das features
3. **Pré-processamento com `Pipeline` e `ColumnTransformer`**
   - Tratamento de dados ausentes
   - One-hot encoding
   - Normalização
   - Balanceamento com **SMOTE**
   - PCA para redução de dimensionalidade
4. **Treinamento dos modelos**
   - Random Forest
   - Support Vector Machine (SVM)
5. **Validação e Otimização**
   - GridSearchCV
   - Cross-Validation
6. **Avaliação**
   - Accuracy, Precision, Recall, F1
   - Curva ROC e AUC
7. **Produção**
   - Serialização (`joblib`)
   - API Flask
   - Exposição com Ngrok para teste

---

## 🏆 Resultados

| Modelo | ACC | Precision | Recall | F1 | AUC |
|-------|-----|-----------|--------|----|-----|
| RandomForest (tuned) | ~0.76 | ~0.64 | ~0.45 | ~0.52 | ~0.79 |
| SVM (tuned) | ~0.72 | ~0.53 | ~0.62 | ~0.57 | ~0.79 |

📌 O **SVM obteve melhor Recall** para a classe de risco (mau pagador), importante em crédito.  
📌 O **RandomForest apresentou maior acurácia geral**.

---

## 🧾 Exemplo de Resposta da API

```json
{
  "classe_predita": 1,
  "prob_mau_pagador": 0.417546
}

```
### 🚀 Deploy

Modelo salvo em joblib

API com Flask

Teste online via Ngrok

Este processo simula um ambiente real de disponibilização de modelo para consumo via API.

### ✅ Conclusão

Este projeto demonstrou um ciclo completo de Machine Learning aplicado ao risco de crédito, incluindo:

   - Análise exploratória

   - Engenharia de atributos

   - Balanceamento de classes com SMOTE

   - Redução de dimensionalidade (PCA)

   - Treinamento e tuning de algoritmos

   - Métricas robustas (AUC-ROC como foco)

   - Deploy via Flask + Ngrok


O pipeline desenvolvido representa um fluxo real utilizado em instituições financeiras e pode ser expandido para ambientes de produção com containers (Docker) e serviços em nuvem.
