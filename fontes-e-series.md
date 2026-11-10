# Fontes e séries da dívida pública brasileira

Consulta: **10/11/2026**, horário de referência America/Fortaleza. Estado: **mapeamento suficiente para a primeira entrega mensal de janeiro/2023 a setembro/2026, com ressalvas documentadas; validação completa das demais apresentações não concluída**.

## Escopo e critérios

O período principal permanece janeiro de 2023 até o último mês disponível de 2026. Nas consultas pontuais das duas séries SGS em 10/11/2026, a última competência retornada foi setembro de 2026. O XLSX atual dos fatores também contém janeiro de 2023 a setembro de 2026; o ZIP/XLS legado termina em novembro de 2018. Além da presença das células, foram verificados os saldos e as identidades dos componentes mensais selecionados no intervalo; as demais apresentações não foram validadas integralmente. 2026 será tratado como ano parcial. Consultar dezembro de 2022 apenas como referência para calcular a variação de janeiro de 2023 é uma **proposta pendente de decisão**.

Metadados são informações que descrevem os dados: conceito, unidade, frequência, cobertura e método. Conferi-los antes da coleta evita juntar medidas incompatíveis ou interpretar um acumulado como movimento mensal. Foram consultados metadados, amostras históricas e os 45 meses do período principal em cada série SGS, além de células dos arquivos oficiais dos fatores. Os trechos de Python serviram apenas à inspeção e à validação documental; não foi construída a base final de análise nem um pipeline.

## 1. DBGG em percentual do PIB — SGS 13762

- **Nome oficial:** Dívida bruta do governo geral (% PIB) - Metodologia utilizada a partir de 2008.
- **Responsável:** Banco Central do Brasil. O catálogo indica BCB/Depec; os dados básicos atuais do SGS indicam BCB-DSTAT e gestão DSTAT/DIFIN/SUFIP. Registram-se as duas atribuições conforme cada fonte.
- **Acesso e documentação:** [catálogo oficial](https://dadosabertos.bcb.gov.br/dataset/13762-divida-bruta-do-governo-geral--pib---metodologia-utilizada-a-partir-de-2008), [metadados SGS](https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&hdOidSerieSelecionada=13762) e [Manual de Estatísticas Fiscais, maio de 2019](https://www.bcb.gov.br/content/estatisticas/Documents/notas_metodologicas/estatisticas-fiscais/estatisticasfiscais.pdf), especialmente seções 4.3 e 5.
- **Definição e abrangência:** endividamento bruto dos governos federal, estaduais e municipais, incluindo compromissadas do BCB; exclui dívidas das empresas estatais. A metodologia consolida obrigações entre entes abrangidos e converte obrigações externas pelo câmbio de fim de período. Não equivale à DLSP nem apenas à dívida federal.
- **Unidade e natureza:** percentual do PIB; relação entre saldo de dívida e PIB, não fluxo. A fórmula exibida no SGS utiliza `SERIE(13741) / SERIE(4382)*100` para o período relevante. O denominador foi conferido nos [dados básicos da SGS 4382](https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&hdOidSerieSelecionada=4382): PIB acumulado nos últimos 12 meses, a preços correntes, em milhões de reais, com frequência mensal. Não é o PIB apenas do mês. Esses códigos são referências da fórmula oficial, não novas séries selecionadas para coleta. O método de construção mensal do PIB ainda não foi aprofundado nesta etapa.
- **Frequência e cobertura:** mensal; início em dezembro de 2006, confirmado no cadastro e na amostra inicial; última observação retornada: setembro de 2026. O nome “a partir de 2008” identifica a metodologia e não a primeira competência.
- **Formatos e acesso previsto:** catálogo oferece JSON, CSV, SOAP/WSDL e visualização HTML. Para uma futura coleta, preferir BCData/SGS em JSON ou CSV com intervalo explícito, após autorização.
- **Evidências:** [amostra inicial CSV](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13762/dados?formato=csv&dataInicial=01/12/2006&dataFinal=31/12/2006) retornou `01/12/2006;55,48`; [amostra de setembro de 2026 com intervalo fixo](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13762/dados?formato=json&dataInicial=01/09/2026&dataFinal=30/09/2026) retornou `01/09/2026`, valor `82.93`. Ambos os exemplos foram reconfirmados em 10/11/2026. A consulta [ultimos/1](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13762/dados/ultimos/1?formato=json), usada apenas para descobrir a competência mais recente, retornou o mesmo mês e valor nessa data. A data representa a competência mensal.
- **Verificação do intervalo principal:** 45 meses de janeiro/2023 a setembro/2026, sem ausências, duplicações ou valores inválidos; saldos compatíveis com o XLSX à precisão de duas casas do SGS, conforme a seção de validação mensal abaixo. A atualização dos metadados do catálogo em 08/09/2026 não foi usada como data do último dado.

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
- **Verificação e limites:** os 45 meses do intervalo principal foram conferidos, sem ausências, duplicações ou valores inválidos, e comparados ao XLSX conforme a seção abaixo. A busca pelo código no catálogo de dados abertos não localizou um conjunto; isso não invalida a identificação confirmada diretamente no SGS. A data de atualização do painel de metadados, 15/12/2010, tampouco é a última competência.

## Rastreabilidade das consultas SGS

| Informação | Significado e evidência |
|---|---|
| Competência | Mês ao qual o dado se refere: dezembro/2006 na amostra histórica e janeiro/2023 a setembro/2026 na verificação integral do intervalo principal. O dia 01 no retorno identifica o mês; não é a data de divulgação. |
| Data da consulta | 10/11/2026: quando os retornos foram lidos e os valores acima reconfirmados. |
| Atualização dos metadados | 08/09/2026 no catálogo da SGS 13762 e 15/12/2010 no painel da SGS 13761, conforme verificação anterior. Indicam atualização da descrição cadastral, não competência nem publicação dos valores. |

Os intervalos fixos permitem reencontrar a competência citada, mas **não congelam a versão dos dados**: consultas futuras podem retornar valores revisados pelo BCB. Os valores transcritos registram o retorno observado em 10/11/2026. As duas respostas do intervalo principal ficaram temporariamente em `/tmp`, com hashes registrados abaixo; não foi criado histórico versionado de dados. A presença dos 45 meses foi agora conferida diretamente, sem inferi-la apenas dos extremos.

## Ambiente usado para desbloquear a leitura

Em 10/11/2026, o terminal disponibilizou `/usr/bin/python` e `/usr/bin/python3`, com Python **3.13.16**. Foi criada a `.venv` exclusiva do projeto com `python -m venv .venv`. A instalação foi feita por `.venv/bin/python -m pip install xlrd`; a versão instalada é **xlrd 2.0.2**. Todos os trechos de inspeção posteriores usaram explicitamente `.venv/bin/python`.

`git check-ignore -v .venv/bin/python` confirmou a regra `.venv/` na linha 6 do `.gitignore` existente. Não houve instalação global, uso de sudo ou alteração do `.gitignore`. Esta é apenas a ferramenta de leitura XLS: **o ambiente completo de análise não está configurado**.

O XLSX alternativo foi identificado antes da leitura. `xlrd` 2.0.2 não suporta XLSX; para a inspeção pontual foram usados `zipfile` e `xml.etree.ElementTree` da biblioteca padrão, lendo os valores armazenados e as referências das células em XML. Não houve recálculo das fórmulas pelo Excel nem instalação de outro leitor. Para uma futura implementação geral, um leitor como `openpyxl` poderá ser avaliado, mas não foi instalado nesta tarefa.

## 3. Fatores condicionantes — arquivos oficial legado e atual

**Responsável:** Banco Central do Brasil. Não foi confirmado código SGS para os fatores. O identificador utilizável nesta etapa é o arquivo oficial, com o caminho e a versão observada registrados abaixo.

### Caminho de acesso e evidência do arquivo consultado

| Recurso | Navegação confirmada em 10/11/2026 | Formato e identificação |
|---|---|---|
| Arquivo legado | [Série histórica da DBGG — fatores condicionantes](https://www.bcb.gov.br/htms/Infecon/seriehistDBGGFC.asp?frame=1) → link [facdbp.zip](https://www.bcb.gov.br/ftp/notaecon/facdbp.zip), lido no HTML da página | ZIP contendo `Facdbp.xls`, 143.872 bytes; SHA-256 do ZIP: `f1c5ddab041f5be3dbede15e79133ab5daccd5684189fd9cb66175631cde298c`. |
| **Fonte adequada ao período do projeto** | [Tabelas especiais](https://www.bcb.gov.br/estatisticas/tabelasespeciais) → “Dívida Bruta do Governo Geral - DBGG - Fatores Condicionantes” → [Facdbp.xlsx](https://www.bcb.gov.br/content/estatisticas/Documents/Tabelas_especiais/Facdbp.xlsx) | XLSX; SHA-256: `248dfef0e1cc5ef0315c3282f758f05264b3315283fe187ff9fe884dd0cc0e62`. Células de 2023–setembro/2026 presentes. |
| Detalhamento, inspeção direcionada | Mesma página → “Dívida Bruta do Governo Geral - Fatores Condicionantes - detalhamento” → [Facdetdbp.xlsx](https://www.bcb.gov.br/content/estatisticas/Documents/Tabelas_especiais/Facdetdbp.xlsx) | XLSX; aba `Rec Div` lida para comparar o total de reconhecimento de dívidas nos 45 meses. Demais abas não foram validadas integralmente. SHA-256: `f5485952a064643a510ee140dc0181b9e4ac4363b769bd20e93465befcaa5a60`. |
| Nota fiscal contemporânea | [Estatísticas Fiscais](https://www.bcb.gov.br/estatisticas/estatisticasfiscais) → [Texto de outubro/2026](https://www.bcb.gov.br/content/estatisticas/hist_estatisticasfiscais/202610_Texto_de_estatisticas_fiscais.pdf) e [Tabelas de outubro/2026](https://www.bcb.gov.br/content/estatisticas/hist_estatisticasfiscais/202610_Tabelas_de_estatisticas_fiscais.xlsx) | Links obtidos da página renderizada. PDF lido: nota de **29/10/2026**, tratando setembro/2026. O anexo XLSX foi apenas localizado, não inspecionado. |

As páginas dinâmicas foram abertas com o Chrome já instalado em `/opt/google/chrome/chrome`, modo headless. Assim foi possível obter os `href` reais, antes indisponíveis na leitura sem JavaScript. Não foram inventados endereços de arquivos. Os downloads e a extração ficaram em `/tmp/dbgg-celulas-b5n8nqwv/`, fora do repositório. Os hashes identificam os bytes consultados, não a competência; os links podem servir versões revisadas no futuro.

### Abas, datas e cobertura efetivamente lidas

| Arquivo e aba | Cabeçalhos e limites nas células | Cobertura verificada |
|---|---|---|
| XLS, `Fluxos mensais` | Ano na linha 5, mês por extenso na linha 7; `C5=2006`, `C7=Dezembro`; bloco iniciado em `EF5=2018`, terminando em `EP7=Novembro`, com saldo em `EP10` | Dezembro/2006 a novembro/2018. Há ainda uma referência auxiliar a novembro/2006 em `A52:B52`; ela não é uma coluna mensal dos fatores. Não contém 2023–2026. |
| XLS, `Fluxos acumulados no ano` | `C5=2007`, `C7=Dezembro`; `N5=2018`, `N7=Novembro`; valores nas respectivas colunas | Dezembro/2007 a novembro/2018: colunas de fechamento de cada ano e acumulado parcial de 2018, não uma sequência de todos os meses. |
| XLSX, `Fluxos mensais` | `C5=2006`, `C7=Dezembro`; `HX5=2026`, `IF7=Setembro`; dados até `IF` | 238 colunas mensais, de dezembro/2006 a setembro/2026. No período principal, **45 meses**: `GN:GY` em 2023, `GZ:HK` em 2024, `HL:HW` em 2025 e `HX:IF` em 2026. |
| XLSX, `Fluxos acumulados no ano` | `C5=2007`, `C7=Dezembro`; `V5=2026`, `V7=Setembro` | Fechamentos de dezembro/2007 a dezembro/2025 e janeiro–setembro/2026 acumulado. Para o projeto: `S`=2023, `T`=2024, `U`=2025, `V`=2026 parcial. |

No XLS as datas **não são células tipadas como data Excel**: foram lidos os anos numéricos e os meses textuais dos cabeçalhos, mantendo o ano de cada bloco. O mesmo padrão foi identificado no XLSX. Nenhuma data de gravação foi usada para inferir cobertura.

No XLSX foram examinadas as 45 colunas do período principal e confirmadas células numéricas nas linhas `10, 12, 14–23, 25, 28, 30, 32–41 e 43` (26 linhas, 1.170 células). Essa conferência inicial comprovou presença. Na etapa seguinte, descrita abaixo, os 45 meses SGS foram comparados aos saldos e as identidades dos componentes mensais foram verificadas. Isso ainda não valida integralmente todas as abas, subcomponentes ou convenções da fonte.

### Estrutura, unidades, hierarquia e sinais

A estrutura relevante é a mesma nos dois arquivos. A primeira parte traz **R$ milhões correntes** (indicação na linha 4), e a segunda apresenta a relação e os fatores em relação ao PIB, conforme a nota 1 nas linhas 46–47. Os nomes de linhas abaixo são os publicados; “Nec. de financiamento” refere-se à decomposição da DBGG, sem equivalência automática ao resultado nominal de todo o setor público.

| Linha monetária / linha relativa ao PIB | Componente ou agregado | Como usar e sinais observados em jan/2023–set/2026 |
|---|---|---|
| 10 / 28 | DBGG — saldo | Nível em R$ milhões / % do PIB. Não somar meses. |
| 12 / 30 | Variação mensal ou acumulada no ano | Diferença de saldos monetários / mudança da relação em **p.p.**, conforme a aba. |
| 14 / 32 | Fatores condicionantes — total | Agregado; não adicionar aos componentes. Linha 32 é proporção do PIB, não a variação da relação por si só. |
| 15 / 33 | Nec. de financiamento — DBGG | Subtotal: emissões líquidas + juros nominais. |
| 16 / 34 | Emissões líquidas | Componente independente: valores positivos aumentam a dívida; negativos correspondem a resgates líquidos na leitura da decomposição. Ambos os sinais presentes. |
| 17 / 35 | Juros nominais | Componente independente; valores positivos em todos os 45 meses examinados. |
| 18 / 36 | Ajuste cambial — total | Componente independente com ambos os sinais; subdividido nas duas linhas seguintes. |
| 19 / 37 | Dívida interna indexada ao câmbio | Subcomponente do ajuste cambial, com ambos os sinais. |
| 20 / 38 | Dívida externa — metodológico | Subcomponente do ajuste cambial, com ambos os sinais. |
| 21 / 39 | Dívida externa — outros ajustes | Componente independente, com ambos os sinais. Nota sobre paridade da cesta de moedas e demais ajustes externos. |
| 22 / 40 | Reconhecimento de dívidas | Componente independente; foram observados valores positivos e negativos. Não presumir que seja sempre aumento da dívida. |
| 23 / 41 | Privatizações | Linha efetivamente presente, com zero nos 45 meses examinados. Sua presença não implica contribuição diferente de zero no período. |
| — / 43 | Efeito do crescimento do PIB sobre a dívida | Contribuição em p.p. ligada à mudança do denominador; não é um fluxo monetário a adicionar à linha 14. |
| 25 / — | PIB acumulado em doze meses — corrente | Denominador em R$ milhões; não confundir com o PIB apenas do mês. |

As linhas 32–41 expressam fatores como **% do PIB**, enquanto as linhas 30 e 43 expressam variações ou efeitos em **pontos percentuais**. Essa distinção deve aparecer nos rótulos dos futuros gráficos.

Para o total monetário, usar **16 + 17 + 18 + 21 + 22 + 23**, ou substituir 16+17 pelo subtotal 15. Se usar 18, não somar novamente 19 e 20. Valores positivos/negativos são contribuições de aumento/redução na identidade contábil; não são julgamento sobre políticas ou prova causal. Sinais futuros não foram presumidos com base na amostra.

### Notas e interpretação das apresentações

- Nas duas abas, `A46:A47` informa que os fatores como percentual do PIB são o total dos fatores dividido pelo PIB corrente acumulado em 12 meses, multiplicado por 100, e adverte que isso **não reflete a variação da dívida em percentagem do PIB**. A mudança da relação exige também o efeito do denominador.
- Na aba mensal, `A48` inclui paridade da cesta de moedas e outros ajustes externos; `A49` descreve o efeito do PIB pela fórmula `Dt-1/(PIBMesAtual/PIBMesBase) - Dt-1`. A linha 50 registra a legenda de dados preliminares; não se inferiu que todas as células tenham essa marcação.
- Na aba acumulada, `A48` diz “Considera a soma dos efeitos mensais até o mês de referência”; a chamada está no ajuste cambial. `A49` trata dos demais ajustes externos e `A50` do efeito do PIB. A legenda de preliminares fica na linha 51.
- **Pendência editorial/metodológica:** a linha monetária de reconhecimento de dívidas remete a `3/` na aba mensal e `4/` na acumulada, mas essas notas descrevem o efeito do PIB. A inconsistência aparece tanto no XLS quanto no XLSX consultados. A investigação no manual e no detalhamento está registrada abaixo: a chamada continua sem correção oficial localizada, mas não impede usar a linha mensal publicada com a ressalva indicada.

Na aba acumulada, os saldos continuam sendo níveis de fim do período. Os fluxos monetários são acumulados desde janeiro. Conferência de 2026: a soma da linha 14 mensal de janeiro a setembro é **1.095.863,39241455 R$ milhões**, igual a `V14` da aba acumulada. As proporções mensais não devem ser somadas para reproduzir a proporção acumulada: a soma da linha 32 mensal é **8,358902029822124**, enquanto `V32` é **8,17685011924861**, pois os denominadores mensais variam. Para o acumulado publicado, ler a própria aba e suas notas.

Em setembro/2026 acumulado, `V32 + V43 = 8,17685011924861 − 3,8931408382141797 = 4,2837092810344295 p.p.`, igual a `V30` na precisão lida. Essa conferência não valida todas as convenções de cada subcomponente acumulado; em particular, a nota de soma de efeitos cambiais merece conferência detalhada antes de conversões próprias.

### Conciliação pontual — setembro de 2026, fonte atual

Foram usados os valores armazenados nas células do XLSX, sem misturar versões ou substituir seus valores pelos arredondados do SGS.

| Célula, aba `Fluxos mensais` | Valor em R$ milhões |
|---|---:|
| `IF16` — emissões líquidas | −50.009,993283230004 |
| `IF17` — juros nominais | 109.537,24508303 |
| `IF18` — ajuste cambial total | −77,34802133999999 |
| `IF21` — outros ajustes externos | −1.491,4534111300002 |
| `IF22` — reconhecimento de dívidas | 869,71031687 |
| `IF23` — privatizações | 0 |

A soma desses componentes, usando `Decimal` sobre os números textuais armazenados no XML, é **58.828,160684199985852 R$ milhões**. A diferença dos saldos é:

`IF10 − IE10 = 11.113.782,53130238 − 11.054.954,37061818 = 58.828,160684200 R$ milhões`.

Resíduo **soma menos diferença dos saldos: −0,000000000014148 R$ milhões**. Na precisão de seis casas decimais, ambos resultam em **58.828,160684**. O resíduo foi medido e preservado; não foi atribuído automaticamente a arredondamento da publicação nem corrigido nos dados. A origem exata das casas residuais nos valores armazenados não foi investigada.

A hierarquia também foi conferida nesse mês: `IF16 + IF17 = IF15 = 59.527,25179979999` e `IF19 + IF20 = IF18 = −77,34802133999999` na aritmética de ponto flutuante usada na inspeção. Esses subtotais não foram adicionados novamente.

Para a relação dívida/PIB:

`IF32 + IF43 = 0,43894983264831083 − 0,3793193868998799 = 0,05963044574843096 p.p.`, igual à variação publicada em `IF30` na precisão de ponto flutuante lida.

A diferença direta `IF28 − IE28`, entre **82,92615178626747%** e **82,86652134051903%**, resulta em **0,05963044574843934 p.p.**; o resíduo frente à soma acima é inferior a `10⁻¹⁴ p.p.` nessa aritmética. Também foi conferida a forma `100 × fator monetário / PIB corrente` e a expressão do efeito do PIB usando os saldos e denominadores da própria planilha. Nenhum dado foi alterado.

Os valores de setembro do XLSX são compatíveis, ao arredondar a duas casas, com as amostras SGS documentadas: **11.113.782,53 R$ milhões** e **82,93% do PIB**. Essa comparação pontual foi ampliada para os 45 meses na seção seguinte. A nota oficial de 29/10/2026 também descreve juros, resgates líquidos e efeito do PIB para setembro, coerentes com os sinais examinados; seus números têm precisão de apresentação diferente.

Como controle histórico separado, novembro/2018 do XLS também foi conciliado: soma dos componentes e diferença dos saldos são **52.741,105218 R$ milhões** a seis casas, e `EP32 + EP43 = EP30 = 0,3226751085283299 p.p.` na aritmética utilizada. Esse controle não estende a cobertura do XLS ao período do projeto.

### Validação mensal integral do intervalo da primeira entrega

Consulta em **10/11/2026**, com `.venv/bin/python`, sem reinstalar ferramentas ou baixar novamente o XLS/XLSX principal. Foi reutilizado `Facdbp-atual.xlsx`, identificado pelo hash acima. As respostas SGS abaixo são consultas de inspeção, não uma base final ou um pipeline.

| Série e consulta fixa | Meses esperados / recebidos | Ausentes / duplicados / fora do intervalo / inválidos |
|---|---:|---|
| [SGS 13761 — janeiro/2023 a setembro/2026](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13761/dados?formato=json&dataInicial=01/01/2023&dataFinal=30/09/2026) | 45 / 45 | 0 / 0 / 0 / 0 |
| [SGS 13762 — janeiro/2023 a setembro/2026](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13762/dados?formato=json&dataInicial=01/01/2023&dataFinal=30/09/2026) | 45 / 45 | 0 / 0 / 0 / 0 |

Foram interpretadas as datas no formato `dd/mm/aaaa`, comparadas as chaves ano/mês à sequência esperada e contadas as ocorrências por competência. Os valores foram interpretados com `Decimal` e verificados como numéricos, finitos e positivos, condição compatível com saldos da DBGG. As duas respostas estão em ordem cronológica. A aba `Fluxos mensais` contém exatamente as mesmas 45 competências selecionadas, também sem duplicação ou ausência.

Hashes SHA-256 das respostas brutas consultadas, mantidas apenas em `/tmp/dbgg-celulas-b5n8nqwv/`:

- SGS 13761: `70d66b5ba3170691e82f69a9803588844913855f6d2f855156d9fa8a47966b32`.
- SGS 13762: `416a199d9b17436c2fa847c2b1f9e069bd00e12b6aa1485edac0ace12c173faa`.

#### Comparação dos saldos com as séries SGS

Foram comparados, por competência, a linha 10 com a SGS 13761 e a linha 28 com a SGS 13762. A planilha armazena mais casas que o SGS. Para testar compatibilidade de precisão, calculou-se uma cópia arredondada a duas casas com `Decimal.quantize(..., ROUND_HALF_UP)`, sem modificar os valores de origem.

| Comparação | Pares | Divergências após arredondar a duas casas | Maior diferença absoluta antes de arredondar |
|---|---:|---:|---|
| Linha 10 × SGS 13761 | 45 | 0 | **0,0045211143 R$ milhões**, dezembro/2023: XLSX `8079270.0245211143`, SGS `8079270.02`. |
| Linha 28 × SGS 13762 | 45 | 0 | **0,004761341773143 p.p.**, setembro/2025: XLSX `77.835238658226857`, SGS `77.84`. |

Os 90 pares diferem nos números brutos por terem casas adicionais na planilha, mas todos coincidem à precisão de publicação do SGS. As diferenças máximas são inferiores a 0,005 na respectiva unidade. Portanto, há compatibilidade de precisão nesta consulta; não se declarou igualdade dos números brutos nem foram corrigidos os dados.

**Consequência prática:** usar SGS para apresentar os saldos e os valores de maior precisão da própria planilha para conferir a decomposição dos fatores. Diferenças mensais calculadas a partir dos saldos SGS arredondados podem não reproduzir todas as casas dos fluxos publicados; não substituir o fluxo oficial por um valor ajustado para fechar a conta.

#### Controles adicionais dos fatores mensais

Sem repetir a conciliação pontual já documentada de setembro, os mesmos relacionamentos foram verificados nas 45 colunas, usando os números textuais armazenados no XML e aritmética `Decimal`. Os resíduos máximos absolutos foram:

| Identidade | Meses | Maior resíduo absoluto |
|---|---:|---:|
| Linhas 16+17+18+21+22+23 menos total da linha 14 | 45 | `2,75 × 10⁻¹¹ R$ milhões` (junho/2024) |
| Linha 14 menos variação publicada na linha 12 | 45 | `9,3 × 10⁻¹⁰ R$ milhões` (outubro/2025) |
| Linhas 16+17 menos subtotal 15 | 45 | `1,6 × 10⁻¹¹ R$ milhões` (junho/2024) |
| Linhas 19+20 menos subtotal 18 | 45 | `2 × 10⁻¹² R$ milhões` (abril/2026) |
| Linhas 34+35+36+39+40+41+43 menos variação publicada na linha 30 | 45 | `2,53 × 10⁻¹⁶ p.p.` (junho/2024) |

Nas **44 transições de fevereiro/2023 a setembro/2026**, a diferença entre saldos consecutivos da própria planilha foi comparada à linha 12, com resíduo máximo de `6,8 × 10⁻¹⁰ R$ milhões` em agosto/2026. Para janeiro/2023, foi conferida a identidade com a **variação mensal já publicada** (`32.356,551644139923 R$ milhões`), sem calcular uma diferença usando dezembro/2022. O uso auxiliar desse mês continua pendente de decisão.

Esses resíduos foram medidos, não removidos nem atribuídos automaticamente a arredondamentos. Não foram encontradas divergências na escala da precisão publicada do SGS. Os controles sustentam o uso descritivo e contábil dos componentes mensais selecionados nesta versão, sem constituir auditoria das operações individuais que os originaram.

### Investigação da nota de reconhecimento de dívidas

O [Manual de Estatísticas Fiscais](https://www.bcb.gov.br/content/estatisticas/Documents/notas_metodologicas/estatisticas-fiscais/estatisticasfiscais.pdf), seção 6, **página impressa 38**, explica o reconhecimento de dívidas como ajuste que separa determinadas operações do resultado fiscal, citando dívidas geradas no passado e reclassificações. Esse trecho está no contexto de DLSP/NFSP: fornece contexto conceitual, mas não foi usado para transferir automaticamente toda convenção dessas estatísticas à DBGG.

A evidência específica da DBGG veio de [Facdetdbp.xlsx](https://www.bcb.gov.br/content/estatisticas/Documents/Tabelas_especiais/Facdetdbp.xlsx): a aba **`Rec Div`** tem `A1=Reconhecimento de Dívidas - Detalhamento por Item`, `A2=Fluxo mensal`, unidade **R$ milhões** na linha 5, ano na linha 6, mês na linha 8 e total `Dívida bruta do Governo Geral` na linha 11. Esse total foi comparado à linha 22 de `Facdbp.xlsx` nos **45 meses**. A diferença foi exatamente zero em 43 pares; nos outros dois, o maior resíduo absoluto foi **`5 × 10⁻¹³ R$ milhões`**, outubro/2023 (`3314.8310689700002` na principal e `3314.8310689699997` no detalhamento). Não houve ajuste desses valores.

O detalhamento também confirma sinal negativo em dezembro/2025: **−499,42247353999994 R$ milhões** na principal. Por isso, a primeira análise conservará o sinal publicado e não tratará reconhecimento como necessariamente positivo. As notas `3/` e `4/` da aba `Rec Div` referem-se, respectivamente, a títulos estaduais e municipais; não esclarecem nem corrigem a chamada homônima da tabela principal.

**Resultado e consequência concreta:** não foi localizada, nas fontes oficiais consultadas, errata que resolva a referência `3/` da linha 22 da aba mensal principal. A incerteza sobre essa chamada permanece. Entretanto, o nome, a unidade, o total independente no detalhamento e as identidades mensais permitem usar a linha como **“Reconhecimento de dívidas — conforme publicado pelo BCB”** na decomposição contábil mensal. Não se deve aplicar a ela a fórmula de efeito do PIB, redistribuí-la entre juros/emissões ou atribuir seu valor a um evento específico sem evidência adicional. Essa ressalva **não bloqueia a coleta nem o uso descritivo do agregado mensal**, mas limita explicações sobre sua composição e origem. A parte de reconhecimento relativa ao PIB é a linha 40; o efeito do denominador permanece separado na linha 43.

Não se declara que o BCB confirmou um erro editorial. O que está confirmado é a inconsistência entre a chamada e o conteúdo da nota e a compatibilidade dos totais mensais entre duas apresentações oficiais.

### Escopo e pendências para a primeira entrega

A primeira entrega usará **saldos e fatores mensais de janeiro/2023 a setembro/2026**, mantendo o agregado cambial, sem abrir seus subcomponentes. Para a decomposição monetária: linhas **16, 17, 18, 21, 22 e 23**. Para a mudança da relação dívida/PIB: correspondentes **34, 35, 36, 39, 40 e 41**, com o efeito do PIB da **43**, distinguindo proporção do PIB e contribuição em p.p. conforme explicado acima.

**Acumulados no ano e análises de subcomponentes ficam fora do escopo inicial.** Os exemplos acumulados já registrados são inspeções limitadas, não validação de suas convenções. Não serão transformados nem utilizados na primeira entrega.

| Grupo | Verificação ou pendência | Estado e consequência |
|---|---|---|
| Essencial mensal | 45 competências SGS, ausência de duplicações e valores inválidos | Resolvida para ambas as séries no intervalo consultado. |
| Essencial mensal | Compatibilidade das competências e saldos com a aba mensal | Resolvida: 45 competências comuns e 90 saldos compatíveis a duas casas. |
| Essencial mensal | Componentes independentes, unidades, sinais e identidades mensais | Resolvida para o conjunto selecionado, com resíduos explicitados e sem dupla contagem. |
| Essencial mensal | Tratamento da nota de reconhecimento de dívidas | Suficiente para uso do agregado publicado com ressalva; chamada original não resolvida por errata oficial. Não atribuir operações ou causas específicas. |
| Essencial na próxima coleta | Manter as versões consultadas e repetir controles após eventual revisão | A executar na coleta; hashes e consultas documentados. A forma de versionar dados ainda será decidida. |
| Decisão de escopo | Dezembro/2022 como referência auxiliar | Continua proposta pendente. Não bloqueia usar o saldo e a variação de janeiro já publicados. |
| Futuro, fora do escopo inicial | Convenções dos acumulados e conversões entre mensal/acumulado | Não validadas integralmente; não usar na primeira entrega. |
| Futuro, fora do escopo inicial | Subcomponentes cambiais e detalhamento por instrumentos/entes | Leitura e validação completas pendentes; usar apenas o agregado cambial na primeira entrega. |
| Futuro, interpretação aprofundada | Corrigir/esclarecer oficialmente a nota e explicar eventos de reconhecimento | Pendente; necessária para atribuições mais específicas, sem bloquear o agregado mensal. |

**Conclusão:** podemos iniciar a coleta dos saldos SGS e dos fatores mensais selecionados para os 45 meses, com a ressalva de reconhecimento preservada e controles de versão. Não há bloqueio técnico ou incompatibilidade de dados identificado para esse escopo. Isso é um mapeamento suficiente para a primeira entrega, **não validação completa de todas as apresentações da fonte**.

### Histórico das verificações anteriores

A instalação isolada de `xlrd`, a leitura do XLS legado, a localização do XLSX atual e a conciliação de setembro/2026 foram preservadas nesta documentação e não repetidas sem necessidade. A investigação atual reutilizou o arquivo principal e acrescentou as consultas SGS do intervalo completo, a comparação entre fontes e a inspeção direcionada de reconhecimento de dívidas. Não houve nova instalação, criação de notebook ou implementação do pipeline definitivo.

## Decisões para a etapa seguinte

1. Manter as unidades originais registradas; converter apenas na apresentação, com rótulos explícitos. Diferenças entre percentuais do PIB são expressas em pontos percentuais (p.p.), distintas de taxas de crescimento percentual.
2. Não somar saldos mensais para obter “dívida anual”. Usar saldo de fim do período para esse propósito; em 2026, indicar o mês efetivamente disponível.
3. Na primeira entrega, usar somente a aba mensal e os componentes selecionados. Acumulados e subcomponentes ficam fora do escopo; suas convenções não foram declaradas validadas.
4. A próxima coleta poderá usar o mapeamento mensal suficiente, mantendo as ressalvas e repetindo os controles em cada versão obtida. Não foi implementado pipeline; validação completa de todas as apresentações permanece fora desta conclusão.
5. Decidir posteriormente quais dados serão versionados. Os arquivos temporários de verificação ficaram em `/tmp`, fora do repositório; os exemplos acima são evidências documentais pontuais.
