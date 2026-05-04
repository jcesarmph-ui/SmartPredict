Projeto: Manutenção Preditiva de Falhas Industriais com Machine Learning
1. Identificação do Grupo
Instituição: Faculdade Engenheiro Salvador Arena

Curso: Engenharia de Controle e Automação

Grupo: Grupo 1

Integrantes:

Júlio César Moreira Pereira - RA: 062210025
Lucas Silva de Alencar - RA: 062210011
Mykaella Soares Dutra - RA: 062210031
Sarah Vieira de Andrade - RA: 062210005
2. Área Problema Selecionada
O grupo seleciona a seguinte área:

 Manutenção Preditiva de Zero-Downtime
 Eficiência Energética e Descarbonização via Smart Grids
 Controle de Qualidade Autônomo com Visão Computacional
 Gêmeos Digitais (Digital Twins) e Analytics em Tempo Real
3. Diagnóstico e Definição do Problema
Esta seção apresenta a fundamentação do desafio.

Contexto: O projeto está inserido no cenário da Indústria 4.0, onde sensores monitoram máquinas em tempo real, permitindo a coleta contínua de dados operacionais.

Problema: Falhas inesperadas em equipamentos industriais geram paradas não planejadas, aumentando custos operacionais, reduzindo a produtividade e impactando negativamente a eficiência do sistema produtivo.

Impacto: A solução proposta visa prever falhas antecipadamente por meio de técnicas de Machine Learning, permitindo a realização de manutenção preditiva, redução de custos e aumento da disponibilidade dos equipamentos.

4. Arquitetura de Dados (Fonte e Dataset)
O projeto utiliza dados estruturados para alimentar os modelos preditivos.

Origem dos Dados:
Dataset de manutenção preditiva disponível em:
https://www.kaggle.com/datasets/stephanmatzka/predictive-maintenance-dataset-ai4i-2020

Características:

Temperatura do ar (Air temperature)
Temperatura do processo (Process temperature)
Velocidade de rotação (Rotational speed)
Torque
Desgaste da ferramenta (Tool wear)
Tipo do produto (Type)
Indicador de falha da máquina (Machine failure)
Volume:
O dataset possui aproximadamente 10.000 registros e 14 atributos técnicos, incluindo variáveis numéricas e categóricas.

5. Plano de Tratamento de Dados (ETL)
O pipeline de dados segue as seguintes etapas:

Extração: Os dados foram carregados a partir de um arquivo no formato CSV utilizando a biblioteca Pandas no ambiente Python (Google Colab).

Transformação: Foram aplicadas as seguintes etapas de tratamento:

Remoção de colunas irrelevantes (UDI e Product ID), por não contribuírem para a previsão
Conversão da variável categórica Type em variáveis numéricas utilizando One-Hot Encoding
Verificação de valores nulos (não foram encontrados valores ausentes)
Padronização dos dados numéricos utilizando StandardScaler para melhorar o desempenho dos modelos de Machine Learning
Carga: Os dados tratados foram exportados para um novo arquivo (dados_tratados.csv), sendo armazenados para utilização nas próximas etapas do projeto (M2 e M3).

6. Análise Exploratória de Dados (M2)
Objetivo: Realizar a exploração dos dados para identificar padrões, correlações e outliers relevantes para a previsão de falhas.

Principais Análises Realizadas Estatística descritiva dos dados Matriz de correlação entre variáveis Identificação de outliers com boxplot Análise de relações entre variáveis com scatterplot Distribuição de variáveis com histogramas Principais Insights Variáveis como Torque e Desgaste da ferramenta possuem forte relação com falhas Outliers podem indicar comportamentos anormais ou falhas críticas Existe padrão entre variáveis operacionais e ocorrência de falha Hipóteses Validadas Quanto maior o torque, maior a chance de falha O desgaste da ferramenta influencia diretamente a falha Outliers podem representar falhas críticas

7. Notebook no Google Colab
(https://colab.research.google.com/drive/17jjNm275cG6SXJODuF8_FYQ4cprOIov2?usp=sharing)

8. Estrutura do Repositório
/docs /data/raw /data/processed /notebooks /scripts requirements.txt

9. Tecnologias Utilizadas
Python Pandas NumPy Matplotlib Seaborn Scikit-learn Google Colab GitHub

10. Apêndice de IA
Ferramenta utilizada: ChatGPT

Forma de uso: Auxílio na estruturação do notebook Sugestão de análises exploratórias Apoio na construção de gráficos Suporte no desenvolvimento de código Python Validação: Todas as análises foram verificadas manualmente pelo grupo Os resultados foram conferidos com base nos dados reais Nenhuma análise foi utilizada sem validação técnica

11. Estrutura do Repositório
A organização do projeto segue a seguinte estrutura:

/docs: Documentação e descrição do projeto
/data/raw: Dados brutos (originais)
/data/processed: Dados tratados após ETL
/notebooks: Notebooks do Google Colab (M1, M2, M3)
/scripts: Scripts auxiliares em Python
requirements.txt: Bibliotecas necessárias para execução
12. Instruções para Execução
Para reproduzir o ambiente e executar o projeto:

Clonar o repositório:
git clone https://github.com/jcesarmph-ui/SmartPredict.git
N1 - 2º Bimestre - Individual - Análise Exploratória de Dados (EDA)

O aluno Júlio César validou estatisticamente que a variável Torque é um preditor relevante na ocorrência de falhas em máquinas industriais. O teste de Mann-Whitney apresentou p-value = 2.26e-64, indicando forte evidência contra a hipótese nula. Além disso, o tamanho do efeito (Cohen's d = 0.79) demonstrou uma diferença de magnitude média a alta entre os grupos, reforçando a importância prática dessa variável para o modelo de manutenção preditiva.

O aluno Lucas Silva validou estatisticamente que a variável de desgaste da ferramenta (Tool wear [min]) é um fator relevante na ocorrência de falhas em máquinas industriais. O teste de Mann-Whitney apresentou p-value= 2.91e-24,ou seja, inferior a 0,05, indicando evidência significativa contra a hipótese nula. Além disso, o tamanho do efeito (Cohen’s d = 0,58) demonstrou uma diferença de magnitude moderada entre os grupos, reforçando a importância prática dessa variável para modelos de manutenção preditiva.

A aluna Sarah Vieira de Andrade validou estatisticamente que a variável de desgaste da ferramenta (Tool wear [min]) é um fator relevante na ocorrência de falhas em máquinas industriais. O teste de Mann-Whitney apresentou p-value = 2.26e-64, valor significativamente inferior a 0,05, indicando forte evidência contra a hipótese nula. Além disso, a análise da diferença entre as médias (≈ 10,54) demonstrou uma variação relevante entre os grupos, reforçando a importância prática dessa variável para modelos de manutenção preditiva.

A aluna Mykaella Dutra validou estatisticamente que a variável temperatura de processo (Process temperature [K]) é um fator relevante na ocorrência de falhas em máquinas industriais. O teste de Mann-Whitney apresentou p-value = 6.49e-05, valor inferior a 0,05, indicando evidência significativa contra a hipótese nula. Além disso, o tamanho do efeito (Cohen’s d = 0.21) demonstrou uma diferença de pequena magnitude entre os grupos, sugerindo que, apesar de estatisticamente relevante, a variável possui impacto prático limitado quando analisada isoladamente, devendo ser utilizada em conjunto com outras variáveis no modelo de manutenção preditiva.
