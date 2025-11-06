# GB Exploratory Analysis of Brazilian Federal Government Travel Expenses (2024)

This Data Science project performs an exploratory analysis of travel expenses for federal civil servants in Brazil for the year 2024, using transparency data provided by the Federal Government.

The main goal is to identify the distribution of expenditures, map the job roles with the highest volume of expenses, and visualize anomalies or issues concerning data transparency in the records.

## 📊 Data and Source

| Field | Detail |
| :--- | :--- |
| **Data Source** | Transparency Portal / Open Data (implied by the file name `GovBR_Dataset_viagem`) |
| **File Used** | `2024_Viagem.csv` |
| **Content** | Details on each travel process, including the superior agency, requesting agency, CPF (anonymized), name, job role, destination, motive, and detailed values (per diem, airfare, other expenses, and refund). |

## 🛠️ Technologies and Tools

* **Language:** Python
* **Environment:** Jupyter Notebook / Google Colab
* **Libraries:**
    * `pandas` (for data manipulation and cleaning)
    * `matplotlib.pyplot` (for data visualization)
    * `csv` (used for import)

## 📋 Methodology

The workflow in the notebook (`GovBR_Dataset_viagem.ipynb`) follows the following main steps:

1.  **Data Loading and Cleaning:**
    * Reading the CSV file with `Windows-1252` encoding and semicolon (`;`) separator.
    * Conversion of monetary value columns (`Valor diárias`, `Valor passagens`, `Valor devolução`, `Valor outros gastos`) to a numeric (Float) type, treating the comma (`,`) as a decimal separator.
2.  **Total Expense Calculation:**
    * Creation of the `despesas_totais` column, summing the `Valor diárias`, `Valor passagens`, and `Valor outros gastos` fields.
3.  **Analysis by Job Role:**
    * Grouping the data by the `Cargo` (Job Role) column and summing the `despesas_totais` for each function.
    * Ordering and selection of the top job roles with the highest volume of expenses.
4.  **Visualization:**
    * Creation of horizontal bar charts to visualize the ranking of expenditures by job role.
    * Adjustment of the X-axis scale (limit set at **R$ 500 Million**) to improve visibility for job roles with lower expenses, preventing visual obscuration by expenditure *outliers*.
    * Creation of pie charts to demonstrate the percentage proportion of expenses among the Top 5 job roles.
    * Creation of vertical bar charts to visualize the average duration of trips (in days) per job role.

## 📊 Results

* **Quantitative Travel per Job Role:** The category "Informações protegidas por sigilo" (Protected Information) leads the volume of trips with nearly 10 thousand occurrences, a figure that triples the second place. This massive concentration in opaque data raises serious concerns about organizational accountability.
* **Total Cost per Job Role:** Expenditures are dominated by opaque categories, with "Informações protegidas por sigilo" totaling R$ 49 million in travel expenses. The high total cost (approximately R$ 9 million) for 'Professor do Magistério Superior' also requires investigation into the nature and necessity of these trips.
* **Most Expensive Trip per Job Role:** The highest individual expense for a single trip (around R$ 160 thousand) is allocated to unidentified categories, followed by a singular R$ 116 thousand expenditure by a Basic Technical Education Professor. Such values demand an in-depth audit of the motives and approval processes.
* **Job Roles with Total Cost > R$ 1 Million:** The set of job roles with total expenses exceeding R$ 1 million is substantially impacted by "Informações protegidas por sigilo", consolidating its influence of approximately R$ 49 million.
* **Impact of Null (NaN) and 'Unidentified' Values:** Over 23 thousand entries with travel expenses did not have the 'Cargo' field specified (NaN), feeding the 'Não Identificado' (Unidentified) category, which leads the volume of trips. This critical data quality failure and cost concentration in opaque categories suggests a structural governance problem.
* **Proportional Cost Analysis:** The chart demonstrates that the 'Unidentified' and 'Informações Sigilosas' job roles together consume over 90% of the five largest travel costs. This alarming disproportion points to a massive concentration of expenditures in categories lacking transparency.
* **Average Duration vs. Total Cost Relationship:** Despite having a significantly lower average trip duration (26 days vs. 217 days for the 'Primeiro Sargento'), the 'Unidentified' role registers a total expense of R$ 222 million. This cost/duration anomaly indicates inefficiency and mandates an immediate audit for resource tracking.

## 🔑 Key Insights

The analysis highlights the high concentration of spending in a few categories and points to transparency challenges:

* **Outliers and Lack of Transparency:** A significant portion of total expenses is allocated to categories representing lack of identification or secrecy, such as "Unidentified" and "Informações protegidas por sigilo".
* **Critical Issue (Potential Fund Misallocation):** The notebook raises the issue of possible fund misallocation, given that the largest volume of expenses is in job roles that cannot be identified, compromising public money tracking.
* **Spending Job Roles:** The rest of the expense ranking is filled by roles with frequent travel, such as `PROFESSOR DO MAGISTERIO SUPERIOR`.

## 🚀 How to Run the Project

1.  **Clone the Repository:**
    ```bash
    git clone [https://www.youtube.com/shorts/3mMG25WHLkU](https://www.youtube.com/shorts/3mMG25WHLkU)
    cd [your_repository_name]
    ```
2.  **Obtain the Dataset:**
    * Download the `2024_Viagem.csv` file from the official Federal Government open data source.
    * Place the file in the folder structure expected by the notebook (as per the `trip` variable in the first code block). **Note:** If you are using Colab, the path will need to be adapted.
3.  **Execute the Notebook:**
    * Open the `GovBR_Dataset_viagem.ipynb` file in Jupyter Notebook, JupyterLab, or Google Colab.
    * Run the cells sequentially to replicate the analysis and generate the charts.



# BR Análise Exploratória de Despesas de Viagens do Governo Federal (2024) 

Este projeto de Data Science realiza uma análise exploratória dos dados de despesas com viagens de servidores públicos federais referentes ao ano de 2024, utilizando dados de transparência do Governo Federal.

O objetivo principal é identificar a distribuição dos gastos, mapear os cargos com maior volume de despesas e visualizar anomalias ou questões de transparência nos registros.

## 📊 Dados e Fonte

| Campo | Detalhe |
| :--- | :--- |
| **Fonte dos Dados** | Portal da Transparência / Dados Abertos (implícito pelo nome `GovBR_Dataset_viagem`) |
| **Arquivo Utilizado** | `2024_Viagem.csv` |
| **Conteúdo** | Detalhes sobre cada processo de viagem, incluindo órgão superior, órgão solicitante, CPF (anonimizado), nome, cargo, destino, motivo e valores detalhados (diárias, passagens, outros gastos e devolução). |

## 🛠️ Tecnologias e Ferramentas

* **Linguagem:** Python
* **Ambiente:** Jupyter Notebook / Google Colab
* **Bibliotecas:**
    * `pandas` (para manipulação e limpeza de dados)
    * `matplotlib.pyplot` (para visualização de dados)
    * `csv` (utilizado na importação)

## 📋 Metodologia da Análise

O fluxo de trabalho no notebook (`GovBR_Dataset_viagem.ipynb`) segue as seguintes etapas principais:

1.  **Carregamento e Limpeza de Dados:**
    * Leitura do arquivo CSV com codificação `Windows-1252` e separador `;`.
    * Conversão das colunas de valores monetários (`Valor diárias`, `Valor passagens`, `Valor devolução`, `Valor outros gastos`) para o tipo numérico (Float), tratando a vírgula (`,`) como separador decimal.
2.  **Cálculo de Despesas Totais:**
    * Criação da coluna `despesas_totais`, somando os campos `Valor diárias`, `Valor passagens` e `Valor outros gastos`.
3.  **Análise por Cargo:**
    * Agrupamento dos dados pela coluna `Cargo` e soma das `despesas_totais` para cada função.
    * Ordenação e seleção dos top cargos com maior volume de gastos.
4.  **Visualização:**
    * Criação de gráficos de barras horizontais para visualizar o ranking de gastos por cargo.
    * Ajuste da escala do eixo X (limite em **R$ 500 Milhões**) para melhorar a visibilidade dos cargos com gastos menores, evitando o ofuscamento causado por *outliers* de despesas.
    * Criação de gráficos de pizza para demonstrar a proporção percentual dos gastos entre o Top 5 cargos.
    * Criação de gráficos de barras verticais para visualizar a duração média das viagens (em dias) por cargo.

## 📊 Análise de Resultados

* **Quantitativo de Viagens por Cargo:** A categoria "Informações protegidas por sigilo" lidera o volume de viagens com quase 10 mil ocorrências, um número que triplica o segundo colocado. Esta concentração massiva em dados não transparentes levanta sérias preocupações sobre a prestação de contas dos órgãos.
* **Custo Total por Cargo:** Os gastos são dominados pelas categorias opacas, com "Informações protegidas por sigilo" totalizando R$ 49 milhões em despesas de viagens. O alto custo total (aproximadamente R$ 9 milhões) do 'Professor do Magistério Superior' também demanda investigação sobre a natureza e necessidade dessas viagens.
* **Viagem Mais Cara por Cargo:** A maior despesa individual (cerca de R$ 160 mil) está alocada em categorias não identificadas, seguida por um gasto singular de R$ 116 mil de um Professor de Ensino Básico Técnico. Tais valores exigem uma auditoria aprofundada nos motivos e processos de aprovação.
* **Cargos com Custo Total > R$ 1 Milhão:** O conjunto de cargos com despesas totais acima de R$ 1 milhão é substancialmente impactado por "Informações protegidas por sigilo", consolidando sua influência de aproximadamente R$ 49 milhões.
* **Impacto de Valores Nulos (NaN) e 'Não Identificado':** Mais de 23 mil entradas com despesas não tiveram o campo 'Cargo' especificado (NaN), alimentando a categoria 'Não Identificado', a qual lidera o volume de viagens. Essa falha crítica na qualidade dos dados e a concentração de custos em categorias opacas sugere um problema estrutural de governança.
* **Análise Proporcional dos Custos:** O gráfico demonstra que os cargos 'Não Identificado' e 'Informações Sigilosas' consomem juntos mais de 90% dos cinco maiores custos de viagens. Esta desproporção alarmante aponta para uma concentração massiva de gastos em categorias que carecem de transparência.
* **Relação Duração Média vs. Custo Total:** Apesar de ter uma duração média de viagens significativamente menor (26 dias vs. 217 dias do Primeiro Sargento), o cargo 'Não Identificado' registra uma despesa total de R$ 222 milhões. Esta anomalia na relação custo/duração indica uma ineficiência e exige imediata auditoria para rastreamento dos recursos.


## 🔑 Principais Insights

A análise ressalta a alta concentração de gastos em poucas categorias e aponta para desafios na transparência:

* **Outliers e Falta de Transparência:** Uma parte significativa das despesas totais está alocada em categorias que representam falta de identificação ou sigilo, como "Não identificado" e "Informações protegidas por sigilo".
* **Questão Crítica (Desvio de Verba):** O notebook levanta a questão de um possível desvio de verba, dado que o maior volume de gastos está em cargos que não podem ser identificados, comprometendo o rastreamento do dinheiro público.
* **Cargos com Despesas:** O restante do ranking de despesas é preenchido por cargos com viagens frequentes, como `PROFESSOR DO MAGISTERIO SUPERIOR`.

## 🚀 Como Rodar o Projeto

1.  **Clonar o Repositório:**
    ```bash
    git clone [https://www.youtube.com/shorts/3mMG25WHLkU](https://www.youtube.com/shorts/3mMG25WHLkU)
    cd [nome do seu repositório]
    ```
2.  **Obter o Dataset:**
    * Baixe o arquivo `2024_Viagem.csv` da fonte oficial de dados abertos do Governo Federal.
    * Coloque o arquivo na estrutura de pastas esperada pelo notebook (conforme a variável `trip` no primeiro bloco de código). **Nota:** Se estiver usando o Colab, será necessário adaptar o caminho.
3.  **Executar o Notebook:**
    * Abra o arquivo `GovBR_Dataset_viagem.ipynb` no Jupyter Notebook, JupyterLab, ou no Google Colab.
    * Execute as células sequencialmente para replicar a análise e gerar os gráficos.
