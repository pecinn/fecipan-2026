# Projeto Berrante — Resumo Expandido (conteúdo do Anexo 1.3)

> Campos entre `[colchetes]` precisam ser preenchidos.
> **A Tabela 1 (custo) pode ser preenchida hoje**, pesquisando preço de componente. É o que garante "resultado parcial" na submissão de amanhã.

---

## Cabeçalho

**Título:** BERRANTE: COLEIRA SENSORA DE BAIXO CUSTO PARA DETECÇÃO PRECOCE DE QUEIMADAS NO PANTANAL A PARTIR DO REBANHO BOVINO

**Autores:** Antony Melgar, [Estudante 2], [Estudante 3], [Estudante 4], João Felipe Moreira de Souza

**Instituição:** Escola Estadual Júlia Gonçalves Passarinho – Corumbá-MS

**Área/Subárea:** CAE – Engenharias · **Tipo de Pesquisa:** Tecnológica

**Palavras-chave:** detecção de queimadas, sensores de baixo custo, Pantanal

---

## Introdução

Os incêndios no Pantanal se repetem a cada ano. Em 2020, a área queimada no bioma foi 376% superior à média registrada entre 2003 e 2019 (GARCIA et al., 2021), no episódio descrito como o maior desastre por fogo já observado na região (LIBONATI et al., 2020). Pletsch et al. (2021) associam o evento à combinação entre a maior seca em sessenta anos e a fragilização das políticas ambientais.

O fator que determina se um foco se torna um incêndio de grandes proporções é o **tempo até a detecção**. O monitoramento disponível hoje opera em duas escalas, ambas com limitações. O sensoriamento por satélite cobre todo o bioma, mas depende do intervalo de revisita e de um tamanho mínimo de foco para registro. Torres fixas de observação e estações meteorológicas oferecem detecção local, porém cobrem um ponto e exigem instalação, energia e manutenção em uma planície onde as distâncias são enormes e a cobertura de telefonia é escassa.

Entre essas duas escalas existe uma lacuna: áreas de centenas de quilômetros quadrados sem qualquer sensor no nível do solo, justamente onde o fogo começa pequeno.

Este trabalho parte de uma constatação sobre o próprio território. Corumbá possui o segundo maior rebanho bovino do Brasil, com mais de 2,1 milhões de cabeças, o equivalente a cerca de 38,8% do rebanho do bioma Pantanal (IBGE, 2024). Esses animais já estão distribuídos exatamente sobre as áreas que queimam, deslocam-se por conta própria e são visitados regularmente pelo manejo da fazenda. **A hipótese é que o rebanho pode funcionar como uma rede de sensores móveis**, dispensando a instalação de infraestrutura fixa: o portador do sensor já existe.

O projeto considera dois indícios complementares. O primeiro são os **gases de combustão** próximos ao solo, detectáveis antes de o foco atingir tamanho visível por satélite. O segundo é comportamental: **bovinos fogem do fogo**, de modo que um deslocamento coletivo anômalo do rebanho é, em si, um indicador de ocorrência.

**Objetivo geral:** desenvolver e avaliar um protótipo de coleira sensora de baixo custo, capaz de detectar indícios de combustão e transmitir alerta com localização, sem depender de cobertura de internet.

**Objetivos específicos:** (a) levantar as limitações do monitoramento atual de queimadas na região; (b) construir o protótipo com sensores de gases, temperatura, umidade e posicionamento; (c) implementar rádio de longo alcance para transmissão sem internet; (d) treinar um classificador que separe indício de combustão de variação normal do ambiente; (e) medir tempo de resposta e alcance de detecção em ensaios controlados; e (f) analisar o custo unitário em comparação com alternativas de monitoramento.

## Metodologia

Pesquisa aplicada de natureza tecnológica, desenvolvida em cinco etapas.

**Etapa 1 – Requisitos.** Levantamento das limitações do monitoramento atual e definição dos requisitos do dispositivo: baixo custo, autonomia energética, operação sem internet e resistência ao uso em campo.

**Etapa 2 – Protótipo.** Montagem do circuito com microcontrolador, sensor de gases de combustão, sensor de temperatura e umidade, módulo de posicionamento por satélite, rádio de longo alcance, LED indicador e alimentação por bateria com painel solar. A arquitetura está descrita na Figura 1.

**Etapa 3 – Classificador.** Os dados dos ensaios alimentam um modelo que decide se a leitura corresponde a um foco ou a variação normal do ambiente. O modelo é treinado com as leituras registradas pelo próprio grupo e executado na base receptora, não na coleira.

**Etapa 4 – Ensaios controlados.** Queima controlada de material vegetal em recipiente metálico, em área aberta e segura, com o protótipo fixado em suporte às distâncias de 1, 3, 5 e 10 metros, com 10 repetições por distância. Mede-se o tempo entre o início da queima e a emissão do alerta, e a taxa de detecção. A taxa de alarme falso é medida em [XX] horas de operação contínua sem fogo.

**Etapa 5 – Análise de custo.** Levantamento do custo unitário dos componentes e comparação com alternativas de monitoramento.

**Procedimentos éticos e de segurança.** O protótipo **não é testado em animais**: em todos os ensaios o dispositivo permanece fixado em suporte. A aplicação em rebanho real fica condicionada à aprovação do Comitê de Ética no Uso de Animais (CEUA/IFMS), conforme o item 4.3 do edital, e está descrita como continuidade. As queimas controladas ocorrem exclusivamente em ambiente próprio e supervisionado; o estande da feira não exibe fogo, chama ou fumaça, em atendimento ao item 6.6.3.

## Resultados e Análise

O custo unitário do protótipo foi levantado a partir do preço dos componentes, conforme a Tabela 1.

**Tabela 1. Custo unitário estimado do protótipo**

| Componente | Função | R$ |
|---|---|---|
| Microcontrolador | processamento e rádio | [XX] |
| Sensor de gases | indício de combustão | [XX] |
| Sensor de temp./umidade | contexto ambiental | [XX] |
| Módulo GPS | posição e movimento | [XX] |
| Rádio de longo alcance | envio sem internet | [XX] |
| Bateria e painel solar | autonomia | [XX] |
| Invólucro e diversos | proteção em campo | [XX] |
| **Total por unidade** | | **[XX]** |

Fonte: Próprio Autor (2026)

Nos ensaios controlados, o sistema detectou a queima em [XX] das 10 repetições a 1 metro e em [XX] das 10 a [XX] metros, com tempo médio de alerta de [XX] segundos. A partir de [XX] metros a detecção [descrever comportamento]. Em [XX] horas de operação sem fogo, registraram-se [XX] alarmes falsos.

O custo por unidade permite equipar [XX] animais pelo valor de [comparação], o que indica que a cobertura por rebanho é economicamente viável em propriedades onde a instalação de torres fixas não é.

## Considerações Finais

Os resultados obtidos sustentam a viabilidade técnica do dispositivo em ensaio controlado e permitem discutir a proposta central: usar um portador que já existe no território, em vez de instalar infraestrutura nova.

Cabe delimitar o alcance. Os ensaios foram realizados em condição controlada, sem vento significativo e com fonte de fumaça pequena, o que não reproduz a dispersão de gases em campo aberto. A autonomia energética não foi avaliada em uso prolongado. O componente de detecção por movimentação anômala do rebanho foi modelado, porém não validado com animais, uma vez que o projeto não realizou testes em bovinos. O custo apurado refere-se a unidades avulsas, sem ganho de escala.

Como continuidade, propõem-se o ensaio em campo aberto com medição de vento, a avaliação de autonomia em ciclo completo, a submissão do protocolo à CEUA/IFMS para validação com animais e o teste de alcance efetivo do rádio na planície.

## Referências

- GARCIA, Letícia Couto *et al.* Record-breaking wildfires in the world's largest continuous tropical wetland: integrative fire management is urgently needed for both biodiversity and humans. **Journal of Environmental Management**, v. 293, art. 112870, 2021. DOI: 10.1016/j.jenvman.2021.112870.
- DAMPAGE, Udaya *et al.* Forest fire detection system using wireless sensor networks and machine learning. **Scientific Reports**, v. 12, 2022. DOI: 10.1038/s41598-021-03882-9.
- INSTITUTO BRASILEIRO DE GEOGRAFIA E ESTATÍSTICA. **Pesquisa Pecuária Municipal 2023.** Rio de Janeiro: IBGE, 2024.
- INSTITUTO NACIONAL DE PESQUISAS ESPACIAIS. **Programa Queimadas: banco de dados de queimadas.** São José dos Campos: INPE, 2026. Disponível em: https://terrabrasilis.dpi.inpe.br/queimadas/. Acesso em: [dia] [mês] 2026.
- LIBONATI, Renata; DACAMARA, Carlos C.; PERES, Leonardo F.; CARVALHO, Lino A. Sander de; GARCIA, Letícia C. Rescue Brazil's burning Pantanal wetlands. **Nature**, v. 588, n. 7837, p. 217-219, 2020. DOI: 10.1038/d41586-020-03464-1.
- PLETSCH, Mikhaela A. J. S. *et al.* The 2020 Brazilian Pantanal fires. **Anais da Academia Brasileira de Ciências**, v. 93, n. 3, art. e20210077, 2021. DOI: 10.1590/0001-3765202120210077.

> Conferir o número do artigo de Dampage et al. na página do periódico antes de submeter.

---

## Pendências

- [ ] **Hoje:** preencher a Tabela 1 com preços reais de componente — é o resultado parcial que sustenta a submissão de amanhã
- [ ] Nomes e e-mails dos outros três estudantes
- [ ] Confirmar as datas no edital específico (selecao.ifms.edu.br)
- [ ] Até setembro: montar o protótipo e rodar os ensaios das distâncias
- [ ] **Não testar em animais** sem parecer da CEUA/IFMS
- [ ] Iniciar o caderno de campo manuscrito (item 6.2)
