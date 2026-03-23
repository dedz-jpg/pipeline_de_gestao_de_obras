# Pipeline de Dados para Gestão de Obras

Projeto completo de engenharia e análise de dados utilizando Excel, Python, MySQL e Power BI.

O objetivo é automatizar o tratamento de dados de obras e gerar insights sobre prazos, atrasos e desempenho dos empreendimentos.

# Objetivos: 

- Automatizar o tratamento de dados de obras
- Construir um pipeline de ETL para padronização das informações
- Disponibilizar dashboards interativos para análise gerencial

## Tecnologias utilizadas

- Excel (fonte de dados)
- Python (Pandas, Pathlib)
- MySQL (armazenamento e modelagem)
- Power BI (visualização e análise)

## Arquitetura do Pipeline

Excel → Python → MySQL → Power BI

![Dashboard de Gestão de Obras](images/dash_gestao.png)

Principais análises:
- Acompanhamento de prazos
- Identificação de atrasos
- Visão geral dos empreendimentos

## Pipeline de Dados

![Pipeline de Dados](images/pipeline_de_dados.jpg)

1. Extração dos dados a partir do Excel
2. Tratamento e padronização com Python
3. Carga dos dados no MySQL
4. Consumo dos dados no Power BI.

## Regras de Negócio

- Cálculo de atraso em meses com base na data prevista
- Classificação de obras em:
  - No prazo
  - Em risco
  - Em atraso
 
## Diferenciais do Projeto

- Estruturação de pipeline ETL
- Uso de banco relacional (MySQL) em vez de Excel como base final
- Separação entre dados brutos e tratados
- Automação do processo de atualização

## Estrutura do Projeto

├── data/
├── src/
├── sql/
├── powerbi/
└── README.md

## Como executar

1. Atualizar o arquivo Excel
2. Rodar o script Python
3. Atualizar o Power BI


## Resultados:

- Automatização de processos
- Redução de erros
- Controle do histórico de dados
- Dashboard atualizado automaticamente

## Melhorias futuras

- Deploy do pipeline em ambiente cloud (AWS)
- Automação do processo via agendamento (scheduler)
- Integração com banco de dados relacional
- Criação de API para consumo dos dados
