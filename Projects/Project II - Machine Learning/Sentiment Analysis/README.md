
# Análise de Sentimentos com Processamento de Linguagem Natural (PLN)
# Sumário
* [Descrição do projeto](#descrição-do-projeto)
* [Project description](#project-description)
* [Linguagens e tecnologias usadas](#linguagens-e-tecnologias-usadas)
* [Bibliotecas usadas](#bibliotecas-usadas)
* [Análise dos dados e Pré-processamento](#análise-dos-dados-e-pré-processamento)
* [Limpeza e transformação dos dados](#limpeza-e-transformação-dos-dados)
* [Treinamento e avaliação do modelo](#treinamento-e-avaliação-do-modelo)


# Descrição do projeto
Este repositório apresenta um MVP (Minimum Viable Product) elaborado como avaliação para a Sprint II do curso de pós-Graduação em Ciência de Dados e Analytics da 
Pontifícia Universidade Católica do Rio de Janeiro (PUC-RIO).

O projeto envolve desenvolver um modelo de classificação de texto utilizando técnicas de Processamento de Linguagem Natural (PLN) para analisar o sentimento 
expresso em avaliações e comentários dos clientes. A ideia é determinar se o sentimento presente em cada texto é positivo ou negativo.

Nossa é de que, com base no conjunto de avaliações dos clientes, é possível criar um modelo capaz de aprender os padrões linguísticos e semânticos que 
distinguem sentimentos positivos de negativos. Utilizaremos técnicas de processamento de linguagem natural, como vetorização de palavras e redes neurais de Deep 
Learning, para extrair e aprender representações textuais significativas.

# Atributos do dataset
**rating:** Representa a classificação dada pelos clientes ao produto, sendo uma escala de 1 a 5 estrelas, onde 1 é a pior classificação e 5 é a melhor.

**gender:** Gênero do cliente (masculino ou feminino).

**variation:** Refere-se à variação específica do produto adquirido pelos clientes, como diferentes cores ou acabamentos.

**verified_reviews:** Contém as avaliações e comentários dos clientes sobre o produto.

**feedback:** É a coluna de saída ou alvo do modelo. Possui valores binários, onde 1 indica que o feedback foi positivo e 0 indica que o feedback foi negativo.

# Project Description
This repository presents an MVP (Minimum Viable Product) developed as an assessment for Sprint II of the Post-Graduation Course in Data Science and Analytics
at Pontifical Catholic University of Rio de Janeiro (PUC-RIO).

The project involves developing a text classification model using Natural Language Processing (NLP) techniques to analyze the sentiment expressed in customer 
reviews and comments. The goal is to determine whether the sentiment present in each text is positive or negative.

Our premise is that, based on the set of customer reviews, it is possible to create a model capable of learning the linguistic and semantic patterns that d
istinguish positive from negative sentiments. We will use natural language processing techniques, such as word vectorization and Deep Learning neural networks,
to extract and learn meaningful textual representations.

# Dataset Attributes
rating: Represents the rating given by customers to the product, on a scale from 1 to 5 stars, where 1 is the worst rating and 5 is the best.

**gender:** Gender of the customer (male or female).

**variation:** Refers to the specific variation of the product purchased by customers, such as different colors or finishes.

**verified_reviews:** Contains customer reviews and comments about the product.

**feedback:** It is the output or target column of the model. It has binary values, where 1 indicates a positive feedback and 0 indicates a negative feedback.

# Linguagens e tecnologias usadas
* Google Colaboratory
* Python 3.11

# Bibliotecas usadas
* Pandas
* Matplotlib
* Seaborn
* NumPy
* Matplotlib
* sklearn
* tensorflow

# Análise dos dados e Pré processamento

<figure>
  <img src="positives_feedbacks.png" alt="Feedbacks positivos">
</figure>

<figure>
  <img src="negatives_feedbacks.png" alt="Feedbacks negativos">
</figure>

<figure>
  <img src="gráfico.png" alt="Distribuição das avaliações negativas(0) e positivas(1)">
</figure>

Nesta análise exploratória do conjunto de dados, identificamos que todas as colunas estão preenchidas, não havendo valores ausentes, o que é positivo para a construção do modelo. As colunas "rating" e "feedback" são numéricas e representam a classificação dada pelos clientes e o feedback positivo ou negativo, respectivamente. As colunas "date", "variation" e "verified_reviews" contêm informações textuais relevantes para análise, como data da avaliação, variação específica do produto e as próprias avaliações verificadas dos clientes.

Observamos que a quantidade de feedbacks positivos é maior do que os feedbacks negativos, sugerindo um possível desequilíbrio de classes. Para simplificar o conjunto de dados e melhorar a eficiência do modelo, removemos colunas irrelevantes e aplicamos a transformação de variáveis dummies nas colunas restantes. Essas etapas de pré-processamento nos permitem construir um modelo de classificação de texto capaz de analisar os sentimentos expressos nas avaliações dos clientes e realizar previsões mais precisas.

# Limpeza e tranformação dos dados

<figure>
  <img src="tabela.png" alt="Primeiras linhas do dataframe após a limpeza e transformação dos dados">
</figure>

Nesta etapa de pré-processamento dos dados, foram tomadas várias medidas para preparar o conjunto de dados para a análise. Primeiro, as colunas "rating" e "date" foram removidas do DataFrame, pois não seriam utilizadas na análise. Em seguida, a coluna "variation" foi codificada utilizando one-hot encoding, convertendo as diferentes variações dos dispositivos em colunas binárias para que pudessem ser utilizadas no modelo de aprendizado. Além disso, foi aplicado o CountVectorizer na coluna "verified_reviews", convertendo as avaliações dos clientes em vetores de contagem de palavras, permitindo sua representação numérica. Por fim, os dataframes resultantes foram concatenados ao longo do eixo das colunas, combinando as informações de avaliações dos clientes com as informações codificadas. O conjunto de dados foi então dividido em conjuntos de treino e teste usando a função train_test_split(), possibilitando avaliar o desempenho do modelo em dados não vistos durante o treinamento. Essas etapas de pré-processamento são essenciais para garantir que os dados estejam em um formato adequado para o modelo de aprendizado de máquina e para obter resultados confiáveis e significativos na análise.
# Treinamento e avaliação do modelo

<figure>
  <img src="summary.png" alt="Summary do modelo sequencial da rede neural">
</figure>

<figure>
  <img src="hist.png" alt="Treinamento do modelo">
</figure

<figure>
  <img src= "matriz_treino.png" alt="Matriz de confusão da base de treino">
</figure>

<figure>
  <img src= "matriz_teste.png" alt="Matriz de confusão da base de teste">
</figure>

O modelo apresentou um bom desempenho tanto na base de treino quanto na base de teste. Na base de treino, teve um alto número de verdadeiros positivos e verdadeiros negativos, indicando que acertou a grande maioria das previsões. Entretanto, houve alguns falsos negativos e falsos positivos, sugerindo um possível overfitting, onde o modelo pode estar se ajustando muito bem aos dados de treino, mas não generalizando tão bem para dados novos.
