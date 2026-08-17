# FECIPAN 2026

Projetos da **E. E. Júlia Gonçalves Passarinho** (Corumbá/MS) para a **Feira de Ciência e Tecnologia do Pantanal em Corumbá (FECIPAN)**, IFMS Campus Corumbá, 08 e 09 de outubro de 2026.

Itinerário Profissional de Informática / Ciência de Dados · Edital nº 056/2026 – PROPI/IFMS

---

## Projetos

| Projeto | Do que se trata |
|---|---|
| **ClassMonitor** | Chamada escolar automatizada por reconhecimento facial. 3º colocado na FETEC/MS 2025 como proposta; esta é a etapa do protótipo funcional |
| [**Berrante**](projeto-berrante/) | Coleira sensora no gado detecta queimada e alerta a sede da fazenda — o rebanho como rede de sensores móveis |
| [**Cordilheira**](projeto-cordilheira/) | Página web de prevenção a queimadas no Pantanal, com quiz pré e pós-uso medindo o ganho de aprendizagem |
| [**Elo**](projeto-elo/) | Aplicativo que integra rotinas em uma base única, para que a IA opere sobre os dados cruzados entre áreas |
| [**Vozes do Pantanal**](projeto-vozes-do-pantanal/) | Memória local e práticas de linguagem, nível Fundamental |

Cada pasta traz o resumo expandido em markdown, `.docx` e `.pdf`, além da figura do resumo.

## ClassMonitor: como funciona

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
| `projeto-*/` | Uma pasta por projeto, com o resumo expandido e o material da banca |

## Trabalhando em outra máquina

```bash
git clone https://github.com/pecinn/fecipan-2026.git
cd fecipan-2026
```

O arquivo `CLAUDE.md` carrega todo o contexto automaticamente ao abrir o Claude Code na pasta.

Rotina diária: `git pull` ao começar, `git add` + `git commit` + `git push` ao terminar.
