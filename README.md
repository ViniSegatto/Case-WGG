# Case WGG WGG Digital Solution

# Previsão de Metas de Vendas - Janeiro de 2024
Este projeto é baseado em um case de previsão, onde o objetivo é prever os percentuais de atingimento de metas de vendas para três países (Brasil, Peru, Colombia/Ecuador) no mês de janeiro de 2024.

A base de dados utilizada contém registros de valores percentuais de metas de vendas, organizados por país e mês, abrangendo o período de fevereiro de 2022 a dezembro de 2023. Esses valores representam a porcentagem do atingimento das metas estabelecidas para cada país em cada mês.

Utilizando técnicas de Machine Learning, incluindo Redes Neurais Recorrentes (RNN), Regressão Linear, Árvores de Decisão (DT), e Florestas Aleatórias (RF), este projeto visa identificar o modelo mais preciso para prever os valores de janeiro de 2024, com base nos dados históricos.

## Vamos começar entendendo melhor os dados! 

## Análise Temporal dos Percentuais de Metas de Vendas
O gráfico abaixo apresenta a evolução dos percentuais de atingimento das metas de vendas para três regiões: Colombia/Ecuador, Peru e Brasil, no período de fevereiro de 2022 a dezembro de 2023. Cada ponto azul representa o valor real observado para o respectivo mês, enquanto a linha laranja mostra a tendência estimada pela Regressão Linear para cada país.

* Colombia/Ecuador: Observa-se uma tendência de crescimento nos valores ao longo do tempo, com variações mais acentuadas no início e uma estabilização nos meses finais.
* Peru: Embora exista uma tendência de alta, os valores apresentam maior volatilidade, com variações significativas em determinados períodos.
* Brasil: A tendência de crescimento é clara, apesar de alguns picos e quedas ao longo do período analisado.
  
![download](https://github.com/user-attachments/assets/f397754a-ecc6-4cbd-a40a-6fd13f5a91a2)

O gráfico de sazonalidade analisa as médias mensais dos valores de atingimento de metas para os três países, destacando possíveis padrões sazonais. Por exemplo, o Brasil mostra um aumento consistente nos últimos meses do ano, enquanto Colômbia/Equador e Peru apresentam picos e vales em diferentes períodos, sugerindo variações sazonais que podem impactar o planejamento e as metas futuras.

![download](https://github.com/user-attachments/assets/d7c71a6c-2fdb-4e20-ad96-74dd84dba65a)

O gráfico de volatilidade compara o desvio padrão dos valores de atingimento de metas entre os países. O Peru apresenta a maior volatilidade, seguido por Colômbia/Equador e Brasil, indicando que os valores de Peru são mais suscetíveis a grandes variações ao longo do tempo, o que pode indicar desafios adicionais na previsão precisa dos valores futuros para este país. 

![image](https://github.com/user-attachments/assets/eb36866b-e51f-48a8-9636-af4981ef8f43)

Os gráficos de distribuição ilustram como os valores de metas de venda (Value) estão distribuídos para os países "Colombia/Ecuador", "Peru" e "Brasil", com linhas indicativas para a média, mediana e moda.

Colombia/Ecuador: A distribuição é levemente inclinada à direita, com a média ligeiramente maior que a mediana e a moda. A maioria dos valores está concentrada entre 0.60 e 0.70.
Peru: Apresenta uma leve inclinação à esquerda, com a média menor que a mediana e a moda, concentrando a maioria dos valores entre 0.65 e 0.70.
Brasil: A distribuição é quase simétrica, com a média, mediana, e moda praticamente sobrepostas, indicando uma estabilidade maior dos valores entre 0.65 e 0.70.

![image](https://github.com/user-attachments/assets/5cefde09-806c-4b71-9267-bce5b04b53ce)

A matriz de correlação explora as relações entre variáveis temporais e categóricas associadas aos países (Brasil, Peru e Colômbia/Ecuador) e o valor das metas de vendas (Value).

Os valores das metas de vendas mostram uma correlação moderada com o tempo, indicando possíveis mudanças ao longo dos anos.
Há indícios de variação sazonal, mas a correlação com meses e dias do ano é relativamente fraca.
O impacto dos países é variado, com o Brasil apresentando uma correlação ligeiramente positiva e a Colômbia/Ecuador uma correlação negativa.
![image](https://github.com/user-attachments/assets/df686b5f-8710-442e-8da7-d2d7c6544948)

## Para decidir qual modelo deve ser utilizado na produção com base nos RMSEs apresentados para os três países (Brasil, Peru e Colombia/Ecuador), vamos analisar e comparar o desempenho de cada modelo.

1. Modelo RNN
 * Brasil: RMSE = 0.2265
 * Peru: RMSE = 0.1915
 * Colombia/Ecuador: RMSE = 0.0757
   
O modelo RNN apresenta o maior RMSE entre os modelos, especialmente para o Brasil e Peru. Isso indica que este modelo é menos preciso e, portanto, menos adequado para ser implementado em produção.

2. Modelo de Regressão Linear
 * Brasil: RMSE = 0.0137
 * Peru: RMSE = 0.0897
 * Colombia/Ecuador: RMSE = 0.0342
   
A Regressão Linear apresenta o menor RMSE para o Brasil, o que sugere que é o modelo mais preciso para esse país. Para Peru e Colombia/Ecuador, os RMSEs também são baixos, especialmente em comparação com o RNN e Decision Tree. A Regressão Linear oferece um bom equilíbrio entre os países, com um excelente desempenho no Brasil.

3. Modelo Decision Tree
 * Brasil: RMSE = 0.0303
 *  Peru: RMSE = 0.1046
 * Colombia/Ecuador: RMSE = 0.0214
   
A Decision Tree apresenta um desempenho bom para Colombia/Ecuador, mas é menos precisa para o Brasil e Peru em comparação com a Regressão Linear. Embora seja competitiva, especialmente para Colombia/Ecuador, a Regressão Linear ainda supera a Decision Tree no geral.

4. Modelo Random Forest
 * Brasil: RMSE = 0.0333
 * Peru: RMSE = 0.1207
 * Colombia/Ecuador: RMSE = 0.0192
   
O Random Forest apresenta o menor RMSE para Colombia/Ecuador, indicando uma alta precisão para este país. No entanto, para o Brasil e Peru, o Random Forest é menos preciso em comparação com a Regressão Linear. Este modelo é excelente para Colombia/Ecuador, mas menos competitivo para os outros países.

## **Conclusão**:
Regressão Linear emerge como o modelo mais equilibrado e preciso entre os três países, especialmente destacando-se para o Brasil com o menor RMSE (0.0137). Random Forest é altamente preciso para Colombia/Ecuador, mas a Regressão Linear ainda apresenta um bom desempenho geral para todos os países, com o menor RMSE para o Brasil e resultados competitivos para os demais.

## **Decisão**:
O modelo de Regressão Linear é o mais indicado para ser utilizado em produção, pois oferece a melhor precisão geral para os três países, garantindo previsões mais consistentes e confiáveis em diferentes cenários.
