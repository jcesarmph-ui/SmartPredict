# Projeto: Manutenção Preditiva de Falhas Industriais com Machine Learning

---

## 1. Identificação do Grupo

**Instituição:** Faculdade Engenheiro Salvador Arena
**Curso:** Engenharia de Controle e Automação
**Grupo:** Grupo 1

**Integrantes:**

* Júlio César Moreira Pereira - RA: 062210025
* Lucas Silva de Alencar - RA: 062210011
* Mykaella Soares Dutra - RA: 062210031
* Sarah Vieira de Andrade - RA: 062210005

---

## 2. Área Problema Selecionada

* Manutenção Preditiva de Zero-Downtime
* Eficiência Energética e Descarbonização via Smart Grids
* Controle de Qualidade Autônomo com Visão Computacional
* Gêmeos Digitais (Digital Twins) e Analytics em Tempo Real

---

## 3. Diagnóstico e Definição do Problema

**Contexto:**
O projeto está inserido no cenário da Indústria 4.0, onde sensores monitoram máquinas em tempo real, permitindo a coleta contínua de dados operacionais.

**Problema:**
Falhas inesperadas em equipamentos industriais geram paradas não planejadas, aumentando custos operacionais, reduzindo a produtividade e impactando negativamente a eficiência do sistema produtivo.

**Impacto:**
A solução proposta visa prever falhas antecipadamente por meio de técnicas de Machine Learning, permitindo a realização de manutenção preditiva, redução de custos e aumento da disponibilidade dos equipamentos.

---

## 4. Arquitetura de Dados (Fonte e Dataset)

**Origem dos Dados:**
https://www.kaggle.com/datasets/stephanmatzka/predictive-maintenance-dataset-ai4i-2020

**Características:**

* Temperatura do ar (Air temperature)
* Temperatura do processo (Process temperature)
* Velocidade de rotação (Rotational speed)
* Torque
* Desgaste da ferramenta (Tool wear)
* Tipo do produto (Type)
* Indicador de falha da máquina (Machine failure)

**Volume:**
O dataset possui aproximadamente 10.000 registros e 14 atributos técnicos.

---

## 5. Plano de Tratamento de Dados (ETL)

**Extração:**
Dados carregados a partir de arquivo CSV utilizando Pandas no Google Colab.

**Transformação:**

* Remoção das colunas UDI e Product ID
* Conversão da variável Type via One-Hot Encoding
* Verificação de valores nulos (não encontrados)
* Padronização com StandardScaler

**Carga:**
Dados exportados para `dados_tratados.csv` para uso nas etapas seguintes.

---

## 6. Análise Exploratória de Dados (M2)

**Objetivo:**
Identificar padrões, correlações e outliers relevantes para previsão de falhas.

**Principais análises:**

* Estatística descritiva
* Matriz de correlação
* Boxplot para outliers
* Scatterplot entre variáveis
* Histogramas de distribuição

**Principais insights:**

* Torque e desgaste da ferramenta possuem forte relação com falhas
* Outliers indicam comportamentos anormais
* Existe padrão entre variáveis operacionais e falha

**Hipóteses validadas:**

* Quanto maior o torque, maior a chance de falha
* O desgaste da ferramenta influencia diretamente a falha
* Outliers podem representar falhas críticas

---

## 7. Notebook no Google Colab

https://colab.research.google.com/drive/17jjNm275cG6SXJODuF8_FYQ4cprOIov2?usp=sharing

---

## 8. Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab
* GitHub

---

## 9. Estrutura do Repositório

```
/docs
/data/raw
/data/processed
/notebooks
/scripts
requirements.txt
```

---

## 10. Apêndice de IA

**Ferramenta utilizada:** ChatGPT

**Forma de uso:**

* Estruturação do notebook
* Sugestão de análises
* Apoio na construção de gráficos
* Suporte no desenvolvimento de código

**Validação:**

* Todas as análises foram verificadas manualmente
* Resultados conferidos com base nos dados reais
* Nenhuma análise foi utilizada sem validação técnica

---

## 11. Instruções para Execução

Clonar o repositório:

```
git clone https://github.com/jcesarmph-ui/SmartPredict.git
```

---

## 12. Análise Estatística Individual

**Júlio César Moreira Pereira:**
Validou que a variável Torque é um preditor relevante de falha.
Teste de Mann-Whitney: p-value = 2.26e-64
Cohen’s d = 0.79 (efeito médio-alto)

**Lucas Silva de Alencar:**
Validou o desgaste da ferramenta como fator relevante.
p-value = 2.91e-24
Cohen’s d = 0.58 (efeito moderado)

**Sarah Vieira de Andrade:**
Confirmou o impacto do desgaste da ferramenta.
p-value = 2.26e-64
Diferença de médias ≈ 10,54

**Mykaella Soares Dutra:**
Validou a temperatura de processo como relevante.
p-value = 6.49e-05
Cohen’s d = 0.21 (efeito pequeno)

---

## 13. Modelo de Inteligência Artificial (M3)

Foi desenvolvido um modelo de classificação utilizando Random Forest para prever falhas em máquinas industriais.

**Resultados:**

* Acurácia: 1.00
* F1-score: 1.00

**Matriz de confusão:**

* 1932 verdadeiros negativos
* 68 verdadeiros positivos
* 0 falsos positivos
* 0 falsos negativos

O modelo apresentou desempenho máximo, indicando forte capacidade de identificação de padrões.


14. Protótipo (Google AI Studio)

[https://ai.studio/apps/f42a79e2-3484-4d5e-bfe2-9e2cae551098](https://ai.studio/apps/f42a79e2-3484-4d5e-bfe2-9e2cae551098)
