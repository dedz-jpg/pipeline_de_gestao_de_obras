PT-BR Version

# Pipeline de Dados para Gestão de Obras

Projeto de engenharia e análise de dados com foco em automação de processos e geração de insights.

## Tecnologias utilizadas

- Excel (fonte de dados)
- Python (Pandas, Pathlib)
- MySQL (armazenamento - em evolução)
- Power BI (visualização)

---

## Objetivo

- Automatizar o tratamento de dados de obras  
- Construir um pipeline de ETL para padronização das informações  
- Disponibilizar dashboards interativos para análise gerencial  

---

## Arquitetura do Pipeline

Excel → Python → MySQL → Power BI  

---

## Dashboard

![Dashboard de Gestão de Obras](images/dash_gestao.png)

**Principais análises:**
- Acompanhamento de prazos  
- Identificação de atrasos  
- Visão geral dos empreendimentos  

---

## Pipeline de Dados

![Pipeline de Dados](images/pipeline_de_dados.jpg)

**Etapas do processo:**

1. Leitura dos dados a partir do Excel  
2. Tratamento e padronização com Python  
3. Geração de base tratada  
4. Consumo dos dados no Power BI  

---

## Regras de Negócio

- Cálculo de atraso em meses com base na data prevista  
- Classificação das obras em:  
  - No prazo  
  - Em risco  
  - Em atraso  

---

## Diferenciais

- Pipeline ETL estruturado  
- Automação do tratamento de dados  
- Aplicação de regras de negócio  
- Integração entre Excel, Python e Power BI  

---

## Estrutura do Projeto

├── data/
├── src/
├── sql/
├── powerbi/
└── README.md


---

## Como executar

1. Atualizar o arquivo Excel  
2. Rodar o script Python  
3. Atualizar o Power BI  

---

## Resultados

- Automatização de processos  
- Redução de erros  
- Controle do histórico de dados  
- Dashboard atualizado automaticamente  

---

## Melhorias futuras

- Deploy do pipeline em ambiente cloud (AWS)  
- Automação via agendamento (scheduler)  
- Integração completa com banco de dados relacional  
- Criação de API para consumo dos dados

---

ENG - Version: 

# Data Pipeline for Construction Project Management

A data engineering and analytics project focused on process automation and insight generation.

## Technologies Used

- Excel (data source)
- Python (Pandas, Pathlib)
- MySQL (storage – in progress)
- Power BI (visualization)

---

## Objective

- Automate the processing of construction project data  
- Build an ETL pipeline to standardize information  
- Provide interactive dashboards for managerial analysis  

---

## Pipeline Architecture

Excel → Python → MySQL → Power BI  

---

## Dashboard

![Construction Management Dashboard](images/dash_gestao.png)

**Key insights:**
- Schedule tracking  
- Delay identification  
- Overall project overview  

---

## Data Pipeline

![Data Pipeline](images/pipeline_de_dados.jpg)

**Process steps:**

1. Extract data from Excel  
2. Transform and standardize data using Python  
3. Generate a clean dataset  
4. Load and visualize data in Power BI  

---

## Business Rules

- Delay calculation in months based on the planned delivery date  
- Project classification into:  
  - On schedule  
  - At risk  
  - Delayed  

---

## Key Features

- Structured ETL pipeline  
- Automated data processing  
- Business rule implementation  
- Integration between Excel, Python, and Power BI  

---

## Project Structure

├── data/
├── src/
├── sql/
├── powerbi/
└── README.md


---

## How to Run

1. Update the Excel file  
2. Run the Python script  
3. Refresh the Power BI dashboard  

---

## Results

- Process automation  
- Error reduction  
- Historical data tracking  
- Automatically updated dashboard  

---

## Future Improvements

- Deploy the pipeline in a cloud environment (AWS)  
- Automate execution using a scheduler  
- Full integration with a relational database  
- API development for data consumption  
