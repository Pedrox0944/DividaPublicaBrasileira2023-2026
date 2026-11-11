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

## Ambiente Python/Jupyter

Ambiente preparado e testado em **11/11/2026**, em Linux x86_64, reutilizando a `.venv` existente com **Python 3.13.16**. Não foi necessário trocar o Python. A `.venv` permanece ignorada pelo Git; nenhum pacote foi instalado globalmente e o ambiente base do Conda não foi modificado.

| Biblioteca | Versão testada | Finalidade |
|---|---|---|
| pandas | 3.1.1 | Organizar e trabalhar com tabelas. |
| Plotly | 7.1.0 | Gerar gráficos interativos. |
| JupyterLab | 4.6.6 | Trabalhar com notebooks. |
| ipykernel | 7.4.0 | Executar células com o Python do projeto. |
| openpyxl | 3.1.5 | Ler e escrever XLSX, formato da fonte atual. |
| requests | 2.34.2 | Preparar a futura coleta por HTTP. |
| xlrd | 2.0.2 | Preservar a leitura do XLS histórico já validado. |

### Reproduzir o ambiente

Na raiz do projeto, com Python **3.13.16** disponível, execute os comandos abaixo. Se a `.venv` já existir e estiver funcional, reutilize-a e pule sua criação. Os comandos usam explicitamente o Python desse ambiente, sem depender de ativação do terminal.

```sh
python3.13 --version
python3.13 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
.venv/bin/python -m pip check
.venv/bin/python -m ipykernel install --prefix .venv --name divida-publica --display-name "Python (.venv - DividaPublica)"
```

[requirements.txt](requirements.txt) registra as versões exatas dos **98 pacotes instalados dentro da `.venv`**, incluindo dependências transitivas e o pip 26.2.1. Foi gerado com `pip freeze --all --path` apontando para o diretório de pacotes da `.venv`. O processo também enxergava `asarPy` em `/app`, fora desse ambiente; ele foi excluído do registro porque não é um pacote instalado no ambiente do projeto. As entradas foram verificadas: contêm somente `nome==versão`, sem caminhos locais, credenciais ou referências temporárias.

Esse registro descreve o conjunto instalado e testado; não é um lockfile com hashes de distribuições e não garante reprodução em outro sistema operacional ou versão de Python. Para alterações futuras nas dependências, atualizar o registro após instalar e testar no ambiente exclusivo. [Referência oficial do pip freeze](https://pip.pypa.io/en/stable/cli/pip_freeze/).

O comando de registro do kernel grava sua configuração apenas em `.venv/share/jupyter/kernels/divida-publica`, sem registro global ou no perfil do usuário. Repita-o ao recriar ou mover a `.venv`, pois o executável registrado depende da localização do ambiente. Esse arquivo gerado fica ignorado junto com a `.venv`.

### Selecionar interpretador e kernel no VS Code

Com a pasta do projeto aberta e as extensões **Python** e **Jupyter**, da Microsoft, disponíveis:

1. Abra a paleta (`Ctrl+Shift+P`), execute **Python: Select Interpreter** e escolha `.venv/bin/python`. Se não aparecer, use **Enter interpreter path** e localize esse arquivo dentro do projeto.
2. Ao abrir um notebook na próxima etapa, clique em **Select Kernel**, no canto superior direito. Se necessário, escolha **Select Another Kernel → Python Environments** e selecione a `.venv` do projeto. Quando o kernel registrado for listado, seu nome será **Python (.venv - DividaPublica)**; confirme o caminho do ambiente.
3. Confira no notebook o valor de `sys.executable`: ele deve apontar para o Python da `.venv` deste projeto. A seleção do interpretador e a seleção do kernel são escolhas separadas.

Essas ações ainda precisam ser confirmadas na interface pelo usuário. Não foi observado o interpretador selecionado, o kernel ativo ou o gráfico renderizado no VS Code. Instruções baseadas na documentação oficial de [ambientes Python](https://code.visualstudio.com/docs/python/environments) e de [seleção de kernels](https://code.visualstudio.com/docs/datascience/jupyter-kernel-management).

Para iniciar o JupyterLab pelo terminal, quando necessário:

```sh
.venv/bin/python -m jupyterlab
```

### Conferência visual no VS Code — pendente

O notebook local `verificacao-visual-ambiente.ipynb`, na raiz do projeto, contém apenas dados fictícios e três células de código: executável Python, tabela pandas e gráfico Plotly. Foi preparado sem execução nem saídas salvas. Ele não acompanha o repositório: a regra `/verificacao-visual-ambiente.ipynb` em `.git/info/exclude` o exclui apenas neste clone, preservando o `.gitignore` compartilhado. A `.venv` continua ignorada pelo `.gitignore`.

Para conferir a interface:

1. Abra `verificacao-visual-ambiente.ipynb` no VS Code.
2. Na paleta (`Ctrl+Shift+P`), use **Python: Select Interpreter** e selecione `.venv/bin/python` deste projeto; se necessário, use **Enter interpreter path**.
3. No canto superior direito do notebook, use **Select Kernel → Select Another Kernel → Python Environments** e selecione a `.venv`. Se aparecer **Python (.venv - DividaPublica)**, confirme que corresponde ao ambiente deste projeto.
4. Clique em **Run All / Executar Tudo**. A primeira célula deve exibir um caminho terminado em `DividaPublica/.venv/bin/python`, dentro da pasta em que este projeto está aberto.
5. Confira a tabela com **Grupo A = 10, Grupo B = 20 e Grupo C = 15**, em unidades fictícias.
6. Confira as três barras do gráfico e passe o mouse sobre elas: o tooltip deve mostrar o grupo e seu valor correspondente.

**Estado:** testes programáticos aprovados na etapa anterior; execução e apresentação visual deste notebook no VS Code ainda pendentes de confirmação do usuário. Preparar o notebook e validar sua estrutura não confirma o kernel selecionado, a tabela visível nem a interação com o gráfico. Se alguma etapa falhar, registrar a célula afetada e a mensagem exibida antes de alterar o ambiente.

### Verificações executadas

- `pip check`: **No broken requirements found**.
- Importações de todas as sete bibliotecas no kernel; seus arquivos e `sys.prefix` foram confirmados dentro da `.venv`.
- Inicialização do kernel registrado no ambiente e execução de **três células**, todas com status `ok`.
- Tabela pandas fictícia com duas linhas, soma conferida e leitura/escrita XLSX em memória com openpyxl.
- Gráfico Plotly criado a partir dessa tabela, gravado em HTML autocontido e emitido pelo kernel como `application/vnd.plotly.v1+json`. A geração foi testada programaticamente; a exibição visual não foi verificada.
- requests importado e uma requisição fictícia preparada, **sem envio HTTP**. O teste não comprova conectividade futura com o BCB.
- JupyterLab respondeu à consulta de versão. Não foi iniciado nem inspecionado um servidor JupyterLab na interface.

O script de teste, o relatório e o gráfico ficaram em `/tmp`, fora dos arquivos versionados; não foi criado notebook de análise. Não houve coleta de dados do BCB nem implementação do pipeline. O ambiente passou nos testes programáticos necessários à primeira coleta; a conferência visual no VS Code permanece pendente. A coleta também deve respeitar as decisões metodológicas e de versionamento registradas neste projeto.

## Situação atual e próxima etapa

O indicador principal, a fonte, a frequência e as medidas foram definidos. O escopo inclui a trajetória e os fatores condicionantes da DBGG, com distinção entre descrição, decomposição contábil e investigação causal.

O [mapeamento de fontes e séries](fontes-e-series.md), consultado em 10/11/2026, está **suficiente para a primeira entrega mensal**, com ressalvas documentadas. Isso não equivale à validação completa de todas as apresentações da fonte.

As séries SGS 13761 e 13762 retornaram os 45 meses de janeiro de 2023 a setembro de 2026, sem ausências, duplicações, competências extras ou valores inválidos. As competências coincidem com as da aba mensal dos fatores; os 90 saldos comparados coincidem ao arredondar a planilha para as duas casas publicadas pelo SGS. Os valores originais foram preservados. Consultas com datas fixas podem retornar valores revisados, por isso os links, a data e os hashes das respostas foram registrados.

Na validação de fontes de 10/11/2026, a `.venv` com Python 3.13.16 e `xlrd` 2.0.2 serviu à leitura do XLS. Em 11/11/2026, ela foi ampliada e testada com as ferramentas descritas na seção de ambiente acima. O XLS legado termina em novembro de 2018; a fonte mensal adequada é o [Facdbp.xlsx atual de Tabelas Especiais](https://www.bcb.gov.br/content/estatisticas/Documents/Tabelas_especiais/Facdbp.xlsx), inspecionado com bibliotecas padrão do Python.

Além da conciliação de setembro de 2026 já documentada, foram conferidas as identidades dos componentes independentes nos 45 meses, com resíduos registrados. O denominador da relação dívida/PIB é o PIB acumulado em 12 meses a preços correntes (SGS 4382). Fatores como proporção do PIB não serão apresentados como variação da razão sem considerar o efeito separado do denominador.

A chamada de nota em reconhecimento de dívidas permanece inconsistente e não foi localizada errata oficial. O manual e a aba mensal `Rec Div` do detalhamento oficial sustentam o uso do **agregado conforme publicado pelo BCB**, com ressalva: seus totais são compatíveis com os da planilha principal nos 45 meses, mas não serão atribuídos a operações ou causas específicas sem novas evidências. Essa incerteza não bloqueia o uso descritivo do agregado mensal.

A primeira entrega usará os saldos e os componentes mensais selecionados, mantendo o ajuste cambial agregado e evitando dupla contagem de subtotais. **Acumulados no ano e subcomponentes ficam fora do escopo inicial; suas convenções não foram validadas integralmente.** As pendências futuras estão separadas das verificações essenciais no documento de fontes.

Podemos iniciar a coleta dos saldos e fatores mensais de janeiro de 2023 a setembro de 2026, sem bloqueio de dados identificado para esse escopo, preservando as versões obtidas e repetindo os controles após revisões. Consultar dezembro de 2022 apenas como referência para calcular a variação de janeiro de 2023 continua proposta pendente de decisão. Nesta inspeção, janeiro foi conferido com a variação já publicada, sem calcular diferença com dezembro de 2022.

Na etapa de mapeamento, foram executados apenas trechos de inspeção e validação. As respostas e planilhas ficaram em pasta temporária; não foi montada a base final, implementado pipeline definitivo ou criado notebook. As instalações posteriores de preparação do ambiente estão registradas acima. A decisão sobre versionamento de dados será tomada posteriormente.

O trabalho será realizado em pequenas entregas, com explicações claras e objetivas. Código de análise será implementado apenas quando solicitado. A decisão sobre quais dados serão versionados será tomada posteriormente.
