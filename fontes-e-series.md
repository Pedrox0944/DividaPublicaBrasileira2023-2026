# Fontes e séries da dívida pública brasileira

Consulta: **10/11/2026**, horário de referência America/Fortaleza. Estado: **mapeamento parcial; validação dos fatores condicionantes pendente**.

## Escopo e critérios

O período principal permanece janeiro de 2023 até o último mês disponível de 2026. Nas consultas pontuais das duas séries SGS em 10/11/2026, a última competência retornada foi setembro de 2026. A cobertura dos fatores ainda não foi confirmada; portanto, esse término não se aplica automaticamente à decomposição. 2026 será tratado como ano parcial. Consultar dezembro de 2022 apenas como referência para calcular a variação de janeiro de 2023 é uma **proposta pendente de decisão**.

Metadados são informações que descrevem os dados: conceito, unidade, frequência, cobertura e método. Conferi-los antes da coleta evita juntar medidas incompatíveis ou interpretar um acumulado como movimento mensal. Nesta etapa foram consultados metadados, duas observações por série e o pequeno arquivo oficial dos fatores; não foi construída uma base de análise.

## 1. DBGG em percentual do PIB — SGS 13762

- **Nome oficial:** Dívida bruta do governo geral (% PIB) - Metodologia utilizada a partir de 2008.
- **Responsável:** Banco Central do Brasil. O catálogo indica BCB/Depec; os dados básicos atuais do SGS indicam BCB-DSTAT e gestão DSTAT/DIFIN/SUFIP. Registram-se as duas atribuições conforme cada fonte.
- **Acesso e documentação:** [catálogo oficial](https://dadosabertos.bcb.gov.br/dataset/13762-divida-bruta-do-governo-geral--pib---metodologia-utilizada-a-partir-de-2008), [metadados SGS](https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&hdOidSerieSelecionada=13762) e [Manual de Estatísticas Fiscais, maio de 2019](https://www.bcb.gov.br/content/estatisticas/Documents/notas_metodologicas/estatisticas-fiscais/estatisticasfiscais.pdf), especialmente seções 4.3 e 5.
- **Definição e abrangência:** endividamento bruto dos governos federal, estaduais e municipais, incluindo compromissadas do BCB; exclui dívidas das empresas estatais. A metodologia consolida obrigações entre entes abrangidos e converte obrigações externas pelo câmbio de fim de período. Não equivale à DLSP nem apenas à dívida federal.
- **Unidade e natureza:** percentual do PIB; relação entre saldo de dívida e PIB, não fluxo. A fórmula exibida no SGS utiliza `SERIE(13741) / SERIE(4382)*100` para o período relevante. O denominador foi conferido nos [dados básicos da SGS 4382](https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&hdOidSerieSelecionada=4382): PIB acumulado nos últimos 12 meses, a preços correntes, em milhões de reais, com frequência mensal. Não é o PIB apenas do mês. Esses códigos são referências da fórmula oficial, não novas séries selecionadas para coleta. O método de construção mensal do PIB ainda não foi aprofundado nesta etapa.
- **Frequência e cobertura:** mensal; início em dezembro de 2006, confirmado no cadastro e na amostra inicial; última observação retornada: setembro de 2026. O nome “a partir de 2008” identifica a metodologia e não a primeira competência.
- **Formatos e acesso previsto:** catálogo oferece JSON, CSV, SOAP/WSDL e visualização HTML. Para uma futura coleta, preferir BCData/SGS em JSON ou CSV com intervalo explícito, após autorização.
- **Evidências:** [amostra inicial CSV](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13762/dados?formato=csv&dataInicial=01/12/2006&dataFinal=31/12/2006) retornou `01/12/2006;55,48`; [amostra de setembro de 2026 com intervalo fixo](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13762/dados?formato=json&dataInicial=01/09/2026&dataFinal=30/09/2026) retornou `01/09/2026`, valor `82.93`. Ambos os exemplos foram reconfirmados em 10/11/2026. A consulta [ultimos/1](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13762/dados/ultimos/1?formato=json), usada apenas para descobrir a competência mais recente, retornou o mesmo mês e valor nessa data. A data representa a competência mensal.
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
- **Evidências:** [amostra inicial CSV](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13761/dados?formato=csv&dataInicial=01/12/2006&dataFinal=31/12/2006) retornou `01/12/2006;1336644,90`; [amostra de setembro de 2026 com intervalo fixo](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13761/dados?formato=json&dataInicial=01/09/2026&dataFinal=30/09/2026) retornou `01/09/2026`, valor `11113782.53`, em milhões de reais. Ambos os exemplos foram reconfirmados em 10/11/2026. A consulta [ultimos/1](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13761/dados/ultimos/1?formato=json), usada apenas para descobrir a competência mais recente, retornou o mesmo mês e valor nessa data.
- **Limites:** continuidade mensal ainda não auditada. A busca pelo código no catálogo de dados abertos não localizou um conjunto; isso não invalida a identificação confirmada diretamente no SGS. A data de atualização do painel de metadados, 15/12/2010, tampouco é a última competência.

## Rastreabilidade das consultas SGS

| Informação | Significado e evidência |
|---|---|
| Competência | Mês ao qual o dado se refere: dezembro de 2006 e setembro de 2026 nas quatro amostras verificadas. O dia 01 no retorno identifica o mês; não é a data de divulgação. |
| Data da consulta | 10/11/2026: quando os retornos foram lidos e os valores acima reconfirmados. |
| Atualização dos metadados | 08/09/2026 no catálogo da SGS 13762 e 15/12/2010 no painel da SGS 13761, conforme verificação anterior. Indicam atualização da descrição cadastral, não competência nem publicação dos valores. |

Os intervalos fixos permitem reencontrar a competência citada, mas **não congelam a versão dos dados**: consultas futuras podem retornar valores revisados pelo BCB. Os valores transcritos registram o retorno observado em 10/11/2026; não foi criado um arquivo histórico das respostas. Verificar primeiro e último mês não prova continuidade mensal: a presença de todos os meses de 2023–2026 permanece pendente.

## 3. Fatores condicionantes — leitura das células bloqueada

- **Nome oficial da página:** Série histórica da DBGG - fatores condicionantes. **Instituição:** Banco Central do Brasil. Não foi confirmado código SGS para esta base ou para seus componentes.
- **Acesso:** [página oficial](https://www.bcb.gov.br/htms/Infecon/seriehistDBGGFC.asp?frame=1), que oferece um recurso “Mensal”, e [ZIP vinculado pela página](https://www.bcb.gov.br/ftp/notaecon/facdbp.zip). Documentação geral: manual citado acima. [Tabelas especiais](https://www.bcb.gov.br/estatisticas/tabelasespeciais) é uma rota oficial a investigar para eventual versão atualizada; sua leitura nesta consulta retornou apenas a exigência de JavaScript.
- **Formato confirmado:** o vínculo foi reconferido no HTML oficial e o ZIP foi baixado novamente em 10/11/2026 para `/tmp/facdbp-validacao.zip`. Contém `Facdbp.xls` (143.872 bytes). SHA-256 do ZIP consultado: `f1c5ddab041f5be3dbede15e79133ab5daccd5684189fd9cb66175631cde298c`. O hash identifica os bytes examinados, não a competência dos dados. Acesso previsto: leitura da planilha oficial com ferramenta adequada, sem modificar os dados.
- **Inspeção anterior, insuficiente para validar células:** os nomes das abas extraídos como texto foram “Fluxos mensais” e “Fluxos acumulados no ano”. A extração de texto também encontrou rótulos de saldo, variação mensal e variação acumulada no ano. Portanto, há apresentações temporais distintas; não se deve tratar toda coluna como fluxo mensal.
- **Rótulos encontrados anteriormente; componentes candidatos a confirmar:** emissões líquidas; juros nominais; ajuste cambial; dívida externa — outros ajustes; reconhecimento de dívidas; privatizações; efeito do crescimento do PIB sobre a dívida. Também aparecem agregados de fatores e necessidades de financiamento. A presença textual foi registrada na inspeção anterior, mas não comprova que todos sejam componentes da apresentação de DBGG relevante. A associação de cada rótulo às células, unidades, hierarquia e competências permanece pendente. Em particular, privatizações não está validada como componente da tabela a utilizar. Não somar agregados e seus subcomponentes.
- **Unidades e metodologia ainda não validadas nas células:** a extração de texto anterior contém indicação de milhões de reais e apresentações em relação ao PIB. Uma nota descreve fatores divididos pelo PIB corrente acumulado em doze meses e adverte que isso não reflete, isoladamente, a variação da razão dívida/PIB; outra menciona soma dos efeitos mensais até o mês de referência. É necessário ler as notas junto às respectivas tabelas para confirmar a unidade e a aplicação de cada coluna, inclusive o efeito do PIB.
- **Cobertura:** primeira e última competências **não confirmadas nas células**. Não foi possível afirmar presença ou ausência de 2023–2026. Datas de gravação do XLS e da entrada no ZIP não foram usadas para inferir a última competência ou declarar o arquivo desatualizado.
- **Pendências essenciais:** abrir as células da planilha com ferramenta adequada, conferir cabeçalhos, notas, primeira e última competência; localizar versão oficial que cubra 2023–2026, se este arquivo não cobrir; confirmar unidade, sinais, componentes e hierarquia de cada apresentação; verificar conciliação com a variação do saldo e da relação dívida/PIB. Não propor cálculos de contribuições antes disso.
- **Bloqueio técnico confirmado nesta etapa:** não foram encontrados `libreoffice`/`soffice`, `ssconvert` ou `xls2csv` no PATH; a lista de pacotes Python não contém leitor XLS, e `Spreadsheet::ParseExcel` não está disponível no Perl. A busca nas bibliotecas de sistema também não localizou leitores relevantes. O download funcionou, mas **o XLS não foi aberto em um leitor de células**. A ferramenta mínima para prosseguir é `xlrd` no Python, ou LibreOffice para inspeção visual. Nenhuma dependência foi instalada, respeitando o limite desta tarefa. Não foi implementado leitor próprio nem pipeline.

### Caminhos oficiais alternativos investigados

A busca serve para localizar uma apresentação utilizável sem presumir que o ZIP seja atual ou antigo. Como sua cobertura não foi lida, não se afirma que uma substituição seja necessária.

| Caminho consultado em 10/11/2026 | Resultado e limite |
|---|---|
| [Tabelas especiais](https://www.bcb.gov.br/estatisticas/tabelasespeciais) | A leitura direta retornou a exigência de JavaScript. A pesquisa indexada do domínio oficial mostrou os títulos “Dívida Bruta do Governo Geral - DBGG - Fatores Condicionantes” e “Dívida Bruta do Governo Geral - Fatores Condicionantes - detalhamento”, mas não forneceu links de arquivos verificáveis. São pistas de navegação, não planilhas atualizadas validadas. |
| [Estatísticas Fiscais](https://www.bcb.gov.br/estatisticas/estatisticasfiscais) | A leitura direta também exigiu JavaScript. Não foi obtido vínculo verificável para as tabelas anexas de uma nota de 2026. Falta abrir a página com JavaScript e seguir o link de tabelas da nota selecionada. |
| [Catálogo oficial: pesquisa DBGG](https://dadosabertos.bcb.gov.br/api/3/action/package_search?q=DBGG&rows=100) | A consulta de metadados retornou 29 conjuntos. A leitura de seus títulos não identificou uma base de fatores da DBGG. A busca também retorna DLSP e ajustes diversos; nenhum desses códigos foi adotado como substituto. Não é prova de inexistência dos fatores no SGS; a pesquisa direta dos componentes no SGS continua pendente. |

Não foi localizado um link exato de uma **versão atualizada validada** dos fatores. Permanecem necessários acesso às páginas dinâmicas e leitura das células do recurso escolhido; não foram construídos endereços de arquivos por suposição.

### Interpretação e conciliação pontual

**Resultado: bloqueada.** Não há mês com contribuições lidas em células, unidades confirmadas e hierarquia validada. Por isso, não foi possível selecionar uma observação compatível, somar componentes ou quantificar diferenças e arredondamentos. Não houve alteração dos dados para forçar igualdade.

O objetivo da conferência será verificar se os componentes independentes explicam a variação correspondente. O saldo é um nível; a apresentação monetária dos fatores descreve mudanças desse nível. A apresentação acumulada no ano deve ser distinguida da mensal, sem somar acumulados ou misturar totais e subcomponentes. A classificação exata e os sinais publicados ainda dependem dos cabeçalhos e notas.

Como identidade algébrica geral, para saldo nominal `D` e denominador `Y` compatíveis:

`100 × (D_t/Y_t − D_anterior/Y_anterior) = 100 × (D_t − D_anterior)/Y_t + 100 × D_anterior × (1/Y_t − 1/Y_anterior)`.

Isso explica por que dividir fatores monetários pelo PIB do período não basta, isoladamente, para explicar a mudança da relação dívida/PIB: também há efeito do denominador. A identidade **não valida a convenção específica das tabelas do BCB**, sobretudo nos acumulados. Antes de aplicá-la, é preciso confirmar o PIB usado, os períodos de referência e a regra oficial de acumulação. Diferenças residuais só poderão ser classificadas como arredondamento após a leitura dos valores, da precisão e das notas; não serão presumidas como tal.

### Estado das pendências anteriores

| Pendência | Estado nesta entrega | Evidência ou próximo requisito |
|---|---|---|
| Reconfirmar quatro amostras SGS e fixar intervalos | Resolvida | Dois meses por série reconfirmados; links fixos acima. |
| Separar competência, consulta e atualização cadastral; explicar revisões | Resolvida | Seção de rastreabilidade. |
| Identificar o denominador da fórmula da SGS 13762 | Resolvida quanto ao conceito cadastral | SGS 4382: PIB em 12 meses, preços correntes; construção mensal ainda não aprofundada. |
| Abrir XLS; validar abas, cabeçalhos e notas em células | Bloqueada | Falta leitor XLS; `xlrd` ou LibreOffice é o requisito mínimo. |
| Confirmar primeira/última competência e cobertura 2023–2026 dos fatores | Bloqueada | Depende da leitura das células; datas do arquivo não comprovam cobertura. |
| Confirmar componentes, unidades, sinais e hierarquia | Bloqueada | Rótulos anteriores permanecem candidatos; faltam cabeçalhos e notas associados às células. |
| Distinguir apresentações mensais, acumuladas e em relação ao PIB | Parcial | Distinção conceitual documentada; convenções específicas da planilha não validadas. |
| Localizar alternativa oficial atualizada, se necessária | Parcial | Rotas e pistas registradas; sem arquivo alternativo ou cobertura validada. |
| Conciliar um mês e avaliar diferenças/arredondamentos | Bloqueada | Nenhum conjunto compatível de células foi lido. |
| Auditar continuidade mensal das séries SGS | Parcial | Apenas extremos foram amostrados; a tarefa não montou base completa. |

## Decisões para a etapa seguinte

1. Manter as unidades originais registradas; converter apenas na apresentação, com rótulos explícitos. Diferenças entre percentuais do PIB são expressas em pontos percentuais (p.p.), distintas de taxas de crescimento percentual.
2. Não somar saldos mensais para obter “dívida anual”. Usar saldo de fim do período para esse propósito; em 2026, indicar o mês efetivamente disponível.
3. Não somar acumulados no ano. Uma eventual transformação em fluxos mensais dependerá da definição oficial, da mudança de ano e das revisões da base; ainda não foi aprovada ou implementada.
4. Antes da coleta completa, resolver as pendências dos fatores e verificar a continuidade e compatibilidade temporal das fontes. O mapeamento permanece parcial.
5. Decidir posteriormente quais dados serão versionados. Os arquivos temporários de verificação ficaram em `/tmp`, fora do repositório; os exemplos acima são evidências documentais pontuais.
