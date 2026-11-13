# Dashboard de Vendas de Bicicletas (Excel)

Dashboard em Excel que explora quais fatores demográficos e financeiros
estão associados à decisão de comprar uma bicicleta.

![Dashboard](imagens/dashboard.png)

> **Observação:** este é um projeto de aprendizado. Segui o tutorial
> [Full Project in Excel](https://www.youtube.com/watch?v=opJgMj1IUrc),
> do Alex The Analyst, e documentei aqui o processo e o meu entendimento.

## Problema de negócio

A base (`bike_buyers`) tem uma linha por cliente, com estado civil, gênero,
renda, quantidade de filhos, escolaridade, ocupação, posse de imóvel,
quantidade de carros, distância de deslocamento, região, idade e se o
cliente comprou ou não uma bicicleta.

**Pergunta:** quais fatores mais se associam à compra de uma bicicleta,
para direcionar melhor campanhas futuras de marketing e vendas?

## Estrutura da pasta de trabalho

| Aba | Função |
|---|---|
| `bike_buyers` | Dados originais, mantidos intactos como backup |
| `Working Sheet` | Cópia dos dados, onde foram feitas a limpeza e a criação de colunas |
| `Pivot Table` | Tabelas dinâmicas e gráficos dinâmicos que alimentam o dashboard |
| `Dashboard` | Visão final e interativa |

*Os nomes das abas estão em inglês, como no arquivo original.*

## Limpeza dos dados

- Remoção de registros duplicados (pelo ID)
- Padronização de categorias: `M`/`S` → `Married`/`Single` e `M`/`F` → `Male`/`Female`
- Revisão de ortografia e consistência, incluindo a categoria `10+ Miles`, para que ela ordene corretamente nos gráficos
- Formatação da coluna `Income` (renda) como moeda, sem casas decimais
- Criação da coluna `Age Brackets` (faixas etárias) com a função `SE` aninhada: `Adolescent` (abaixo de 31 anos), `Middle-age` (31 a 54 anos) e `Old` (55 anos ou mais)

## Análise e dashboard

Três tabelas dinâmicas com seus gráficos:

1. **Renda média por gênero × compra de bicicleta** (gráfico de colunas)
2. **Distância de deslocamento × compra de bicicleta** (gráfico de linhas)
3. **Faixa etária × compra de bicicleta** (gráfico de linhas com marcadores)

Três segmentações de dados (slicers) conectadas a todas as tabelas
dinâmicas: **Marital Status** (estado civil), **Region** (região) e
**Education** (escolaridade).

## Principais resultados

- Em ambos os gêneros, quem comprou bicicleta tem renda média maior.
- As compras tendem a cair conforme a distância de deslocamento aumenta; as menores distâncias (0–1 e 1–2 milhas) concentram mais compradores.
- O grupo de meia-idade (31 a 54 anos) é o único com mais compradores do que não compradores.

**Perfil com maior tendência de compra:** pessoas de meia-idade, com renda média mais elevada e que moram relativamente perto do trabalho.

## Limitações

- Os dados mostram associações, não causas.
- A análise é descritiva: não foram aplicados testes estatísticos.
- O dashboard é uma entrega da análise; não medi nenhum impacto no negócio.
- O projeto usa a base e a estrutura de um tutorial.

## Como conferir

Baixe o arquivo `dashboard_vendas_bicicletas.xlsx` e abra no Excel. Na aba
`Dashboard`, use as segmentações de dados para filtrar todos os gráficos
ao mesmo tempo.

## Ferramentas

Microsoft Excel: fórmulas condicionais, limpeza de dados, tabelas dinâmicas,
gráficos dinâmicos e segmentações de dados.

## Próximos passos

- Refazer a análise no Power BI
- Responder às mesmas perguntas com SQL
