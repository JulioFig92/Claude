# Claude — motor do segundo cérebro

Este repositório guarda **as regras e o protocolo** do segundo cérebro, que é processado por três IAs em etapas:

| Etapa | Quem | Papel | Tipo de dado |
|---|---|---|---|
| 1 | **Claude** (Claude Code) | Recebe o material cru, separa, categoriza, cataloga e propõe conexões | "Grosso": tudo o que chega na Entrada |
| 2 | **Codex** (ChatGPT) | Refina, confere e cuida do que é mais delicado | "Fino": o que já foi triado |
| 3 | **Gemini Spark** + **Gemini Notebook** | Transforma em tarefas, agenda e estudo; integra tudo | O que já foi aprovado |
| Reserva | **Antigravity** | Assume quando alguém fica sem cota; leituras longas; scripts | Conforme a etapa que assumir |
| Bancada | **VS Code** + **GitHub Desktop** | Você vê, revisa e aprova o que as IAs mudaram | — |

Quem faz o quê, em que horário e como respeitar a janela de 5 horas e o teto semanal de cada uma:
[`docs/orquestracao.md`](docs/orquestracao.md).

> **Este repositório é público.** Nenhum dado pessoal, pensamento, conversa ou nome de pessoa entra aqui.
> Os dados circulam só pelo Google Drive (pasta `Segundo Cérebro`). Aqui ficam apenas regras, modelos e scripts.

## Arquivos

- [`docs/fluxo.md`](docs/fluxo.md) — como os dados passam de uma IA para outra, pastas do Drive, permissões e instruções para o Spark.
- [`docs/orquestracao.md`](docs/orquestracao.md) — roteamento, rotina diária e semanal, cotas, contingência e fases de implantação.
- [`CLAUDE.md`](CLAUDE.md) — regras que o Claude segue ao processar.
- [`AGENTS.md`](AGENTS.md) — regras que o Codex segue ao trabalhar neste projeto.
- [`GEMINI.md`](GEMINI.md) — regras do Antigravity / Gemini como reserva.
- [`templates/nota-processada.md`](templates/nota-processada.md) — formato de cada nota que sai da etapa 1.
- [`templates/painel-de-cotas.md`](templates/painel-de-cotas.md) — planilha onde cada IA registra quanto gastou.
