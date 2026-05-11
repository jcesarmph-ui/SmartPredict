# 🔧 Projeto: SmartPredict - Manutenção Preditiva de Falhas Industriais com Machine Learning

> Projeto desenvolvido para a disciplina de Ciência de Dados com foco em manutenção preditiva industrial utilizando técnicas de Machine Learning, Análise Exploratória de Dados e otimização de modelos preditivos.

![Status do Projeto](https://img.shields.io/badge/Status-Concluído%20/%20M4-brightgreen)
![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Modelagem-orange?logo=scikit-learn)
![Google AI Studio](https://img.shields.io/badge/Google%20AI%20Studio-Dashboard-purple)

---

# 👥 1. Identificação do Grupo

- **Instituição:** Faculdade Engenheiro Salvador Arena
- **Curso:** Engenharia de Controle e Automação
- **Disciplina:** Ciência de Dados
- **Grupo:** Grupo 1

## Integrantes

* **Júlio César Moreira Pereira** - RA: 062210025
* **Lucas Silva de Alencar** - RA: 062210011
* **Mykaella Soares Dutra** - RA: 062210031
* **Sarah Vieira de Andrade** - RA: 062210005

---

# 🎯 2. Área-Problema Selecionada

O grupo selecionou a área de **Manutenção Preditiva de Zero-Downtime**.

## ✅ Recorte do projeto

Predição de falhas em máquinas industriais através da análise de sensores operacionais utilizando técnicas de Machine Learning.

## 📌 Justificativa e Hipótese

A manutenção corretiva gera altos custos industriais devido a paradas inesperadas de máquinas e perda de produtividade. O projeto busca antecipar falhas utilizando dados de sensores industriais.

A hipótese principal é que variáveis operacionais como torque, desgaste da ferramenta e temperatura possuem forte relação com a ocorrência de falhas mecânicas.

---

# 🧩 3. Diagnóstico e Definição do Problema

O projeto está inserido no contexto da Indústria 4.0, onde sensores monitoram equipamentos em tempo real, permitindo a coleta contínua de dados operacionais.

- **Problema:** Falhas inesperadas em equipamentos industriais geram paradas não planejadas, aumento de custos operacionais e redução da eficiência produtiva.

- **Impacto:** A solução desenvolvida busca reduzir o downtime industrial através da previsão antecipada de falhas utilizando Inteligência Artificial.

---

# 🗂️ 4. Arquitetura de Dados (Fonte e Dataset)

* **Origem:** https://www.kaggle.com/datasets/stephanmatzka/predictive-maintenance-dataset-ai4i-2020

* **Características:** O conjunto de dados apresenta aproximadamente 10.000 registros e 14 atributos técnicos.

* **Variáveis Principais:**
  - Air temperature
  - Process temperature
  - Rotational speed
  - Torque
  - Tool wear
  - Type

* **Variável Alvo:** `Machine failure`

---

# 🔄 5. Plano de Tratamento de Dados (ETL)

O pipeline de dados segue as seguintes etapas:

1. **Extração:** Carregamento dos dados brutos em formato CSV utilizando Pandas no Google Colab.

2. **Transformação:**
   - Remoção das colunas UDI e Product ID
   - Conversão da variável categórica Type utilizando One-Hot Encoding
   - Verificação de valores nulos
   - Padronização dos dados utilizando StandardScaler

3. **Carga:** Exportação dos dados tratados para `dados_trata.csv` (dados tratados) na pasta `/data/processed`.

---

# 📈 6. Desenvolvimento e Otimização (M2, M3 e M4)

## M2 — Análise Exploratória (EDA)

Foi realizada a análise exploratória dos dados para identificar padrões, correlações e outliers relevantes para a previsão de falhas.

### Principais análises realizadas:
- Estatística descritiva
- Heatmap de correlação
- Boxplot para identificação de outliers
- Scatterplots entre variáveis
- Histogramas de distribuição

### Principais insights:
- Torque e desgaste da ferramenta possuem forte relação com falhas
- Outliers indicam possíveis comportamentos críticos
- Existe correlação entre variáveis operacionais e falhas industriais

---

## M3 — Modelagem de IA

Foi desenvolvido um modelo de classificação utilizando Random Forest para prever falhas industriais.

### Resultados obtidos:
- **Acurácia:** 1.00
- **F1-Score:** 1.00

### Matriz de Confusão:
- 1932 verdadeiros negativos
- 68 verdadeiros positivos
- 0 falsos positivos
- 0 falsos negativos

O modelo apresentou excelente capacidade de identificação de padrões relacionados às falhas industriais.

---

## M4 — Refinamento e Otimização Profissional

O modelo passou por um processo de refinamento técnico para garantir maior robustez e capacidade de generalização.

### Ajuste de Hiperparâmetros

Foi utilizada a técnica `RandomizedSearchCV` para encontrar automaticamente a melhor configuração do modelo Random Forest.

### Melhor configuração encontrada:

```python
RandomForestClassifier(
    max_depth=5,
    min_samples_split=10,
    n_estimators=200
)
```

### Interpretação:
- `n_estimators=200`: utilização de 200 árvores para maior robustez
- `max_depth=5`: limitação da profundidade para evitar overfitting
- `min_samples_split=10`: redução de divisões excessivamente específicas

---

### Validação Cruzada (Cross-Validation)

Resultados da validação cruzada:

```python
Scores: [0.9995 0.999  0.6715 0.998  0.999 ]
Média: 0.9334
```

A média de aproximadamente 93,34% demonstra elevada capacidade de generalização do modelo, indicando boa robustez para aplicações reais de manutenção preditiva.

---

### Engenharia de Atributos Final

Foi realizada análise de importância das variáveis (*Feature Importance*), identificando Torque, Tool wear e Process temperature como os atributos mais relevantes para a previsão de falhas.

---

# 🖥️ 7. Dashboard de Monitoramento

Foi desenvolvido um dashboard no Google AI Studio para visualização dos resultados do modelo em tempo real.

## Link do Protótipo
[https://ai.studio/apps/f42a79e2-3484-4d5e-bfe2-9e2cae551098](https://aistudio.google.com/apps/f42a79e2-3484-4d5e-bfe2-9e2cae551098?showPreview=true&showAssistant=true)

## Funcionalidades
- Exibição da acurácia do modelo
- Indicadores de falhas detectadas
- Visualização gráfica das predições
- Interface para monitoramento industrial


# Dashboard de Monitoramento em Tempo Real
https://ai.studio/apps/90c99e26-d356-4ec3-bf14-7a73f042e0fd

---

# 🧱 8. Estrutura do Repositório

```bash
/
├── data/
│   ├── raw/
│   └── processed/
│
├── docs/
│
├── images/
│
├── notebooks/
│   ├── M2_EDA.ipynb
│   ├── M3_Modelagem.ipynb
│   ├── M4_Otimizacao.ipynb
│   └── n1_individual/
│
├── scripts/
│
├── requirements.txt
└── README.md
```

---

# 🚀 9. Instruções para Execução

## Clonar o repositório

```bash
git clone https://github.com/jcesarmph-ui/SmartPredict.git
```

## Instalar dependências

```bash
pip install -r requirements.txt
```

---

# 🧪 10. N1 Individual — Aprofundamento Estatístico

| Integrante | Variável Analisada | Teste Realizado |

| Júlio César Moreira Pereira | Torque | Mann-Whitney + Cohen's d | Validou que a variável Torque é um preditor relevante de falha. Teste de Mann-Whitney: p-value = 2.26e-64 Cohen’s d = 0.79 (efeito médio-alto)

| Lucas Silva de Alencar | Tool wear | Mann-Whitney + Cohen's d | Validou o desgaste da ferramenta como fator relevante. p-value = 2.91e-24 Cohen’s d = 0.58 (efeito moderado)

| Sarah Vieira de Andrade | Tool wear | Mann-Whitney | Confirmou o impacto do desgaste da ferramenta. p-value = 2.26e-64 Diferença de médias ≈ 10,54

| Mykaella Soares Dutra | Process temperature | Mann-Whitney + Cohen's d | Validou a temperatura de processo como relevante. p-value = 6.49e-05 Cohen’s d = 0.21 (efeito pequeno)

---

# 🤖 11. Apêndice de IA

## Ferramentas utilizadas
- ChatGPT
- Google AI Studio

## Aplicação
- Estruturação dos notebooks
- Sugestão de análises exploratórias
- Apoio na construção do dashboard
- Suporte na organização do pipeline de Machine Learning
- Revisão textual e documentação

## Validação
Todos os resultados, métricas, gráficos e interpretações estatísticas foram revisados e validados manualmente pelo grupo.

---

© 2026 - Projeto de Ciência de Dados - Faculdade Engenheiro Salvador Arena
14. Protótipo (Google AI Studio)

