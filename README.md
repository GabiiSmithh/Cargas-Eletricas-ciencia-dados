# Projeto de Ciência de Dados — Carga de Energia Elétrica

## Sobre o projeto

Este projeto tem como objetivo preparar e integrar dados de carga de energia elétrica do subsistema Sul do Brasil, disponibilizados pelo **ONS**, com dados meteorológicos do **INMET**, considerando o período de 2000 a 2025.

A base contempla informações diárias de carga elétrica, temperatura, umidade relativa do ar, precipitação e calendário (dias úteis, finais de semana e feriados nacionais).

## Preparando o ambiente (Windows)

- Instale o Python 3 caso ainda não esteja instalado. Utilize a versão **3.13**.
- No Visual Studio Code, instale as extensões:
  - Python — Microsoft;
  - Jupyter — Microsoft.
- Execute o comando abaixo para verificar a versão instalada:

```bash
py --version
```

- Crie o ambiente virtual na pasta do projeto:

```bash
py -3.13 -m venv .venv
```

- Ative o ambiente virtual:

```powershell
.\.venv\Scripts\Activate.ps1
```

- Com o ambiente ativado, atualize o pip:

```bash
python -m pip install --upgrade pip
```

- Instale as dependências utilizadas no projeto:

```bash
pip install pandas numpy pyarrow holidays openpyxl jupyter ipykernel matplotlib duckdb scipy statsmodels
```

- Pressione `Ctrl + Shift + P`, pesquise `Python: Select Interpreter` e selecione o interpretador correspondente ao ambiente `.venv` (Python 3.13).

- Ao abrir o notebook, selecione o kernel correspondente ao ambiente virtual criado.

## Notebooks

Execute na ordem abaixo:

1. `notebooks/integracao.ipynb`: integra os dados do ONS, do INMET e do calendário e gera `dados/processados/ons_projeto_integrado.parquet`.
2. `notebooks/analise_exploratoria.ipynb`: consultas SQL (DuckDB), análise exploratória, testes das hipóteses H1 (clima) e H2 (calendário) e implicações para a modelagem, com o recorte de 2021 a 2025.

## Observação

Os dados originais do ONS e do INMET não estão disponíveis neste repositório devido ao grande volume de arquivos. Para executar o processamento, é necessário disponibilizá-los nas respectivas pastas `dados/ONS` e `dados/INMET`.

Esses dados estão disponíveis no relatório.
