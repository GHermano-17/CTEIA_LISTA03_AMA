# Avaliação Comparativa de Modelos de Classificação: MLP, SVM e Ensembles

Lista 3 da disciplina de Aprendizagem de Máquina — CTEIA/UFC.

Avaliação comparativa entre quatro modelos de classificação multiclasse sobre o dataset **Vehicle Silhouettes**, utilizando validação cruzada estratificada com 5 folds. Os hiperparâmetros foram otimizados via GridSearchCV e RandomizedSearchCV em notebook auxiliar.

---

## Dataset

**Vehicle Silhouettes** — OpenML ID: 54

| Propriedade | Valor |
|-------------|-------|
| Amostras | 846 |
| Features | 18 atributos numéricos (método HIPS) |
| Classes | 4 (Bus, Opel, Saab, Van) |
| Tarefa | Classificação multiclasse |

---

## Modelos Avaliados

| Modelo | Configuração principal |
|--------|----------------------|
| SVM (RBF) | C=150, gamma=auto |
| MLP | hidden=(100,50), relu, alpha=0.015 |
| Gradient Boosting | n_estimators=150, max_depth=2, lr=0.1 |
| Random Forest | n_estimators=150, max_depth=14 |

---

## Resultados (Validação Cruzada 5-Fold)

| Ranking | Modelo | Acurácia | F1-Score Macro |
|---------|--------|----------|----------------|
| 1º | SVM (RBF) | **85.35% ± 2.89%** | 85.33% ± 2.92% |
| 2º | MLP | 84.40% ± 3.07% | 84.45% ± 3.15% |
| 3º | Gradient Boosting | 78.14% ± 2.95% | 77.89% ± 3.10% |
| 4º | Random Forest | 76.48% ± 2.65% | 75.79% ± 2.88% |

O SVM com kernel RBF obteve o melhor desempenho geral. Os modelos ensemble baseados em árvores (Random Forest e Gradient Boosting) apresentaram overfitting mais acentuado e desempenho inferior neste dataset, sugerindo que a estrutura de silhuetas de veículos é mais adequada para modelos baseados em margens e redes neurais.

---

## Dependências
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## Notebooks

- **Principal:** `LISTA_03_FINAL_AMA.ipynb`
- **Busca de hiperparâmetros:** [GridSearch/RandomizedSearch](https://colab.research.google.com/drive/1HCjABaJvuRrceyLCwDN9uRVQqvO2rnmQ?usp=sharing)

---

## Autor

**Guilherme Hermano de Paula Ferreira**  
CTEIA — Universidade Federal do Ceará
