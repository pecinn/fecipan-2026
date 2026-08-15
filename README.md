# ClassMonitor — FECIPAN 2026

Protótipo de sistema de chamada escolar automatizada por reconhecimento facial, desenvolvido para a **Feira de Ciência e Tecnologia do Pantanal em Corumbá (FECIPAN)**, IFMS Campus Corumbá, 08 e 09 de outubro de 2026.

**E. E. Júlia Gonçalves Passarinho** — Corumbá/MS · Itinerário Profissional de Informática / Ciência de Dados

O projeto foi **3º colocado na FETEC/MS 2025** como proposta. Esta é a etapa de construção do protótipo funcional.

---

## Como funciona

Uma câmera observa a sala, identifica os estudantes presentes e registra a frequência automaticamente em um banco de dados, com painel de acompanhamento para a gestão escolar — atrasos, saídas e relatórios de assiduidade.

Todo o processamento é **local e offline**. Nenhuma imagem é armazenada ou transmitida.

## Privacidade

Reconhecimento facial de estudantes envolve **dado pessoal sensível de menores de idade**. Este repositório é privado e não contém — nem deve conter — nenhum dado pessoal real:

- Armazena-se apenas o **embedding** (vetor numérico), nunca a fotografia
- Fotos, embeddings, banco de dados e termos assinados estão bloqueados no [`.gitignore`](.gitignore)
- Testes e medições são feitos com a equipe e voluntários maiores de idade, mediante termo de consentimento

Ver [`CLAUDE.md`](CLAUDE.md) para o detalhamento das restrições de LGPD e do item 4.3 do edital.

## Organização

| Pasta | Conteúdo |
|---|---|
| [`00-edital/`](00-edital/) | Edital 056/2026 destrinchado: regras, prazos, critérios, formatação do resumo |
| [`01-ideias/`](01-ideias/) | Concepção, escopo e decisões de projeto |
| [`02-resumos/`](02-resumos/) | Resumo expandido, banner e relatório |

## Trabalhando em outra máquina

```bash
git clone https://github.com/pecinn/fecipan-classmonitor.git
cd fecipan-classmonitor
```

O arquivo `CLAUDE.md` carrega todo o contexto automaticamente ao abrir o Claude Code na pasta.

Rotina diária: `git pull` ao começar, `git add` + `git commit` + `git push` ao terminar.
