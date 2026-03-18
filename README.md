##  FarmTech Solutions – Análise de Rendimento de Safras

Este repositório contém o projeto desenvolvido para a **Fase 5** do curso, com o objetivo de analisar e modelar o rendimento de diferentes culturas agrícolas com base em variáveis climáticas.

### Contexto
Uma fazenda de médio porte produz quatro culturas: **Cacau, Óleo de Palma, Arroz e Borracha**. Foram coletados dados de **precipitação, temperatura, umidade específica, umidade relativa** e o respectivo **rendimento** (em toneladas/hectare). O desafio foi:

- Explorar os dados para entender padrões e relações;
- Aplicar **clusterização** para identificar tendências de produtividade e possíveis outliers;
- Desenvolver **cinco modelos preditivos** (regressão supervisionada) para estimar o rendimento das safras.

### Principais Descobertas
A **análise exploratória (EDA)** revelou que:
- A **cultura** é o fator dominante: **Óleo de Palma** (~175.000) tem produtividade muito superior às demais (**Arroz** ~32.000, **Cacau** e **Borracha** ~8.000–9.000).
- As **variáveis climáticas** são bastante homogêneas entre as culturas, com baixa variabilidade e correlações fracas com o rendimento.

### Clusterização (Não Supervisionado)
Utilizando **K-Means apenas com variáveis climáticas**, identificamos **6 clusters** com separação moderada (silhouette = 0,4457). Os clusters apresentaram **perfis de rendimento distintos**, sugerindo que, mesmo em condições climáticas similares, é possível agrupar observações com produtividades diferentes. O **DBSCAN** complementou a análise, detectando outliers que podem representar condições extremas ou erros de medição.

### Modelagem Preditiva (Supervisionado)
Foram treinados cinco modelos: **Regressão Linear, Árvore de Decisão, Random Forest, Gradient Boosting e SVR**.  
- **Com a variável cultura**, todos (exceto SVR) alcançaram **R² > 0,99** no teste, confirmando o poder preditivo da cultura.  
- **Apenas com variáveis climáticas**, os modelos tiveram desempenho **péssimo** (R² negativo ou próximo de zero).  
- **Clusters climáticos** também não agregaram poder preditivo, reforçando que a cultura é indispensável.

### Modelo Recomendado para Produção
A **Regressão Linear** foi escolhida como o melhor modelo por aliar:
- Alta performance (R² = 0,995, MAE ≈ 3132)
- Simplicidade e interpretabilidade (coeficientes claros)
- Baixo custo computacional para inferência

### Estrutura do Notebook
O notebook `PabloGonzalez_RM567944_fase5_cap1.ipynb` contém todo o desenvolvimento, organizado em seções com:
- Código Python comentado e otimizado
- Visualizações e tabelas
- Células markdown com a descrição dos achados e conclusões

### Vídeo de Demonstração
[https://youtu.be/kgZfllw3g1A](https://youtu.be/kgZfllw3g1A) – vídeo com a explicação breve do projeto.

---

**Nome:** Pablo Leon D Gonzalez
**RM:** 567944 
