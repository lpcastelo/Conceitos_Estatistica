# Conceitos de Estatística — Análise de Preços de Supermercado

Projeto do módulo 13 do curso de Cientista de Dados da Ebac, aplicando conceitos de estatística descritiva e visualização de dados sobre uma base real de produtos de supermercado.

## Objetivo

Explorar estatisticamente os preços de produtos de uma rede de supermercados chilena, identificando o comportamento de médias, medianas e dispersão por categoria, além de padrões de desconto entre categorias e marcas.

## Dados

Base de produtos de um supermercado chileno (`MODULO7_PROJETOFINAL_BASE_SUPERMERCADO.csv`), com as colunas:

- **Title** — nome do produto
- **Marca** — marca do produto
- **Categoria** — categoria do produto (rótulos em espanhol)
- **Preco_Normal** — preço sem desconto
- **Preco_Desconto** — preço após desconto
- **Preco_Anterior** — preço antes do desconto ser aplicado
- **Desconto** — valor total do desconto aplicado

## Etapas realizadas

1. **Leitura dos dados** com pandas a partir do CSV.
2. **Estatística descritiva por categoria**: cálculo de média, mediana e desvio padrão de `Preco_Normal`, identificando categorias com maior dispersão.
3. **Tratamento de dados**: identificado que valores `0` em `Preco_Normal` na verdade indicam produtos com desconto, cujo preço real estava em `Preco_Anterior`. As duas colunas foram unificadas em `Preco_Unificado`, e os produtos sem nenhum preço válido foram removidos da análise.
4. **Análise de outliers**: boxplots da categoria de maior desvio padrão (antes e depois do tratamento de dados), confirmando forte assimetria na distribuição de preços.
5. **Visualização de descontos**: gráfico de barras com a média de desconto por categoria.
6. **Visualização interativa**: treemap (Plotly) cruzando categoria e marca pela média de desconto.

## Principais resultados

- Categorias com maior desvio padrão apresentam maior discrepância entre média e mediana, indicando distribuições assimétricas com presença de outliers.
- O tratamento do valor `0` (convenção de dados da fonte, não preço real) alterou média, mediana e desvio padrão de praticamente todas as categorias, mostrando o impacto de um problema de qualidade de dados não tratado na análise estatística.
- Mesmo após o tratamento, a distribuição de preços segue fortemente assimétrica, com diversos outliers.

## Tecnologias

- Python
- pandas
- matplotlib
- plotly

## Como executar

1. Clone o repositório.
2. Instale as dependências: `pip install pandas matplotlib plotly`.
3. Coloque o arquivo `MODULO7_PROJETOFINAL_BASE_SUPERMERCADO.csv` no mesmo diretório do notebook (ou ajuste o caminho na célula de leitura).
4. Execute `Profissao Cientista de Dados M13 Projeto.ipynb` em ordem.
