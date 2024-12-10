# **Pipeline-Study**

O seguinte arquivo trata sobre um estudo a respeito das funções de Pipeline e ColumnTransformer, a inspiração e fonte de estudo foi baseada no código feito pelo usuário [KEVIN SMITH 94624 do Kaggle](https://www.kaggle.com/code/kevinsmith94624/time-series-forecasting) 

## **Table of Contents**
1. [Data](#data)
2. [Tabela de Dúvidas](#duvidas)
3. [Fim](#fim)



---

## **Data**

Os dados foram retirados da competição do Kaggle [Store Sales - Time Series Forecasting](https://www.kaggle.com/competitionsstore-sales-time-series-forecasting/data?select=train.csv)

E a o código utilizado foi o do usuário [KEVIN SMITH 94624 do Kaggle](https://www.kaggle.com/code/kevinsmith94624/time-series-forecasting) 

---

## **Duvidas**

* **SimpleImputer**, é um método em que quando chamado ele calcula a estratégia escolhida (se escolher média, ele calcula a média da coluna), daí caso haja valores NULL na coluna ele irá substituir aqueles valores pela média (caso você escolha média como estratégia). Algumas estratégias são:
    * Média (mean)
    * Mediana (median)
    * Constante especificada (constant)
    * Valor Mais frequente (most_frequent)

* **StandardScaler**, biblioteca que padroniza os dados numéricos, garantindo que todas estejam na mesma escala antes de alimentar o modelo. Padroniza os dados para que tenham, média = 0 e desvio padrão = 1

* **OneHotEncoder**, biblioteca utilizada para converter dados categóricos em dados numéricos, chamados de variáveis dummy. Criando colunas separadas para cada categoria e preenchendo elas com valores binários 0 ou 1.
    * O **handle_unknown = 'ignore'** ignora valores que possam aparecer nos dados de teste que não estavam nos dados de treinamento, assim evitando que gere erros. 


* **ColumnTransformer**, é a biblioteca responsável por aplicar as tranformações necessárias às colunas que estamos tratando. De acordo com o scikit learn:
    ```python
    ColumnTransformer(transformers = [
        List of Tuples
        ('name', transformers, columns)
    ])
    ```

* **preprocessor**, aqui a gente só está definindo que quando chamarmos o model_pipeline ele passará os dados pelo preprocessor que definimos anteriormente.

* **xgb.XGBRegressor**, modelo de regressão baseado em árvores de decisão com boosting, que combina várias árvores de decisão para criar um modelo forte. O XGBRegressor mais especificamente é ótimo para lidar com problemas de regressão, para prever valores contínuos.

* **model_pipeline.fit(X_train, y_train)**, usa o X_train e y_train para alimentar nosso pipeline, primeiro passando os valores pelo tratamento do preprocessor, e depois usando o resultado para alimentar o modelo XGBRegressor.

---

## **Fim**

Obrigado por chegar até aqui, esse é apenas um estudo feito por mim para melhorar as minhas habilidades lidando com dados, e principalmente na preparação dos dados.
