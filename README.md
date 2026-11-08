# Claude — motor do segundo cérebro

Este repositório guarda **as regras e o protocolo** do segundo cérebro, que é processado por três IAs em etapas:

| Etapa | Quem | Papel | Tipo de dado |
|---|---|---|---|
| 1 | **Claude** (Claude Code) | Recebe o material cru, separa, categoriza, cataloga e propõe conexões | "Grosso": tudo o que chega na Entrada |
| 2 | **Codex** (ChatGPT) | Refina, confere e cuida do que é mais delicado | "Fino": o que já foi triado |
| 3 | **Gemini Spark** + **Gemini Notebook** | Transforma em tarefas, agenda e estudo; integra tudo | O que já foi aprovado |

> **Este repositório é público.** Nenhum dado pessoal, pensamento, conversa ou nome de pessoa entra aqui.
> Os dados circulam só pelo Google Drive (pasta `Segundo Cérebro`). Aqui ficam apenas regras, modelos e scripts.

## Arquivos

- [`docs/fluxo.md`](docs/fluxo.md) — como os dados passam de uma IA para outra, pastas do Drive, permissões e instruções para o Spark.
- [`CLAUDE.md`](CLAUDE.md) — regras que o Claude segue ao processar.
- [`AGENTS.md`](AGENTS.md) — regras que o Codex segue ao trabalhar neste projeto.
- [`templates/nota-processada.md`](templates/nota-processada.md) — formato de cada nota que sai da etapa 1.
