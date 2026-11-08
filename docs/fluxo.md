# Fluxo do segundo cérebro

Decisões que definem este fluxo: [`decisoes.md`](decisoes.md).

## Visão geral

```
 VOCÊ fala por voz
   │
   ▼  CAPTURA — ChatGPT / Codex
 00 Entrada ................. pacote de voz: transcrição + resumo (+ PDFs, prints, anotações)
   │
   ▼  FORÇA BRUTA (antes) — Gemini Spark
 05 Pré-processado (Spark) .. volume pesado já separado por assunto, sem interpretar
   │
   ▼  CENTRO — Claude  (refina, marca natureza e autoria, faz as conexões principais)
 10 Refinado (Claude) ....... todas as notas refinadas + Índice + Sugestões de conexão
   ├──► 20 Aprovado ........... estudo e tarefas passam direto
   └──► 15 Para aprovar ....... pensamentos pessoais esperam você
           │
           ▼  APROVAÇÃO — você, por voz no ChatGPT
         20 Aprovado .......... Codex move o que você aprovou e grava no Obsidian
   │
   ▼  FORÇA BRUTA (depois) — Gemini Spark + Gemini Notebook
 30 Ação (Spark) ............ tarefas, agenda, briefing diário, pesquisas de apoio
                              └─► pesquisa volta para 00 Entrada → Claude refina

 90 Pedidos e cotas ......... pedidos entre as IAs + relatórios de cada rodada
 99 Arquivo cru ............. originais já processados (nada é apagado)
```

## Pastas no Google Drive (`Meu Drive/Segundo Cérebro`)

| Pasta | Quem escreve | Quem lê | Conteúdo |
|---|---|---|---|
| `00 Entrada` | Codex (voz), você, Spark (pesquisas) | Spark, Claude | Material cru |
| `05 Pré-processado (Spark)` | Spark | Claude | Volume pesado separado por assunto; transcrições longas quebradas em partes |
| `10 Refinado (Claude)` | Claude | Codex, você | Notas refinadas, `Índice`, `Sugestões de conexão` |
| `15 Para aprovar` | Claude | ChatGPT (lê por voz), Codex | Notas de pensamento pessoal aguardando você |
| `20 Aprovado` | Claude (estudo/tarefas), Codex (após aprovação) | Spark, Gemini Notebook, Codex | Tudo o que está liberado |
| `30 Ação (Spark)` | Spark | Você, Claude | Briefings, tarefas, resultados de pesquisa |
| `90 Pedidos e cotas` | Todos | Todos | `Pedidos abertos/`, `Pedidos atendidos/`, `Relatórios de rodada/` |
| `99 Arquivo cru` | Claude, Spark | — | Originais já processados |

**Por que mover em vez de editar:** o conector do Drive que o Claude usa cria e move arquivos, mas não edita o conteúdo
de arquivos existentes. Por isso, no sistema todo, **o estado de um arquivo é a pasta em que ele está**:
aprovar = mover de `15` para `20`; pedido atendido = mover de `Pedidos abertos` para `Pedidos atendidos`.
Índice e Sugestões são recriados a cada rodada com a data no nome; a versão anterior vai para `99 Arquivo cru`.

## Pacote de voz (o que o Codex salva em `00 Entrada`)

Um arquivo por conversa, nome `Voz AAAA-MM-DD HHhMM — <assunto>`. Modelo: [`templates/pacote-de-voz.md`](../templates/pacote-de-voz.md).
Duas partes separadas: **transcrição** (o mais completa possível) e **resumo do ChatGPT**, marcando em cada ponto
se foi **dito por você** ou **sugerido pelo ChatGPT**.

## Pedidos entre as IAs

Cada pedido é **um arquivo** em `90 Pedidos e cotas/Pedidos abertos`, com o nome:

```
Pedido AAAA-MM-DD — de <quem> para <quem> — <prioridade> — <custo P/M/G> — <assunto>
```

O conteúdo explica o pedido. Quem atende move o arquivo para `Pedidos atendidos` e cita o resultado no relatório da rodada.

## Natureza de cada nota

Toda nota refinada recebe **uma** natureza: `imaginação` · `hipótese` · `plano` · `decisão` · `fato`.
Notas de naturezas diferentes podem ficar no mesmo assunto e se conectar, mas a natureza nunca é trocada
sem você dizer. Sem indicação clara na fala, o Claude escolhe a mais conservadora e anota a dúvida.

## Conexões

- **Fortes** (relação clara e justificada) → entram na nota como `[[link]]`, com o motivo e o tipo:
  `aplica` · `contradiz` · `evolui de` · `exemplo de` · `depende de` · `relacionado`.
- **Possíveis** → vão para `10 Refinado (Claude)/Sugestões de conexão AAAA-MM-DD`, para você aprovar por voz.
- Igualdade de palavras não basta.

## O que precisa de aprovação

| Tipo | Caminho |
|---|---|
| Estudo (Faculdade, OAB) e tarefas | **Direto** para `20 Aprovado` |
| Pensamentos, ideias pessoais, imaginação | `15 Para aprovar` → você aprova por voz → `20 Aprovado` |
| Sugestões de conexão | Lista à parte → você aprova por voz → o Codex aplica no cofre |
| Qualquer coisa com autoria incerta | `15 Para aprovar`, sempre |

## Escopo do piloto (1 semana)

Somente **Faculdade** e **Ideias**. Material de Vida pessoal ou Finanças/empresa que chegar à Entrada
**não é processado**: o Claude o deixa na Entrada e cita no relatório.

## Regras que valem para todas as etapas

1. **Autoria**: pensamentos e falas de outra pessoa nunca são atribuídos a você; sugestão do ChatGPT não é pensamento seu. Autoria incerta fica marcada como incerta.
2. **Aprovação**: nada de pensamento pessoal entra no cofre sem você aprovar.
3. **Nada é apagado**: originais vão para `99 Arquivo cru`.
4. **Sem invenção**: síntese não é transcrição; datas e fatos ausentes da fonte não são criados.
5. **Legislação**: conferir em fonte oficial (planalto.gov.br) antes de citar artigo.
6. **Dados fora do Git**: este repositório é público; nada pessoal entra aqui.
