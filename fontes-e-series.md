# Fontes e séries da dívida pública brasileira

Consulta: **10/11/2026**, horário de referência America/Fortaleza. Estado: **mapeamento parcial; validação dos fatores condicionantes pendente**.

## Escopo e critérios

O período principal é janeiro de 2023 a setembro de 2026, última competência retornada nas consultas pontuais das duas séries SGS nesta data. A cobertura dos fatores ainda não foi confirmada; portanto, esse término não se aplica automaticamente à decomposição. 2026 será tratado como ano parcial. Consultar dezembro de 2022 apenas como referência para calcular a variação de janeiro de 2023 é uma **proposta pendente de decisão**.

Metadados são informações que descrevem os dados: conceito, unidade, frequência, cobertura e método. Conferi-los antes da coleta evita juntar medidas incompatíveis ou interpretar um acumulado como movimento mensal. Nesta etapa foram consultados metadados, duas observações por série e o pequeno arquivo oficial dos fatores; não foi construída uma base de análise.

## 1. DBGG em percentual do PIB — SGS 13762

- **Nome oficial:** Dívida bruta do governo geral (% PIB) - Metodologia utilizada a partir de 2008.
- **Responsável:** Banco Central do Brasil. O catálogo indica BCB/Depec; os dados básicos atuais do SGS indicam BCB-DSTAT e gestão DSTAT/DIFIN/SUFIP. Registram-se as duas atribuições conforme cada fonte.
- **Acesso e documentação:** [catálogo oficial](https://dadosabertos.bcb.gov.br/dataset/13762-divida-bruta-do-governo-geral--pib---metodologia-utilizada-a-partir-de-2008), [metadados SGS](https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&hdOidSerieSelecionada=13762) e [Manual de Estatísticas Fiscais, maio de 2019](https://www.bcb.gov.br/content/estatisticas/Documents/notas_metodologicas/estatisticas-fiscais/estatisticasfiscais.pdf), especialmente seções 4.3 e 5.
- **Definição e abrangência:** endividamento bruto dos governos federal, estaduais e municipais, incluindo compromissadas do BCB; exclui dívidas das empresas estatais. A metodologia consolida obrigações entre entes abrangidos e converte obrigações externas pelo câmbio de fim de período. Não equivale à DLSP nem apenas à dívida federal.
- **Unidade e natureza:** percentual do PIB; relação entre saldo de dívida e PIB, não fluxo. A fórmula exibida no SGS utiliza `SERIE(13741) / SERIE(4382)*100` para o período relevante. Esses códigos são referências da fórmula oficial, não novas séries selecionadas para coleta.
- **Frequência e cobertura:** mensal; início em dezembro de 2006, confirmado no cadastro e na amostra inicial; última observação retornada: setembro de 2026. O nome “a partir de 2008” identifica a metodologia e não a primeira competência.
- **Formatos e acesso previsto:** catálogo oferece JSON, CSV, SOAP/WSDL e visualização HTML. Para uma futura coleta, preferir BCData/SGS em JSON ou CSV com intervalo explícito, após autorização.
- **Evidências:** [amostra inicial CSV](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13762/dados?formato=csv&dataInicial=01/12/2006&dataFinal=31/12/2006) retornou `01/12/2006;55,48`; [última observação JSON](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13762/dados/ultimos/1?formato=json) retornou `01/09/2026`, valor `82.93`. A data representa a competência mensal.
- **Limite:** a continuidade de todos os meses de 2023–2026 ainda não foi auditada. A atualização dos metadados do catálogo em 08/09/2026 não foi usada como data do último dado.

## 2. DBGG nominal — SGS 13761 confirmada

- **Nome oficial exibido pelo SGS na sessão em inglês:** “Gross general government debt - Balances in reais (million) - Method used since 2008”. Tradução descritiva: dívida bruta do governo geral, saldos em milhões de reais, metodologia utilizada a partir de 2008.
- **Responsável:** Banco Central do Brasil, Departamento de Estatísticas (BCB-DSTAT; DSTAT/DIFIN/SUFIP).
- **Documentação:** [metadados e dados básicos SGS 13761](https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&hdOidSerieSelecionada=13761) e manual acima. Os painéis internos exigiram cookies da sessão; abrir primeiro o endereço principal do SGS. Os dados básicos e o painel de metadados confirmaram a unidade e a frequência, embora o campo de cobertura conceitual deste último esteja em construção.
- **Definição, abrangência e método:** saldo nominal da DBGG, sob a mesma metodologia das séries selecionadas. O cadastro classifica como saldos em reais correntes e mostra a fórmula `SERIE(13741)`. A definição institucional da DBGG consta da seção anterior e do manual.
- **Unidade original confirmada:** **R$ milhões**, e não reais unitários. Para apresentar em reais, multiplicar por 1.000.000; para trilhões de reais, dividir o valor original por 1.000.000. São valores correntes, sem deflação.
- **Natureza e frequência:** saldo mensal, não fluxo nem acumulado anual.
- **Cobertura:** dezembro de 2006 a setembro de 2026 nas verificações de início e última observação. “End date: Undefined” no cadastro significa ausência de término cadastral, não disponibilidade futura.
- **Formatos e acesso previsto:** JSON e CSV confirmados por amostras; consulta HTML dos metadados SGS. Futuro acesso por BCData/SGS com intervalo explícito. Outros formatos não foram validados especificamente para este código.
- **Evidências:** [amostra inicial CSV](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13761/dados?formato=csv&dataInicial=01/12/2006&dataFinal=31/12/2006) retornou `01/12/2006;1336644,90`; [última observação JSON](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13761/dados/ultimos/1?formato=json) retornou `01/09/2026`, valor `11113782.53`, em milhões de reais.
- **Limites:** continuidade mensal ainda não auditada. A busca pelo código no catálogo de dados abertos não localizou um conjunto; isso não invalida a identificação confirmada diretamente no SGS. A data de atualização do painel de metadados, 15/12/2010, tampouco é a última competência.

## 3. Fatores condicionantes — base localizada, validação parcial

- **Nome oficial da página:** Série histórica da DBGG - fatores condicionantes. **Instituição:** Banco Central do Brasil. Não foi confirmado código SGS para esta base ou para seus componentes.
- **Acesso:** [página oficial](https://www.bcb.gov.br/htms/Infecon/seriehistDBGGFC.asp?frame=1), que oferece um recurso “Mensal”, e [ZIP vinculado pela página](https://www.bcb.gov.br/ftp/notaecon/facdbp.zip). Documentação geral: manual citado acima. [Tabelas especiais](https://www.bcb.gov.br/estatisticas/tabelasespeciais) é uma rota oficial a investigar para eventual versão atualizada; sua leitura nesta consulta retornou apenas a exigência de JavaScript.
- **Formato confirmado:** ZIP de 51.187 bytes contendo `Facdbp.xls` (143.872 bytes). Acesso previsto: download manual da planilha oficial e conferência visual das abas e notas antes de qualquer extração.
- **Inspeção limitada:** os nomes das abas extraídos do arquivo são “Fluxos mensais” e “Fluxos acumulados no ano”. A extração de texto também encontrou rótulos de saldo, variação mensal e variação acumulada no ano. Portanto, há apresentações temporais distintas; não se deve tratar toda coluna como fluxo mensal.
- **Componentes identificados nos rótulos:** emissões líquidas; juros nominais; ajuste cambial; dívida externa — outros ajustes; reconhecimento de dívidas; privatizações; efeito do crescimento do PIB sobre a dívida. Também aparecem agregados de fatores e necessidades de financiamento. A presença textual está confirmada, mas a associação de cada rótulo às células, unidades, hierarquia e competências permanece pendente. Não somar agregados e seus subcomponentes.
- **Unidades e metodologia:** o texto contém indicação de milhões de reais e apresentações em relação ao PIB. Uma nota descreve fatores divididos pelo PIB corrente acumulado em doze meses e adverte que isso não reflete, isoladamente, a variação da razão dívida/PIB; outra menciona soma dos efeitos mensais até o mês de referência. É necessário ler as notas junto às respectivas tabelas para confirmar a unidade e a aplicação de cada coluna, inclusive o efeito do PIB.
- **Cobertura:** primeira e última competências **não confirmadas**. A entrada do ZIP e a propriedade de última gravação do XLS indicam dezembro de 2018; são sinais de arquivo legado, não prova de última competência. Não há evidência suficiente de cobertura de 2023–2026.
- **Pendências essenciais:** abrir as células da planilha com ferramenta adequada, conferir cabeçalhos, notas, primeira e última competência; localizar versão oficial que cubra 2023–2026, se este arquivo não cobrir; confirmar unidade, sinais, componentes e hierarquia de cada apresentação; verificar conciliação com a variação do saldo e da relação dívida/PIB. Não propor cálculos de contribuições antes disso.
- **Limitação de acesso:** o navegador de pesquisa não processou o ZIP; o download direto funcionou. Sem leitor XLS disponível no ambiente, foram inspecionados apenas formato, propriedades e rótulos de texto. Nenhuma dependência foi instalada e nenhum script de coleta ou análise foi implementado.

## Decisões para a etapa seguinte

1. Manter as unidades originais registradas; converter apenas na apresentação, com rótulos explícitos. Diferenças entre percentuais do PIB são expressas em pontos percentuais (p.p.), distintas de taxas de crescimento percentual.
2. Não somar saldos mensais para obter “dívida anual”. Usar saldo de fim do período para esse propósito; em 2026, indicar o mês efetivamente disponível.
3. Não somar acumulados no ano. Uma eventual transformação em fluxos mensais dependerá da definição oficial, da mudança de ano e das revisões da base; ainda não foi aprovada ou implementada.
4. Antes da coleta completa, resolver as pendências dos fatores e verificar a continuidade e compatibilidade temporal das fontes. O mapeamento permanece parcial.
5. Decidir posteriormente quais dados serão versionados. Os arquivos temporários de verificação ficaram em `/tmp`, fora do repositório; os exemplos acima são evidências documentais pontuais.
