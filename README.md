1. Extração
2. import pandas as pd

# Leitura de arquivo CSV
url = "https://exemplo.com/dados.csv"
dados = pd.read_csv(url)

# Visualizando os primeiros registros
print(dados.head())

2. Transformação

3. # Conversão de coluna para datetime
dados['data'] = pd.to_datetime(dados['data'])

# Removendo duplicatas
dados.drop_duplicates(inplace=True)

# Criando uma nova coluna: vendas totais
dados['vendas_totais'] = dados['quantidade'] * dados['preco_unitario']

# Verificando as mudanças
print(dados.info())
print(dados.head())

. Carga e Análise

import matplotlib.pyplot as plt
import seaborn as sns

# Distribuição das vendas totais
sns.histplot(dados['vendas_totais'], bins=20, kde=True)
plt.title("Distribuição das Vendas Totais")
plt.xlabel("Vendas Totais")
plt.ylabel("Frequência")
plt.show()

# Agregação: vendas por produto
vendas_por_produto = dados.groupby('produto')['vendas_totais'].sum().reset_index()
print(vendas_por_produto)
4. Relatório Final
Ferramentas Utilizadas
Categoria	Ferramentas
Linguagem	Python (pandas, matplotlib, seaborn)
Banco de Dados	MySQL, PostgreSQL
Planilhas	Excel, Google Sheets
BI e Dashboards	Power BI, Tableau



