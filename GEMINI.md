# Regras para o Google — Gemini Spark, Gemini Notebook e Antigravity

Leia `docs/decisoes.md`, `docs/fluxo.md` e `docs/orquestracao.md`. Responda em português do Brasil.
Se a ferramenta não carregar este arquivo sozinha, cole o trecho correspondente nas instruções dela.

## Crivo da realidade (vale para todas as ferramentas Google)

Antes de usar qualquer fato sobre o dono, consulte `Segundo Cérebro/Fatos vigentes`. Fato ausente: cite fonte e data
e marque "não confirmado". Fontes em conflito: não escolha; peça ao Claude e avise o dono. Ver `docs/fluxo.md`.

## Gemini Spark — força bruta antes e depois do Claude

**Antes (06:00 e 16:00, Brasília):** pegue o que for novo em `Segundo Cérebro/00 Entrada` e grave em
`05 Pré-processado (Spark)`:
- transcreva áudios;
- quebre textos longos em partes por assunto, **sem resumir demais e sem interpretar**;
- extraia o texto de PDFs e imagens;
- mantenha as marcas `[dito pelo dono]` / `[sugerido pelo ChatGPT]` e o nome do arquivo de origem.
Não mova nem apague os originais: o Claude faz isso.

**Depois:**
- **Tarefas e agenda** (13:30 e 21:00): para cada `- [ ]` com data em `20 Aprovado`, crie tarefa ou evento com link para a nota.
- **Briefing** (08:30, por e-mail): agenda do dia, tarefas, quantas notas há em `15 Para aprovar`, último relatório do Claude.
- **Pesquisa de apoio**: atenda os pedidos `para Spark` em `90 Pedidos e cotas/Pedidos abertos`; grave o resultado em
  `00 Entrada` como `Pesquisa AAAA-MM-DD — <assunto>` (com links das fontes) e mova o pedido para `Pedidos atendidos`.
- **Resumo do dia** (23:00) em `30 Ação (Spark)`.
- Depois de cada etapa, escreva um relatório em `90 Pedidos e cotas/Relatórios de rodada`.

**No Mac:** use só as pastas conectadas `Documents/ChatGPT` e o clone deste repositório (este, **só leitura**).
Nunca conecte nem altere o cofre do Obsidian. Nunca grave dados pessoais no repositório: ele é público.

## Gemini Notebook — estudo

Notebook **"Faculdade"** com fontes da pasta `20 Aprovado` (área Faculdade). Gere resumos, áudios e quizzes.
Não é fonte de verdade: o que o Notebook concluir e for útil volta como material novo para `00 Entrada`.

## Antigravity — reserva

1. Quando o Claude ou o Codex ficar sem cota, assuma o papel deles seguindo `CLAUDE.md` ou `AGENTS.md`. Ao substituir o
   Claude, **tudo** vai para `15 Para aprovar`, e a próxima rodada do Claude revisa.
2. Leitura gigante (cofre inteiro, PDFs enormes), sobretudo aos sábados: lista de duplicatas e conexões possíveis → pedido para o Claude.
3. Scripts deste repositório, numa branch `antigravity/…`.

## Regras

As mesmas de `CLAUDE.md` → "Regras invioláveis". O Google executa e pré-processa; **não refina nem decide conexões** —
isso é do Claude. Este repositório é público: nada pessoal entra aqui.
