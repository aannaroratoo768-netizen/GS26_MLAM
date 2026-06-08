## Global Solution — Análise Estatística com Dados do IBGE
### Modelagem Linear para Aprendizagem de Máquina | Ciências da Computação — 1CCPK

---

## Descrição do Projeto

Este projeto realiza uma **análise estatística completa** da distribuição populacional dos municípios brasileiros, utilizando dados reais do **Censo Demográfico 2022** fornecidos pelo **IBGE** via API pública (SIDRA).

A análise foi desenvolvida em **Python** e contempla todas as etapas exigidas pelo Global Solution: coleta e justificativa da base de dados, tabelas de distribuição de frequências, gráficos estatísticos, análises univariadas com estatística descritiva e relatório técnico consolidado.

O contexto do trabalho está alinhado à **nova economia espacial**: dados populacionais georreferenciados são fundamentais para aplicações de Machine Learning em planejamento territorial, cobertura de satélites de comunicação, sensoriamento remoto e políticas públicas orientadas por dados.

---

## Estrutura do Repositório

```
 global-solution-ibge/
├── 📓 global_solution_ibge.ipynb   # Notebook principal com todo o código
├── 📄 dados_ibge_censo2022.csv     # Base de dados gerada (IBGE Censo 2022)
├── 📊 grafico1_histograma_log_populacao.png
├── 📊 grafico2_barras_porte_regiao.png
├── 📊 grafico3_boxplot_quartis.png
├── 📝 relatorio_estatistico.txt    # Relatório técnico em texto
├── 📋 relatorio_estatistico.pdf    # Relatório técnico final (PDF)
└── 📖 README.md
```

---

## Base de Dados

| Item | Descrição |
|------|-----------|
| **Fonte** | IBGE — Instituto Brasileiro de Geografia e Estatística |
| **Pesquisa** | Censo Demográfico 2022 |
| **API** | SIDRA — Sistema IBGE de Recuperação Automática |
| **URL** | https://servicodados.ibge.gov.br/api/docs/agregados |
| **Cobertura** | 5.570 municípios brasileiros |
| **Formato** | JSON (API) → CSV (exportado pelo notebook) |
| **Variáveis** | Município, Estado, Região, População, Porte, Log₁₀(Pop.) |

### Justificativa da escolha
- ✅ **Relevância:** Maior pesquisa estatística do Brasil, com cobertura nacional total
- ✅ **Qualidade:** Coleta e controle metodológico institucional do IBGE
- ✅ **Aderência ao tema:** Base essencial para ML aplicado à economia espacial e planejamento territorial
- ✅ **Potencial analítico:** Contém variáveis discretas e contínuas, com distribuição log-normal clássica
- ✅ **Acesso aberto:** API REST pública, sem autenticação, acessada diretamente pelo código

---

## Etapas da Análise

### 01 — Coleta e Justificativa da Base
Dados obtidos automaticamente via API SIDRA do IBGE, sem necessidade de download manual. O notebook acessa o endpoint da Tabela 9514 (população por município, Censo 2022) e estrutura os dados em um DataFrame pandas.

### 02 — Tabelas de Distribuição de Frequências
- **Variável discreta:** Porte do município (1 = Muito Pequeno → 5 = Metrópole), com frequência absoluta, relativa e acumulada
- **Variável contínua:** Log₁₀ da população, com número de classes calculado pela Regra de Sturges, ponto médio de cada classe, e frequências absoluta, relativa e acumulada

### 03 — Gráficos Estatísticos
- **Gráfico 1:** Histograma do Log₁₀(População) com curva KDE e linha da média
- **Gráfico 2:** Barras agrupadas — quantidade de municípios por porte e região geográfica
- **Bônus:** Boxplot comparativo das duas variáveis analisadas

### 04 — Análises Univariadas
Duas análises completas contendo:
- Medidas de tendência central: média, mediana e moda
- Medidas de dispersão: máximo, mínimo, amplitude, variância e desvio padrão
- Medidas separatrizes: Q1, Q2, Q3 e IQR
- Interpretação textual dos resultados

### 05 — Relatório Técnico
Relatório consolidado com visão geral da base, padrões identificados, análise regional e implicações para Machine Learning e economia espacial.

---

## Como Executar

### Opção 1 — Google Colab (recomendado)
1. Acesse [colab.research.google.com](https://colab.research.google.com)
2. Vá em **Arquivo → Fazer upload de notebook**
3. Selecione o arquivo `global_solution_ibge.ipynb`
4. Execute todas as células com **Runtime → Run all**

### Opção 2 — Localmente (Jupyter)
```bash
# Instalar dependências
pip install pandas numpy matplotlib seaborn requests scipy

# Executar o Jupyter
jupyter notebook global_solution_ibge.ipynb
```

> O notebook acessa a API do IBGE em tempo real. É necessária conexão com a internet.

---

## Tecnologias Utilizadas

| Biblioteca | Versão | Uso |
|------------|--------|-----|
| `pandas` | ≥ 1.5 | Manipulação de dados e tabelas |
| `numpy` | ≥ 1.23 | Cálculos numéricos e estatísticos |
| `matplotlib` | ≥ 3.6 | Construção dos gráficos |
| `seaborn` | ≥ 0.12 | Estilização e temas visuais |
| `scipy` | ≥ 1.9 | Estatística descritiva avançada |
| `requests` | ≥ 2.28 | Acesso à API REST do IBGE |

---

## Principais Resultados

- **~72%** dos municípios brasileiros têm menos de 10.000 habitantes
- A distribuição da população segue um padrão **log-normal**, clássico em dados sociodemográficos
- Após transformação logarítmica: média ≈ 3,9 e desvio padrão ≈ 0,65 (distribuição quase simétrica)
- Menos de **1%** dos municípios são metrópoles, mas concentram grande parte da população urbana
- A transformação log₁₀ é essencial no pré-processamento para modelos de regressão linear

---

## Fonte dos Dados

```
Instituto Brasileiro de Geografia e Estatística (IBGE)
Censo Demográfico 2022 — Tabela 9514
API SIDRA: https://servicodados.ibge.gov.br/api/v3/agregados/9514
Acesso público e gratuito, sem necessidade de autenticação.
```

---

Anna Karla - RM: 569604

---

*Global Solution | Modelagem Linear para Aprendizagem de Máquina*
