o codigo que usei foi:

## Objetivo: 
    # Atualizar a base de dados de obras com as informações mais recentes disponíveis.
    # A BASE - EMPREENDIMENTO será o arquivo raiz para que possa surgir as conferências necessárias para a atualização.
    # Quando eu atualizar a BASE - EMPREENDIMENTO, as outras bases serão atualizadas automaticamente, pois elas estão vinculadas a ela.
    # Eu rodo as atualizações da BASE toda sexta-feira. 
    # Após atualização da BASE - EMPREENDIMENTO, eu gero um relatório de conferência para verificar se as atualizações foram realizadas corretamente.
    # Se estiver tudo certo, eu anexo no e-mail de envio do Dash Corporativo para que haja uma transparência referente as obras no mês de análise. 
    # Pandas é uma biblioteca de código aberto para análise de dados em Python. Ela fornece estruturas de dados e funções para manipulação e análise de dados de forma eficiente. 
    # Pathlib é uma biblioteca padrão do Python para manipulação de caminhos de arquivos e diretórios. Ela fornece uma interface orientada a objetos para trabalhar com caminhos, facilitando a criação, leitura, escrita e manipulação de arquivos e diretórios de forma mais intuitiva e legível.

import pandas as pd
from pathlib import Path

arquivo_base = Path(r"Z:\Op_Int_Negocios\00_Base de Dados\01_Base Geral\2026.03\BASE - EMPREENDIMENTO.xlsx")
arquivo_saida = Path(r"Z:\Op_Int_Negocios\12_Estudos\Acompanhamento semanal de obras.xlsx")
nome_aba = "BASE"

df = pd.read_excel(arquivo_base, sheet_name=nome_aba, header=4)
df.columns = df.columns.astype(str).str.strip()

# confira os nomes exatos no Excel
col_obra = "OBRA"
col_plan_perc = "MENSAL - PLAN - %OBRA"
col_real_perc = "MENSAL - REAL - %OBRA"
col_aderencia = "ADERÊNCIA - PREVISON"
col_prev_ult_med = "PREVISION - ULTIMA MEDIÇÃO"

# manter apenas linhas com obra
df = df[df[col_obra].notna()].copy()

# tratar colunas numéricas
colunas_numericas = [
    col_plan_perc,
    col_real_perc,
    col_aderencia
]

for col in colunas_numericas:
    df[col] = (
        df[col]
        .astype(str)
        .str.replace("%", "", regex=False)
        .str.replace(",", ".", regex=False)
        .str.strip()
    )
    df[col] = pd.to_numeric(df[col], errors="coerce")

# tratar data
df[col_prev_ult_med] = pd.to_datetime(df[col_prev_ult_med], errors="coerce")

# manter apenas colunas relevantes
colunas_saida = [
    col_obra,
    col_plan_perc,
    col_real_perc,
    col_aderencia,
    col_prev_ult_med
]

df_base_tratada = df[colunas_saida].copy()

# exportar
with pd.ExcelWriter(arquivo_saida, engine="openpyxl", mode="w") as writer:
    df_base_tratada.to_excel(writer, sheet_name="Base Tratada", index=False)

print(f"Planilha atualizada com sucesso em: {arquivo_saida}")
