# Trajetória da dívida pública brasileira

## Objetivo

Desenvolver um projeto de portfólio para descrever a trajetória da dívida pública brasileira e investigar os fatores condicionantes de suas variações, aprendendo e documentando a lógica de cada etapa. A análise explicativa partirá da decomposição contábil publicada pelo Banco Central, respeitando os limites de interpretação causal.

## Pergunta central

“Como a Dívida Bruta do Governo Geral (DBGG) evoluiu entre 2023 e o último mês disponível de 2026, e quais fatores contribuíram para suas variações?”

## Período

De janeiro de 2023 até o último mês divulgado de 2026, com frequência mensal. A última competência disponível será identificada após a validação das séries; quando a cobertura não alcançar dezembro, 2026 será apresentado como ano parcial.

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

Valores em reais correntes não descontam a inflação; sua evolução e a relação dívida/PIB serão interpretadas como medidas distintas. Dados observados serão separados de hipóteses, e lacunas ou diferenças de cobertura serão documentadas. Não há, nesta etapa, códigos de séries validados, valores coletados ou resultados de análise.

## Ferramentas

- Python para o desenvolvimento da análise.
- Jupyter para apresentar o raciocínio e os resultados.
- pandas para organizar e tratar os dados.
- Plotly para criar visualizações interativas.
- Git para acompanhar as alterações do projeto.

## Situação atual e próxima etapa

O indicador principal, a fonte, a frequência e as medidas foram definidos. O escopo inclui a trajetória e os fatores condicionantes da DBGG, com distinção entre descrição, decomposição contábil e investigação causal.

A próxima etapa será identificar e validar as séries oficiais antes da coleta, registrando códigos, unidades, periodicidade e cobertura temporal. Essa validação deverá confirmar a correspondência das séries com o indicador, as medidas e os fatores condicionantes escolhidos, além da última competência disponível de 2026.

Não há dados coletados, notebooks ou código de análise, e nenhuma dependência foi instalada nesta etapa.

O trabalho será realizado em pequenas entregas, com explicações claras e objetivas. Código de análise será implementado apenas quando solicitado. A decisão sobre quais dados serão versionados será tomada posteriormente.
