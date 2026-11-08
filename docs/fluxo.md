# Fluxo do segundo cérebro

## Visão geral

```
 Você (voz, texto, foto, áudio)
        │
        ▼
 Drive: Segundo Cérebro/00 Entrada ............ material cru, sem organizar
        │
        ▼  ETAPA 1 — Claude
 Drive: Segundo Cérebro/10 Triado (Claude) .... notas catalogadas + índice + pendências
        │
        ▼  ETAPA 2 — Codex
 Drive: Segundo Cérebro/20 Refinado (Codex) ... notas conferidas e aprovadas por você
        │                                         └─► Obsidian (cofre), só com sua aprovação
        ▼  ETAPA 3 — Gemini Spark + Gemini Notebook
 Drive: Segundo Cérebro/30 Ação (Spark) ....... tarefas, agenda, resumos de estudo

 Drive: Segundo Cérebro/90 Pedidos ............ fila de ordens para qualquer etapa
```

O **Google Drive é o barramento comum**: é o único lugar que as três IAs conseguem ler e escrever.
Spark e Gemini Notebook leem o Drive nativamente; o ChatGPT/Codex lê pelo conector do Drive;
o Claude lê e cria arquivos pelo conector do Drive.

## Pastas

| Pasta | Quem escreve | Quem lê | Conteúdo |
|---|---|---|---|
| `00 Entrada` | Você, Spark (por e-mail), qualquer IA | Claude | Qualquer coisa crua: transcrições de voz, anotações, prints, PDFs |
| `10 Triado (Claude)` | Claude | Codex, você | Uma nota por ideia, no formato do modelo; `Índice.md`; `Pendências.md` |
| `20 Refinado (Codex)` | Codex | Spark, Gemini Notebook, você | Notas conferidas e aprovadas |
| `30 Ação (Spark)` | Spark | Você | Tarefas, compromissos, resumos |
| `90 Pedidos` | Você, Codex, Spark | Claude | `Pedidos para o Claude` — uma linha por ordem |
| `99 Arquivo cru` | Claude | — | Originais já processados (nunca apagados) |

## Como dar ordens ao Claude a partir de outra IA

Qualquer etapa pode escrever no documento `90 Pedidos/Pedidos para o Claude`, uma ordem por linha:

```
- [ ] 2026-11-08 | de: Codex | processar a Entrada e separar o que é Civil III
- [ ] 2026-11-08 | de: Spark | criar nota de estudo sobre responsabilidade civil
```

O Claude lê essa fila quando roda (manualmente ou por tarefa agendada), executa e marca `- [x]` com o resultado.

## Permissões que o Claude precisa

| Permissão | Para quê | Situação |
|---|---|---|
| Google Drive (conector) | Ler a Entrada, criar notas e índices | **Ativo.** Pode ler e criar arquivos novos; não edita os arquivos existentes |
| GitHub `JulioFig92/Claude` | Guardar regras e scripts | **Ativo** (repositório público: só regras, nunca dados) |
| Gmail (conector) | Ler material enviado por e-mail; mandar pedidos para o Spark | Disponível; usar só com sua autorização |
| Google Agenda (conector) | Ver compromissos ligados às notas | Disponível; leitura |
| Tarefa agendada | Processar a Entrada sozinho, por exemplo 2× por dia | Só com sua autorização |
| Cofre do Obsidian (iCloud, no Mac) | Escrever direto no cofre | **Sem acesso.** Caminho: o Codex aplica no cofre o que você aprovar, ou o cofre passa a sincronizar uma cópia com o Drive |

## Instruções para colar no Gemini Spark

> Você é a etapa 3 do meu segundo cérebro. Trabalhe só com a pasta do Google Drive
> "Segundo Cérebro/20 Refinado (Codex)".
> 1. Toda nota com tarefas (`- [ ]`) ou datas vira tarefa ou evento na minha Agenda, com link para a nota.
> 2. Escreva um resumo semanal em "Segundo Cérebro/30 Ação (Spark)".
> 3. Quando precisar que algo seja reprocessado, escreva uma linha em
>    "Segundo Cérebro/90 Pedidos/Pedidos para o Claude", no formato
>    `- [ ] AAAA-MM-DD | de: Spark | pedido`.
> 4. Não altere arquivos das pastas 00, 10 e 20.
> 5. Respeite a autoria: o que foi dito ou pensado por outra pessoa nunca é atribuído a mim.

## Gemini Notebook (antigo NotebookLM)

Crie um notebook por área (por exemplo, "Civil III") e adicione como fonte os documentos da pasta
`20 Refinado (Codex)`. Fontes do Drive se mantêm sincronizadas. Prefira **Google Docs** como formato
das notas refinadas, porque é o formato que o Notebook aceita melhor.

## Regras que valem para todas as etapas

1. **Autoria**: pensamentos e falas de outra pessoa nunca são atribuídos a você. Autoria incerta fica marcada como incerta.
2. **Aprovação**: nada derivado dos seus pensamentos entra no cofre do Obsidian sem você aprovar o texto.
3. **Nada é apagado**: originais vão para `99 Arquivo cru`.
4. **Sem invenção**: síntese não é transcrição; datas e fatos que não estão na fonte não são criados.
5. **Dados fora do Git**: nada pessoal entra neste repositório.
