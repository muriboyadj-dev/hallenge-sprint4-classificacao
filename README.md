# Challenge Sprint 4 — Classificação linear de energia renovável

## Integrantes
* Gustavo Guedes Pereira — RM 569779
* Lucas Angelo — RM 569530
* Gustavo de Souza — RM 570746
* Arthur Tae — RM 570647
* Gabriel Rodrigues — RM 569322
* Murillo Boyadjian - RM 570774

## Vídeo
https://youtu.be/HtVT6HjjbCs

## Sobre o projeto
Classificação da variável `Energy_Class` (High, Low, Medium) com o dataset
[Renewable Energy Production Dataset (2010–2020)](https://www.kaggle.com/datasets/itsrohithere/renewable-energy-production-dataset-2010-2020/data),
usando **Regressão Logística** (modelo linear do scikit-learn) em dois cenários de divisão dos dados.

## Arquivos do repositório
| Arquivo | Conteúdo |
|---|---|
| `renewable_energy.csv` | Base de dados utilizada |
| `Challenge_Sprint4_Classificacao.ipynb` | Código em Python, textos e justificativas |
| `resultados/matriz_correlacao.png` | Matriz de correlação das features e da classe codificada |
| `resultados/matriz_confusao_cenario1_60_40.png` | Matriz de confusão do cenário 1 |
| `resultados/matriz_confusao_cenario2_85_15.png` | Matriz de confusão do cenário 2 |
| `resultados/metricas_cenarios.csv` | Acurácia, precisão e recall dos dois cenários |

## Resumo da solução
1. **Dataset:** carregado com pandas; `Energy_Class` codificada com `LabelEncoder`; matriz de correlação construída.
2. **Features:** nenhuma feature tem correlação forte com a classe (a maior é `Efficiency_Ratio`, −0,17) e não há redundância entre elas; foram usadas **todas as 7 features**.
3. **Modelo:** Regressão Logística com padronização (`StandardScaler`), `random_state=42` e divisão estratificada.
4. **Cenários:** 60% treino / 40% teste e 85% treino / 15% teste, com as demais condições iguais.

## Resultados
| Cenário | Acurácia | Precisão (ponderada) | Recall (ponderado) |
|---|---|---|---|
| 1 — 60/40 | 0,75 | 0,75 | 0,75 |
| 2 — 85/15 | 0,80 | 0,80 | 0,80 |

O cenário 2 teve métricas um pouco melhores. Nos dois, a classe High é bem identificada e a classe Medium é a mais confundida.
A análise completa está no notebook.

## Como executar
1. Instale as bibliotecas: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`.
2. Deixe `renewable_energy.csv` na mesma pasta do notebook.
3. Abra `Challenge_Sprint4_Classificacao.ipynb` no Jupyter ou no Google Colab e execute todas as células.
