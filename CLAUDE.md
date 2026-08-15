# FECIPAN 2026 — Projeto ClassMonitor

> Este arquivo é o contexto do projeto. É lido automaticamente ao abrir o Claude Code
> nesta pasta, em qualquer máquina. Mantenha atualizado — o histórico de conversas
> **não** sincroniza entre o PC de mesa e o notebook; este arquivo sim.

---

## Quem

**João Felipe Moreira de Souza** — coordenador e professor na **E. E. Júlia Gonçalves Passarinho**, Corumbá/MS. Itinerário Profissional de Informática / Ciência de Dados (Banco de Dados, Visão Computacional, Algoritmos, Programação, Python).

Equipe prevista: 4 estudantes bolsistas + orientador. Idioma de trabalho: **português do Brasil**.

## O que

Construir o **protótipo funcional do ClassMonitor** — sistema de chamada escolar automatizada por reconhecimento facial — para apresentar na **FECIPAN**.

O ClassMonitor foi **3º colocado na FETEC/MS em 2025** como proposta (projeto Fundect, área "Cidades Inteligentes"). Agora a meta é o artefato funcionando, com dados medidos.

## Onde e quando

- **Feira:** FECIPAN — Feira de Ciência e Tecnologia do Pantanal em Corumbá, IFMS Campus Corumbá
- **Datas do evento:** 08 e 09/10/2026
- **Edital:** nº 056/2026 – PROPI/IFMS
- **Contato:** fecipan@ifms.edu.br
- **Modelos:** Anexo 1.3 (resumo expandido) e Anexo 2.3 (banner)

Detalhamento completo em [`00-edital/`](00-edital/):
- `edital-056-2026-resumo-operacional.md` — regras, prazos, critérios de avaliação, premiação
- `estrutura-resumo-expandido.md` — formatação do resumo e o conflito entre o edital e o modelo da feira

---

## Decisões já tomadas

| Decisão | Detalhe |
|---|---|
| **Cenário de demonstração** | Reconhecer **várias pessoas ao mesmo tempo**, simulando uma sala de aula — não uma pessoa por vez |
| **Painel da gestão** | Acessível de outro computador na rede da escola, não só do notebook do protótipo |
| **Processamento** | 100% local, offline. Nenhuma imagem ou embedding sai da máquina |
| **Arduino** | Opcional e secundário. Se entrar, é como feedback físico (LED/display/buzzer), não como sensor de identificação |
| **Sincronização** | Git + GitHub privado. Código versionado; dados de pessoas ficam locais |

## Stack pretendida

- **Python** + **OpenCV** (câmera) + **InsightFace** (detecção e reconhecimento, roda em CPU)
- **SQLite** para o banco de presença
- **FastAPI** ou **Streamlit** para o painel da gestão
- **Pandas / Matplotlib** para os relatórios e a análise — conteúdo do próprio itinerário

Pipeline: captura → detecção de rostos → embedding (512-d) → comparação por similaridade de cosseno contra os cadastrados → decisão por limiar → registro no banco com regras de negócio (tolerância de atraso, debounce, entrada/saída).

---

## Restrição inegociável: LGPD e ética

**Rosto é dado pessoal sensível** (LGPD art. 5º, II). Os titulares são **menores de idade** (art. 14 — exige consentimento específico e destacado de pai/mãe ou responsável). Além disso, o **item 4.3 do edital** exige respaldo de Comitê de Ética **antes do início das atividades**, com parecer anexado ao resumo em arquivo único (4.3.4).

**Estratégia adotada:** desenvolver e medir o protótipo com **a própria equipe e voluntários maiores de idade com termo de consentimento assinado**. A aplicação em turmas reais fica como continuidade condicionada à aprovação ética, descrita nas Considerações Finais.

**Privacy by design como diferencial do projeto**, não como obstáculo:
- Armazenar **apenas o embedding**, nunca a fotografia
- Processamento local, sem nuvem
- `.gitignore` bloqueia fotos, embeddings, banco e termos assinados desde o primeiro commit

> **Regra prática:** se um arquivo contém ou deriva do rosto de uma pessoa real, ele não entra no Git. Sem exceção.

## O que precisa ser medido

O item 5.3.2 do edital **prioriza trabalhos com resultados parciais ou finais**. Protótipo que funciona é demonstração; protótipo medido é pesquisa. Coletar:

- Acurácia de identificação: acertos, falsos positivos, falsos negativos em N tentativas
- Desempenho com variação: óculos, iluminação natural vs. artificial, ângulo, distância
- **Tempo de chamada manual vs. automatizada** (cronometrado) — o número mais convincente para a gestão
- Robustez a spoofing: o sistema aceita uma foto exibida no celular?

Esses dados alimentam "Resultados e Análise" com tabela e gráfico reais.

---

## Pendências abertas

- [ ] **Datas da Etapa 01/02/03 da FECIPAN** — vêm em edital específico do campus (item 9.1), publicado em https://selecao.ifms.edu.br/. O edital geral só diz "a partir de 15/07/2026". Isso define todo o cronograma para trás. **Verificar antes de qualquer outra coisa.**
- [ ] Baixar o Anexo 1.3 (`.docx`) e o Anexo 2.3 (`.pptx`) da Central de Seleção
- [ ] **Instalar Python** — não está instalado em nenhuma das máquinas até agora
- [ ] Definir a área do item 3.7: provavelmente **CET (Ciência da Computação)** ou **MDIS**; decidir considerando concorrência e as categorias especiais "inovação tecnológica" e "impacto socioambiental"
- [ ] Declarar Tipo de Pesquisa — provável **Tecnológica** (a grade do item 7.4-II cobra protótipo, viabilidade técnica e custo-benefício)
- [ ] Redigir termo de consentimento para os voluntários
- [ ] **Iniciar o caderno de campo manuscrito** — obrigatório, avaliado, cronológico, e não dá para reconstruir depois

---

## Estrutura do repositório

```
FECIPAN/
├── CLAUDE.md              ← este arquivo
├── 00-edital/             documentos de referência do edital
├── 01-ideias/             concepção, escopo, decisões de projeto
└── 02-resumos/            resumo expandido, banner, relatório
```

## Convenções

- Documentação e código em **português**
- Commits em português, no imperativo ("adiciona painel", "corrige limiar")
- Nada de dado pessoal real em commit — conferir o `.gitignore` antes de `git add`
