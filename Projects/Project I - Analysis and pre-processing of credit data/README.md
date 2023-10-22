
# Análise e Pré-Processamento de Dados de Crédito
# Sumário
* [Descrição do projeto](#descrição-do-projeto)
* [Project description](#project-description)
* [Linguagens e tecnologias usadas](#linguagens-e-tecnologias-usadas)
* [Bibliotecas usadas](#bibliotecas-usadas)
* [Análise dos dados](#analise-dos-dados)
* [Visualização](#visualização)
* [Conclusão](#conclusão)

# Descrição do projeto
Este repositório apresenta um MVP (Minimum Viable Product) elaborado como avaliação para a Sprint I do curso de pós-Graduação em Ciência de Dados e Analytics da Pontifícia Universidade Católica do Rio de Janeiro (PUC-RIO).  

O projeto envolve a análise e pré-processamento dos relatórios de crédito do período de 2022, disponibilizados pelo Banco Central, com a finalidade de investigar sobre o perfil da indimplência no Brasil após a pandemia, considerando, principalmente, os ativos de crédito classificados pelo Banco Central como "problemáticos". 

Os ativos são considerados ativos problemáticos quando é constatado pelo menos um dos seguintes eventos:

  I - operações de crédito em atraso há mais de 90 (noventa) dias;
  
  II - a existência de indicativos de que a obrigação não será integralmente honrada sem que seja necessário recurso a garantias ou a colaterais (Para o BCB estes            indicativos ocorrem quando a operação é objeto de reestruturação e a instituição financeira reconhece contabilmente deterioração significativa da qualidade do           crédito   do   tomador, classificando-o entre os níveis de risco E e H).
  
Embora não utlizemos técnicas de machine learning nessa tarefa, a base de dados utilizada foi escolhida devido à sua adequação para o futuro desenvolvimento de um modelo preditivo do risco de eventual inadimplência, um provável desdobramento futuro deste projeto. 

A hipótese principal a qual iremos testar é de que, em 2022, houve uma ocorrência maior de ativos de crédito considerados problemáticos entre indivíduos de camadas economicamente mais pobres relacionada, sobretudo, a modalidade de crédito de habitação. Para tal, além de analisarmos o período de 2022, nos concentraremos nos dados do S1, que agrupa segmentos bancários mais robustos, e de Pessoa Física (PF). 

O desenvolvimento da análise e pré-processamento é construído de forma simples e clara, podendo ser facilmente compreendida por todos que possuírem algumas noções básicas da linguagem Python, sobretudo aqueles que já estejam familiarizados com a biblioteca Pandas. 

# Project Description
This repository presents a Minimum Viable Product (MVP) developed as an evaluation for the first sprint of the MBA in Data Science and Analytics at the Pontifical Catholic University of Rio de Janeiro (PUC-RIO). The project involves analyzing and preprocessing credit reports from the year 2022 that were made available by the Central Bank of Brazil to investigate the profile of delinquency in Brazil. The focus is mainly on credit assets classified by the Central Bank as "problematic". Assets are considered problematic when at least one of the following events occurs:

  I - credit operations that are overdue for more than 90 (ninety) days;
  
  II - the existence of indications that the obligation will not be fully honored without the need for guarantees or collaterals. 
  For the Central Bank, these indications occur when the operation is subject to restructuring, and the financial institution recognizes significant deterioration in     the credit quality of the borrower, classifying it between risk levels E and H.
  
Although we did not use machine learning techniques for this task, the database used was chosen because of its suitability for the future development of a predictive model of the risk of eventual default, which may be a probable future development of this project.

The main hypothesis we will test is that in 2022, there was a higher occurrence of credit assets considered problematic among individuals from economically poorer layers, mainly related to the housing credit modality. To do so, in addition to analyzing the 2022 period, we will focus on data from S1, which aggregates more robust banking segments, and from Individual Persons (PF).

The development of the analysis and preprocessing is presented in a simple and clear way, easily understandable by anyone who has some basic knowledge of the Python language, especially those who are already familiar with the Pandas library.

# Linguagens e tecnologias usadas
* Google Colaboratory
* Python 3.11

# Bibliotecas usadas
* Pandas
* Matplotlib
* Seaborn
* NumPy
* Opendatasets
* Os
* Missingno
* Gdown
* Zipfile

# Análise dos dados
* Primeiras linhas do dataset
Nas primeiras linhas, notamos algumas colunas com valores faltantes e outras que consideramos não possuírem valor direto para o objetivo de nossa análise. Nesse sentido, na etapa de pré-processamento, tratamos devidamente os valores faltantes e reduzimos a dimensionalidade do dataframe excluindo as colunas desnecessárias para o nosso projeto. 

<img src="primeiras-linas1.png">

<img src="primeiras_linhas2).png">

* Informações dos atributos do dataset
Aqui vemos que todos os atributos são do tipo 'object', indicando que possivelmente os dados foram armazenados como 'string'. Isso dificulta a realização de análises e operações matemáticas de dados das variáveis numéricas, como a realização de resumos estatíticos que nos permitam estabelecer informações importantes, como média, mediana e desvio parão. 

Portanto, também fizemos o devido tratamento desses dados convertendo as variáveis categóricas e numéricas de acordo com seus devidos tipos.
<img src="atributos.png">

# Visualização 
* Ativos problemáticos por Porte
Os ativos probemáticos aparecem com maior concentração na faixa de renda de Mais de 1 a 2 salários mínimos.

<img src="porte.png">

* Distribução dos Ativos problemáticos por Modalidade ao longo do tempo
O crédito habitacional aparece como a modalidade com maior peso nos ativos problemáticos durante todo o período analisado. 

<img src="tempo_modalidade.png">

* Outras vizualizações interessantes
<img src="estado.png">

<img src="ocupacao.png">

<img src="indexador.png">

# Conclusão
A análise do setor bancário e de crédito é frequentemente dificultada pela confidencialidade dos dados relevantes, o que muitas vezes leva à construção de modelos com amostras muito antigas ou com muitas variáveis desidentificadas. Optamos por analisar um conjunto de dados reais de operações de crédito criado pelo Banco Central do Brasil, pois acreditamos que o acesso a dados atualizados e bem documentados é valioso. Devido ao grande volume de dados, concentramos nossa análise no tipo de cliente Pessoa Física (PF) e no Segmento (SR) do tipo S1, que corresponde ao segmento bancário de maior porte. Essa abordagem foi suficiente para construir nossa análise e confirmar nossas hipóteses iniciais. Em resumo, confirmanmos nossa hipótese de que, com base nos dados do Banco Central, a maior parte dos ativos problemáticos em 2022 era composta por indivíduos com renda entre 1 e 2 salários mínimos, com a maior incidência na modalidade de crédito habitacional. Isso pode ser um efeito da pandemia e do aumento da inflação do período, que afetou o mercado imobiliário. Também observamos um padrão regional e sazonal nas ocorrências de ativos problemáticos, com os índices mais altos no último trimestre do ano, especialmente em dezembro. Além disso, os ativos problemáticos estão concentrados na Região Sudeste, principalmente nos Estados de São Paulo, Rio de Janeiro e Minas Gerais, que são considerados alguns dos mais ricos do país e também os mais populosos. 
