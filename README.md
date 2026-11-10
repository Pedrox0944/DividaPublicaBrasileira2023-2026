# Trajetória da dívida pública brasileira

## Objetivo

Desenvolver um projeto de portfólio para descrever a trajetória da dívida pública brasileira e investigar os fatores condicionantes de suas variações, aprendendo e documentando a lógica de cada etapa. A análise explicativa partirá da decomposição contábil publicada pelo Banco Central, respeitando os limites de interpretação causal.

## Pergunta central

“Como a Dívida Bruta do Governo Geral (DBGG) evoluiu entre 2023 e o último mês disponível de 2026, e quais fatores contribuíram para suas variações?”

## Período

De janeiro de 2023 até o último mês divulgado de 2026, com frequência mensal. A última competência é verificada por fonte: para as séries de saldo, a consulta de 10/11/2026 retornou setembro de 2026; o XLSX atual dos fatores também contém dados até setembro de 2026. Portanto, 2026 é tratado como ano parcial nesta consulta.

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

Valores em reais correntes não descontam a inflação; sua evolução e a relação dívida/PIB serão interpretadas como medidas distintas. Dados observados serão separados de hipóteses, e lacunas ou diferenças de cobertura serão documentadas. As séries SGS 13762 (% do PIB) e 13761 (milhões de reais correntes) tiveram os 45 meses de janeiro de 2023 a setembro de 2026 verificados e comparados aos saldos da planilha dos fatores, respeitando a precisão publicada. Ainda não há base final organizada nem resultados da análise.

## Ferramentas

- Python para o desenvolvimento da análise.
- Jupyter para apresentar o raciocínio e os resultados.
- pandas para organizar e tratar os dados.
- Plotly para criar visualizações interativas.
- Git para acompanhar as alterações do projeto.

## Situação atual e próxima etapa

O indicador principal, a fonte, a frequência e as medidas foram definidos. O escopo inclui a trajetória e os fatores condicionantes da DBGG, com distinção entre descrição, decomposição contábil e investigação causal.

O [mapeamento de fontes e séries](fontes-e-series.md), consultado em 10/11/2026, está **suficiente para a primeira entrega mensal**, com ressalvas documentadas. Isso não equivale à validação completa de todas as apresentações da fonte.

As séries SGS 13761 e 13762 retornaram os 45 meses de janeiro de 2023 a setembro de 2026, sem ausências, duplicações, competências extras ou valores inválidos. As competências coincidem com as da aba mensal dos fatores; os 90 saldos comparados coincidem ao arredondar a planilha para as duas casas publicadas pelo SGS. Os valores originais foram preservados. Consultas com datas fixas podem retornar valores revisados, por isso os links, a data e os hashes das respostas foram registrados.

O ambiente isolado já disponível usa Python 3.13.16 e `xlrd` 2.0.2 na `.venv`, ignorada pelo Git. Sua preparação serviu à validação do XLS e não configura o ambiente completo de análise. O XLS legado termina em novembro de 2018; a fonte mensal adequada é o [Facdbp.xlsx atual de Tabelas Especiais](https://www.bcb.gov.br/content/estatisticas/Documents/Tabelas_especiais/Facdbp.xlsx), inspecionado com bibliotecas padrão do Python.

Além da conciliação de setembro de 2026 já documentada, foram conferidas as identidades dos componentes independentes nos 45 meses, com resíduos registrados. O denominador da relação dívida/PIB é o PIB acumulado em 12 meses a preços correntes (SGS 4382). Fatores como proporção do PIB não serão apresentados como variação da razão sem considerar o efeito separado do denominador.

A chamada de nota em reconhecimento de dívidas permanece inconsistente e não foi localizada errata oficial. O manual e a aba mensal `Rec Div` do detalhamento oficial sustentam o uso do **agregado conforme publicado pelo BCB**, com ressalva: seus totais são compatíveis com os da planilha principal nos 45 meses, mas não serão atribuídos a operações ou causas específicas sem novas evidências. Essa incerteza não bloqueia o uso descritivo do agregado mensal.

A primeira entrega usará os saldos e os componentes mensais selecionados, mantendo o ajuste cambial agregado e evitando dupla contagem de subtotais. **Acumulados no ano e subcomponentes ficam fora do escopo inicial; suas convenções não foram validadas integralmente.** As pendências futuras estão separadas das verificações essenciais no documento de fontes.

Podemos iniciar a coleta dos saldos e fatores mensais de janeiro de 2023 a setembro de 2026, sem bloqueio de dados identificado para esse escopo, preservando as versões obtidas e repetindo os controles após revisões. Consultar dezembro de 2022 apenas como referência para calcular a variação de janeiro de 2023 continua proposta pendente de decisão. Nesta inspeção, janeiro foi conferido com a variação já publicada, sem calcular diferença com dezembro de 2022.

Foram executados apenas trechos de inspeção e validação no ambiente existente. As respostas e planilhas ficaram em pasta temporária; não foi montada a base final, implementado pipeline definitivo ou criado notebook. Não houve nova instalação nesta tarefa. A decisão sobre versionamento de dados será tomada posteriormente.

O trabalho será realizado em pequenas entregas, com explicações claras e objetivas. Código de análise será implementado apenas quando solicitado. A decisão sobre quais dados serão versionados será tomada posteriormente.
