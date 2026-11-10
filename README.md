# Trajetória da dívida pública brasileira

## Objetivo

Desenvolver um projeto de portfólio para descrever a trajetória da dívida pública brasileira e investigar os fatores condicionantes de suas variações, aprendendo e documentando a lógica de cada etapa. A análise explicativa partirá da decomposição contábil publicada pelo Banco Central, respeitando os limites de interpretação causal.

## Pergunta central

“Como a Dívida Bruta do Governo Geral (DBGG) evoluiu entre 2023 e o último mês disponível de 2026, e quais fatores contribuíram para suas variações?”

## Período

De janeiro de 2023 até o último mês divulgado de 2026, com frequência mensal. A última competência é verificada por fonte: para as séries de saldo, a consulta de 10/11/2026 retornou setembro de 2026; a cobertura dos fatores ainda não foi confirmada; quando a cobertura não alcançar dezembro, 2026 será apresentado como ano parcial.

## Indicador e fonte

- **Indicador principal:** Dívida Bruta do Governo Geral (DBGG), segundo a metodologia do Banco Central.
- **Fonte principal:** Banco Central do Brasil (BCB).
- **Frequência:** mensal.
- **Medidas:** valor nominal em reais correntes e relação dívida/PIB, expressa em percentual.

A DBGG abrange diferentes esferas de governo, incluindo os governos federal, estaduais e municipais, conforme a metodologia do BCB. Sua variação não será atribuída automaticamente ao presidente da República.

### Referência metodológica

[Manual de Estatísticas Fiscais do Banco Central](https://www.bcb.gov.br/content/estatisticas/Documents/notas_metodologicas/estatisticas-fiscais/estatisticasfiscais.pdf).

## Análise explicativa e rigor metodológico

Serão investigados os fatores condicionantes publicados pelo Banco Central, como juros, emissões e resgates líquidos, efeitos cambiais, efeito do PIB nominal sobre a relação dívida/PIB e demais ajustes. A classificação definitiva, as unidades e a aplicação de cada fator às medidas escolhidas dependerão da documentação oficial da base.

O projeto distinguirá três níveis de análise:

- **Descrição:** apresentar a evolução observada da DBGG e suas variações mensais.
- **Decomposição contábil:** examinar quanto cada fator condicionante contribui para a variação, segundo as definições e identidades contábeis do BCB.
- **Investigação causal:** avaliar hipóteses sobre efeitos de políticas ou eventos, o que exige método e evidências adicionais à decomposição contábil. Nenhuma conclusão causal será tratada como resultado automático dessa decomposição.

A contribuição contábil de um fator não prova o efeito causal de uma política específica. A análise dos episódios distinguirá dados observados, hipóteses explicativas e evidências que sustentem cada interpretação.

## Entregas planejadas

- Gráfico da trajetória mensal da DBGG em reais correntes e em percentual do PIB.
- Gráficos das contribuições dos fatores condicionantes, conforme a disponibilidade e a classificação oficial das séries.
- Análise contextualizada dos principais episódios, com fontes e limites das interpretações apresentados explicitamente.

## Limitações e transparência

A última competência disponível e a cobertura de cada série serão informadas nas entregas. Comparações que incluam 2026 considerarão seu caráter parcial, quando aplicável, sem tratar meses ainda não divulgados como dados observados.

Valores em reais correntes não descontam a inflação; sua evolução e a relação dívida/PIB serão interpretadas como medidas distintas. Dados observados serão separados de hipóteses, e lacunas ou diferenças de cobertura serão documentadas. As séries SGS 13762 (% do PIB) e 13761 (milhões de reais correntes) foram identificadas e validadas por metadados e amostras pontuais. Ainda não há base completa coletada nem resultados de análise.

## Ferramentas

- Python para o desenvolvimento da análise.
- Jupyter para apresentar o raciocínio e os resultados.
- pandas para organizar e tratar os dados.
- Plotly para criar visualizações interativas.
- Git para acompanhar as alterações do projeto.

## Situação atual e próxima etapa

O indicador principal, a fonte, a frequência e as medidas foram definidos. O escopo inclui a trajetória e os fatores condicionantes da DBGG, com distinção entre descrição, decomposição contábil e investigação causal.

O [mapeamento de fontes e séries](fontes-e-series.md), consultado em 10/11/2026, está **parcial**. As séries SGS 13762 e 13761 foram confirmadas como mensais, com início em dezembro de 2006 e última observação retornada em setembro de 2026. As quatro amostras foram reconfirmadas com consultas de datas fixas, que também podem retornar valores revisados. A continuidade de todos os meses ainda será verificada. O denominador da fórmula da SGS 13762 foi identificado como PIB acumulado em 12 meses a preços correntes (SGS 4382).

O ZIP oficial dos fatores foi baixado novamente, mas a leitura das células está **bloqueada pela ausência de leitor XLS** no ambiente. Não houve instalação de dependências. Para prosseguir, será necessário `xlrd` ou LibreOffice. Não foram confirmadas a primeira e a última competência dos fatores, a cobertura de 2023–2026, os componentes, suas unidades, sinais e hierarquia, nem a conciliação pontual. Foram investigadas rotas alternativas oficiais, sem validar um arquivo atualizado. Os rótulos anteriormente extraídos permanecem candidatos.

A próxima etapa será resolver essas verificações antes da coleta completa. O período principal permanece janeiro de 2023 até o último mês disponível de 2026; setembro de 2026 foi confirmado para os saldos, mas ainda não para os fatores. Consultar dezembro de 2022 apenas como referência para calcular a variação de janeiro de 2023 continua como proposta pendente de decisão.

Foram consultados metadados, pequenas amostras oficiais e o arquivo dos fatores para verificação. Não foi montada a base completa, não foram criados scripts de coleta, notebooks ou código de análise, e nenhuma dependência foi instalada nesta etapa.

O trabalho será realizado em pequenas entregas, com explicações claras e objetivas. Código de análise será implementado apenas quando solicitado. A decisão sobre quais dados serão versionados será tomada posteriormente.
