# PowerBI---Exporta-es
📊 Dashboard de Exportações Globais
✅ Descrição
Este projeto apresenta um dashboard interativo desenvolvido no Power BI para análise de exportações globais. Ele inclui:

Mapa geográfico preenchido mostrando intensidade das exportações por país.
Ranking dos Top 10 países exportadores.
Filtros interativos por Ano e Continente.
Medidas DAX para cálculos dinâmicos (quantidade total, ranking, percentual e Top 10).


🛠 Tecnologias Utilizadas

Power BI Desktop
DAX (Data Analysis Expressions)
Excel (Base de dados)


📂 Estrutura do Repositório
📂 PowerBI-Exportacoes
 ├── 📄 README.md
 ├── 📄 Exportacoes.pbix
 ├── 📂 Dados
 │    └── BasedeDadosTechChalengev2.xlsx
 ├── 📂 Imagens
 │    └── dashboard-preview.png
 ├── 📂 DAX
 │    └── medidas.txt


🔍 Funcionalidades

Mapa Preenchido (Filled Map) com escala de cores (Amarelo → Vermelho).
Gráfico de Barras Horizontal com Top 10 países.
Segmentadores para Ano e Continente.
Medidas DAX:

TotalQuantidadeExportada
RankingExportacao
PercentualExportacao
Top10Exportacao




📐 Medidas DAX
DAXTotalQuantidadeExportada =CALCULATE(    SUM('Exportacao'[TotalQuantidade]),    FILTER('Exportacao', 'Exportacao'[Coluna1] = "Ok!" && 'Exportacao'[Ano] >= 2000))RankingExportacao =RANKX(    ALL('Exportacao'[País Corrigido]),    CALCULATE(SUM('Exportacao'[TotalQuantidade]), FILTER('Exportacao', 'Exportacao'[Coluna1] = "Ok!" && 'Exportacao'[Ano] >= 2000)),    ,    DESC,    DENSE)PercentualExportacao =DIVIDE(    [TotalQuantidadeExportada],    CALCULATE(SUM('Exportacao'[TotalQuantidade]), FILTER('Exportacao', 'Exportacao'[Coluna1] = "Ok!" && 'Exportacao'[Ano] >= 2000)),    0)Top10Exportacao =IF([RankingExportacao] <= 10, [TotalQuantidadeExportada], BLANK())Mostrar mais linhas

🖼 Preview do Dashboard
!Dashboard Preview

🚀 Como usar

Baixe o arquivo .pbix.
Abra no Power BI Desktop.
Explore os filtros e visuais interativos.


📢 Contribuição
Sinta-se à vontade para abrir issues ou enviar pull requests com melhorias.
