# SmartPredict | Manutenção Preditiva com Machine Learning

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"/>
  <img src="https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white" alt="Scikit-learn"/>
  <img src="https://img.shields.io/badge/Jupyter- F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter"/>
  <img src="https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Google Colab"/>
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=plotly&logoColor=white" alt="Matplotlib"/>
  <img src="https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge&logo=python&logoColor=white" alt="Seaborn"/>
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git"/>
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</p>

<p align="center">
  Solução analítica para previsão de falhas industriais por meio de análise exploratória, tratamento de dados, modelagem preditiva e avaliação de algoritmos de Machine Learning.
</p>

---

## Visão Geral

O SmartPredict é um projeto de Ciência de Dados e Inteligência Artificial voltado à manutenção preditiva industrial, utilizando dados operacionais para investigar padrões associados à ocorrência de falhas em equipamentos.

A solução utiliza o conjunto de dados AI4I 2020, que reúne variáveis relacionadas às condições de operação de máquinas, permitindo estudar a relação entre parâmetros técnicos e a ocorrência de falhas.

O fluxo de desenvolvimento abrange preparação dos dados, análise exploratória, investigação estatística, treinamento de modelos, otimização de hiperparâmetros e avaliação dos resultados.

## Problema Abordado

Falhas inesperadas em equipamentos industriais podem provocar interrupções operacionais, custos de manutenção e redução da disponibilidade dos ativos.

A manutenção preditiva utiliza dados operacionais e técnicas analíticas para identificar padrões associados a situações de risco, oferecendo subsídios para decisões de manutenção.

O projeto investiga a aplicação de Machine Learning à classificação de falhas a partir de variáveis como:

- Temperatura do ar.
- Temperatura do processo.
- Velocidade de rotação.
- Torque.
- Desgaste da ferramenta.
- Tipo de produto.

## Objetivos

- Explorar e compreender os dados operacionais.
- Identificar relações estatísticas entre variáveis e falhas.
- Preparar os dados para treinamento de modelos.
- Construir um classificador de falhas com Random Forest.
- Investigar a importância das variáveis preditoras.
- Otimizar hiperparâmetros e avaliar a generalização do modelo.
- Apresentar os resultados por meio de visualizações e protótipos de dashboard.

## Fonte de Dados

O projeto utiliza o conjunto de dados **AI4I 2020 Predictive Maintenance Dataset**, disponibilizado no Kaggle.

[Consultar o dataset AI4I 2020 no Kaggle](https://www.kaggle.com/datasets/stephanmatzka/predictive-maintenance-dataset-ai4i-2020)

O conjunto possui aproximadamente 10 mil registros e reúne informações operacionais utilizadas na investigação de falhas de máquinas.

### Variável-alvo

`Machine failure`

A variável indica a ocorrência de falha, permitindo formular o problema como uma tarefa de classificação supervisionada.

## Pipeline de Ciência de Dados

### 1. Extração e preparação dos dados

Os dados são carregados em Python a partir de arquivos CSV, utilizando Pandas para manipulação e preparação.

As etapas incluem:

- Remoção de identificadores que não contribuem diretamente para a previsão.
- Verificação de valores ausentes.
- Codificação de variáveis categóricas com One-Hot Encoding.
- Preparação dos atributos numéricos.
- Organização dos dados para treinamento e avaliação.

### 2. Análise Exploratória de Dados

A análise exploratória investiga a distribuição das variáveis, as relações entre atributos e a ocorrência de falhas.

As técnicas utilizadas incluem:

- Estatística descritiva.
- Matrizes de correlação e heatmaps.
- Histogramas.
- Boxplots.
- Gráficos de dispersão.
- Análise comparativa entre registros com e sem falha.

A investigação concentra-se especialmente nas variáveis operacionais potencialmente associadas às falhas, como torque, desgaste da ferramenta e temperatura do processo.

### 3. Modelagem preditiva

O algoritmo Random Forest é utilizado para construir um modelo de classificação.

O método combina múltiplas árvores de decisão para produzir previsões a partir dos atributos operacionais.

O fluxo de modelagem inclui:

- Separação dos conjuntos de treinamento e teste.
- Preparação das variáveis de entrada.
- Treinamento do classificador.
- Geração de previsões.
- Avaliação por métricas de classificação.
- Análise da matriz de confusão.

### 4. Otimização de hiperparâmetros

O projeto utiliza `RandomizedSearchCV` para investigar configurações do Random Forest.

Uma das configurações identificadas durante os experimentos foi:

```python
RandomForestClassifier(
    max_depth=5,
    min_samples_split=10,
    n_estimators=200
)
```

Os parâmetros controlam, respectivamente, a profundidade máxima das árvores, o número mínimo de amostras necessário para dividir um nó e a quantidade de árvores do modelo.

### 5. Avaliação e interpretação

A avaliação considera métricas de classificação e validação cruzada para investigar o comportamento do modelo em diferentes divisões dos dados.

Também é utilizada a análise de importância das variáveis para identificar quais atributos mais contribuem para as previsões do classificador.

## Resultados Experimentais

Os resultados registrados nos experimentos incluem:

| Métrica ou análise | Resultado registrado |
|---|---|
| Acurácia inicial | 1,00 |
| F1-score inicial | 1,00 |
| Média reportada na validação cruzada | Aproximadamente 93,34% |
| Método de otimização | RandomizedSearchCV |
| Modelo principal | Random Forest |

A avaliação inicial registrou uma matriz de confusão com 1.932 verdadeiros negativos, 68 verdadeiros positivos, nenhum falso positivo e nenhum falso negativo no conjunto avaliado.

Entretanto, a validação cruzada apresentou resultados variáveis, incluindo uma pontuação de aproximadamente 0,6715 em uma das divisões.

Essa diferença evidencia a importância de analisar a distribuição dos resultados, a representatividade das divisões e a possível influência de sobreajuste ou particularidades do conjunto de dados. A acurácia inicial, isoladamente, não garante que o modelo terá desempenho equivalente em novos dados.

Os resultados devem ser interpretados como evidências experimentais obtidas no dataset utilizado, e não como garantia de desempenho em equipamentos industriais reais.

## Dashboard de Monitoramento

Foram desenvolvidos protótipos de interface para apresentar informações relacionadas às previsões e aos indicadores do modelo.

### Protótipos disponíveis

- [Dashboard de monitoramento](https://ai.studio/apps/f42a79e2-3484-4d5e-bfe2-9e2cae551098)
- [Dashboard de monitoramento em tempo real — protótipo](https://ai.studio/apps/90c99e26-d356-4ec3-bf14-7a73f042e0fd)

As interfaces foram concebidas para demonstrar a visualização de indicadores, previsões e informações relacionadas às falhas.

Os links correspondem a protótipos, não devendo ser interpretados automaticamente como uma solução industrial conectada a sensores reais.

## Tecnologias e Ferramentas

| Tecnologia | Aplicação no projeto |
|---|---|
| Python | Implementação do fluxo analítico e da modelagem. |
| Pandas | Manipulação e preparação dos dados. |
| NumPy | Operações numéricas e suporte ao processamento. |
| Scikit-learn | Treinamento, otimização e avaliação dos modelos. |
| Random Forest | Classificação de falhas. |
| RandomizedSearchCV | Busca de hiperparâmetros. |
| StandardScaler | Padronização de variáveis numéricas. |
| One-Hot Encoding | Representação de variáveis categóricas. |
| Matplotlib | Visualização gráfica dos dados e resultados. |
| Seaborn | Visualizações estatísticas. |
| Google Colab e Jupyter Notebook | Desenvolvimento e execução dos experimentos. |
| Git e GitHub | Versionamento e documentação. |

## Estrutura do Repositório

```text
SmartPredict/
├── apresentacao/
│   └── powerpoint/
├── dashboard/
├── data/
├── images/
├── notebooks/
├── N1_Julio_Cesar.ipynb
└── README.md
```

- `apresentacao/`: materiais de apresentação do projeto.
- `dashboard/`: arquivos relacionados às interfaces de visualização.
- `data/`: dados utilizados no fluxo analítico.
- `images/`: recursos gráficos e imagens.
- `notebooks/`: notebooks de análise e experimentação.
- `N1_Julio_Cesar.ipynb`: notebook de aprofundamento estatístico.

## Competências Demonstradas

- Ciência de Dados e análise exploratória.
- Estatística aplicada à investigação de falhas.
- Engenharia e preparação de atributos.
- Machine Learning supervisionado.
- Otimização de hiperparâmetros.
- Avaliação e interpretação de modelos.
- Visualização de dados e construção de protótipos analíticos.
- Aplicação de Inteligência Artificial à manutenção preditiva.

---

**Projeto de Ciência de Dados aplicado à manutenção preditiva, integrando análise estatística, preparação de dados e modelagem de Machine Learning para investigação de padrões associados a falhas industriais.**
