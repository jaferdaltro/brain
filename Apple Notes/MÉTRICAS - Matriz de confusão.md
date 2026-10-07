---
apple-notes-id: 679E393C-F7D3-4BF6-B035-AA9F9E8D15EC
---
#topicos_avancados 

*Ao construir um classificador usando machine learning, um desenvolvedor deve se perguntar o quão bom é seu modelo para predição. Assim, ao treinar um modelo de aprendizagem algumas métricas podem ser utilizadas para avaliação. A métrica utilizada para determinação do “melhor modelo” depende do problema analisado. Neste artigo, veremos as principais métricas para avaliação de modelos de classificação de dados, como acurácia, sensibilidade (recall ou revocação), especificidade, precisão e F-score (Tabela 1).*
  

| **Método** | **Fórmula** |
| -- | -- |
| Sensibilidade | VP / (VP+FN) |
| Especificidade | VN / (FP+VN) |
| Acurácia | (VP+VN) / N |
| Precisão | VP / (VP+FP) |
| F-score | 2 x (PxS) / (P+S) |


   
*Tabela 1. Visão geral das métricas usadas para avaliar métodos de classificação. VP: verdadeiros positivos; FN: falsos negativos; FP: falsos positivos; VN: verdadeiros negativos; P: precisão; S: sensibilidade; N: total de elementos. Fonte: adaptado de Mariano (2019) \[1\]*