# Orquestração — todas as ferramentas, respeitando as cotas

Este documento diz **quem faz o quê, quando e com qual reserva**, para que nenhuma ferramenta fique parada
enquanto outra estoura o limite. Complementa [`fluxo.md`](fluxo.md) (pastas e regras de dados).

---

## 1. O elenco

| Ferramenta | Onde roda | O que alcança | Papel principal | Cota |
|---|---|---|---|---|
| **Claude Code** (nuvem, pelo app) | Servidores da Anthropic | Drive, Gmail, Agenda, GitHub | **Etapa 1 — triagem do cru** (o "grosso") | Janela de 5 h + teto semanal |
| **Claude Code** (no Mac, terminal ou VS Code) | Seu Mac | Arquivos locais, inclusive o cofre | Reserva da etapa 1 quando o trabalho precisa de arquivos locais | Mesma cota do Claude acima (é a mesma conta) |
| **Codex** (ChatGPT) | App do Codex / VS Code | Seu Mac, Drive pelo conector | **Etapa 2 — refino, conferência e aplicação no cofre** (o "fino") | Janela de 5 h + teto semanal; créditos extras pagos |
| **Antigravity** (Google) | Seu Mac | Arquivos locais, navegador | **Reserva geral + leitura longa + scripts.** Modelos Gemini (e, conforme o plano, modelos Claude) com cota separada | Janela de 5 h + teto semanal no AI Pro; Ultra sem teto semanal |
| **Gemini Spark** | Nuvem do Google, 24 h | Gmail, Drive, Docs, Agenda | **Etapa 3 — tarefas, agenda, resumos**, trabalha enquanto você dorme | Plano Google AI |
| **Gemini Notebook** (ex-NotebookLM) | Nuvem do Google | Pastas do Drive como fonte | **Estudo** — Civil III, OAB: resumos, áudios, quizzes | Plano Google AI |
| **VS Code** | Seu Mac | Repositório + cofre | **Bancada**: você vê as mudanças lado a lado, com as extensões do Claude Code e do Codex | Sem cota |
| **GitHub Desktop** | Seu Mac | Este repositório | **Portão de aprovação**: puxa o que as IAs fizeram, você revisa e junta | Sem cota |

Cada ferramenta tem **seu próprio estoque de cota**. A ideia central é: **nunca gastar a cota cara num trabalho que a cota barata faz.**

---

## 2. Roteamento — qual ferramenta para cada tipo de tarefa

| Tarefa | Principal | 1ª reserva | 2ª reserva | Por quê |
|---|---|---|---|---|
| Separar e catalogar material cru | Claude (nuvem) | Antigravity (Gemini) | Codex | Volume alto, precisa de cuidado com autoria |
| Ler muito material de uma vez (cofre inteiro, PDF grande) | Antigravity (Gemini) | Gemini Notebook | Claude | Gemini aguenta contexto muito longo |
| Propor conexões entre notas | Claude | Codex | Antigravity | Exige julgamento de contexto |
| Conferir autoria e fidelidade (revisão) | Codex | Claude | — | Revisor deve ser **diferente** de quem escreveu |
| Aplicar no Obsidian (após sua aprovação) | Codex | Claude Code no Mac | Antigravity | Precisa de acesso ao Mac |
| Escrever/consertar scripts do projeto | Antigravity | Codex | Claude | Poupa as cotas de texto |
| Virar tarefa e compromisso | Spark | Claude (com conector da Agenda) | — | Spark está sempre ligado |
| Estudo, resumo em áudio, quiz | Gemini Notebook | Claude | — | É para isso que ele existe |
| Pesquisa de legislação (planalto.gov.br) | Claude | Spark | Codex | Conferir sempre em fonte oficial |
| Aprovação final | **Você** (GitHub Desktop / Drive) | — | — | Nada sobe sem você |

**Regra de ouro da revisão:** quem escreveu não revisa. Se o Claude triou, o Codex confere; se o Codex estiver sem cota,
o Antigravity confere; só em último caso o próprio Claude revisa, e aí a nota continua `status: rascunho`.

---

## 3. Rotina diária — janelas de 5 horas escalonadas

A janela de 5 horas começa **na primeira mensagem**. Por isso, começar todas as ferramentas ao mesmo tempo desperdiça cota:
elas esgotam juntas e renovam juntas. O plano abaixo **escalona** as janelas para sempre haver uma ferramenta com cota cheia.
Os horários são exemplos — ajuste ao seu dia, mantendo o espaçamento.

```
        06h    08h    10h    12h    14h    16h    18h    20h    22h    00h
Spark   ████████████████████████████████████████████████████████████████████  (contínuo)
Claude         [===== Janela A =====]              [===== Janela B =====]
Codex                       [===== Janela A =====]              [== B ==]
Antigrav.            ( reserva — entra quando alguém fica vermelho )
Você     ☕ briefing        ✔ aprova            ✔ aprova            🔀 GitHub Desktop
```

| Horário | Quem | O que faz | Duração alvo |
|---|---|---|---|
| **06:30** | Spark | Briefing do dia em `30 Ação (Spark)`: agenda, tarefas vencendo, o que chegou na Entrada | automático |
| **08:00** | Claude — Janela A | Lê `90 Pedidos` + **só os arquivos novos** da Entrada; tria em lote; atualiza Índice e Pendências; registra no Painel | até ~60% da janela |
| **11:00** | Codex — Janela A | Revisa as notas triadas pela manhã; prepara as que precisam da sua aprovação | até ~60% da janela |
| **12:30** | **Você** (10 min) | Aprova ou corrige as notas em `10 Triado` (ou responde ao Codex) | — |
| **13:00** | Codex | Grava as aprovadas em `20 Refinado` e aplica no cofre | resto da janela A |
| **13:30** | Spark | Lê `20 Refinado`; cria tarefas e eventos | automático |
| **18:00** | Claude — Janela B | Pedidos da tarde + conexões entre as notas novas e as antigas + pesquisa de legislação pendente | até ~60% da janela |
| **21:00** | Codex — Janela B | Revisão curta do que o Claude fez à tarde | curta |
| **22:00** | **Você** (5 min) | GitHub Desktop: puxa, revisa e junta as mudanças de regras/scripts | — |
| **23:00** | Spark | Resumo do dia em `30 Ação (Spark)` | automático |
| **qualquer hora** | Antigravity | Entra quando o Painel mostra alguém **vermelho**, ou para scripts e leituras longas | conforme cota |

**Por que só ~60% da janela:** os 40% restantes ficam de reserva para pedidos urgentes, correções e para você conversar sem bater no limite.

---

## 4. Rotina semanal — respeitando o teto semanal

O teto semanal é o que mais pega de surpresa. Divida a semana assim:

| Dia | Foco | Ferramentas pesadas |
|---|---|---|
| Seg–Qui | Fluxo normal (seção 3) | Claude + Codex |
| Sex | Fluxo leve; Claude faz o **relatório da semana** (o que entrou, o que ficou pendente) | Claude |
| Sáb | **Dia do Google**: Gemini Notebook gera resumos e quizzes de estudo; Antigravity faz a leitura longa do cofre e procura notas duplicadas | Gemini Notebook + Antigravity |
| Dom | Spark monta o **plano da semana**; você revisa o Painel de cotas | Spark |

**Termômetro semanal** (cada ferramenta, olhando o próprio painel de uso):

- **Até 50% usados na quarta-feira** → verde, segue o plano.
- **50–75% na quarta** → amarelo: a triagem pesada passa para o Antigravity; Claude e Codex só fazem revisão e conexões.
- **Mais de 75% antes de sexta** → vermelho: a ferramenta sai da rotina até renovar; sobe a 1ª reserva da seção 2.
- **Sempre guardar ~20% do teto semanal** de Claude e de Codex para emergências e para conversar com você.

---

## 5. Painel de cotas

Uma planilha Google em `Segundo Cérebro/90 Pedidos/Painel de cotas`. **Toda ferramenta, ao terminar uma rodada, escreve uma linha.**
Modelo das colunas em [`templates/painel-de-cotas.md`](../templates/painel-de-cotas.md).

Antes de começar, cada IA lê as últimas linhas do Painel:

- Se a ferramenta dela está **vermelha** → não começa; escreve o pedido para a reserva em `Pedidos`.
- Se outra ferramenta está **vermelha** → assume o trabalho dela, conforme a seção 2.

As porcentagens vêm **do painel de uso de cada ferramenta** (Claude: configurações → uso; Codex: indicador de uso do app;
Antigravity: indicador de cota no próprio app). Nunca estimar de cabeça.

---

## 6. Economia de tokens — regras para todas as IAs

1. **Ler só o que é novo.** A triagem olha arquivos da Entrada modificados depois da última rodada (data registrada no Painel). Nunca reler tudo.
2. **Índice antes do cofre.** Para propor conexões, ler `Índice` (títulos e assuntos), não as notas inteiras. Abrir uma nota só quando o título indicar relação.
3. **Lotes.** Juntar até ~20 arquivos por rodada. Uma rodada grande custa menos que vinte pequenas.
4. **Passagem curta.** Cada etapa entrega à seguinte uma passagem de **no máximo 15 linhas** (formato abaixo), não a conversa inteira.
5. **Modelo certo para o trabalho.** Triagem simples → modelo mais leve da ferramenta; conexões difíceis e revisão de autoria → modelo mais forte.
6. **Leitura longa vai para o Gemini.** Arquivo enorme ou o cofre inteiro → Antigravity ou Gemini Notebook, nunca Claude ou Codex.
7. **Nada de "conferir de novo por garantia".** A revisão é feita uma vez, por outra IA, e registrada.

### Formato da passagem (handoff)

```
PASSAGEM — <de> → <para> — <AAAA-MM-DD HH:MM>
Feito: <n> notas triadas em 10 Triado (lista no Índice, seção "novas")
Precisa de você: <n> rascunhos de pensamento aguardando aprovação
Dúvidas de autoria: <n> (em Pendências)
Pedidos abertos para <para>: <lista curta>
Cota de <de>: <verde/amarelo/vermelho>, renova <quando>
```

---

## 7. Fila de pedidos — formato completo

Documento `90 Pedidos/Pedidos para o Claude` (e, se quiser, um igual para cada ferramenta):

```
- [ ] 2026-11-08 | de: Spark | para: Claude | prioridade: alta | custo: M | processar a Entrada de hoje
- [ ] 2026-11-08 | de: Você  | para: Claude | prioridade: média | custo: G | ligar notas de Civil III às de OAB
- [x] 2026-11-07 | de: Codex | para: Claude | prioridade: baixa | custo: P | refazer nota X | feito: nota refeita, autoria marcada incerta
```

- **custo**: `P` (cabe numa conversa curta), `M` (uma rodada de triagem), `G` (vários lotes; distribuir pela semana).
- Pedido `G` com a ferramenta amarela → vai para a reserva ou fica para o sábado.

---

## 8. VS Code e GitHub Desktop

**VS Code — a bancada.** Abra a pasta deste repositório. Com as extensões do Claude Code e do Codex instaladas, você
conversa com as duas ali mesmo e vê as mudanças nos arquivos lado a lado. Use para revisar scripts e regras.
O cofre do Obsidian também pode ser aberto no VS Code para conferir mudanças, mas quem escreve nele é o Codex, com sua aprovação.

**GitHub Desktop — o portão de aprovação.** Cada IA trabalha numa branch com o próprio nome:

| Prefixo da branch | De quem |
|---|---|
| `claude/…` | Claude |
| `codex/…` | Codex |
| `antigravity/…` | Antigravity |

Você abre o GitHub Desktop, vê o que cada uma mudou e junta na principal só o que aprovar. Assim duas IAs nunca
sobrescrevem o trabalho uma da outra. Lembrete: este repositório é **público** e guarda só regras e scripts.
Se um dia quiser versionar o cofre, crie **outro repositório, privado**, e decida isso à parte.

---

## 9. Plano de contingência

| Situação | O que acontece |
|---|---|
| Claude sem cota | Antigravity (Gemini) faz a triagem com as mesmas regras (`GEMINI.md`); Codex revisa |
| Codex sem cota (como em 8/11) | Claude faz a revisão leve; nada vai para o cofre; notas ficam em `10 Triado` com `status: rascunho` até o Codex voltar |
| Antigravity sem cota | Leituras longas vão para o Gemini Notebook; scripts esperam |
| Spark indisponível | Claude gera `30 Ação/Tarefas pendentes` e, com sua autorização, cria os eventos pela Agenda |
| Todos vermelhos | Só a Entrada recebe material; nada se perde; processa quando renovar |
| Conflito entre IAs | Vale a regra mais restritiva; a dúvida vai para `Pendências` e você decide |

---

## 10. Implantação em fases

| Fase | O que | Quem | Pronto quando |
|---|---|---|---|
| **0** | Suas autorizações (dados reais, pasta no Drive, rodada automática) | Você | Você responder |
| **1** | Criar `Segundo Cérebro` no Drive, a fila de pedidos e o Painel de cotas | Claude | Pastas e planilha existem |
| **2** | Colar as instruções no Spark; criar o notebook "Civil III" no Gemini Notebook apontando para `20 Refinado` | Você (5 min) | Spark respondeu ao primeiro pedido |
| **3** | Abrir este repositório no VS Code e no GitHub Desktop; Codex e Antigravity leem `AGENTS.md` / `GEMINI.md` | Você + Codex | Cada um fez uma branch de teste |
| **4** | **Piloto de 1 semana só com Civil III** | Todos | Uma semana de Painel preenchido sem ninguém estourar |
| **5** | Ajustar horários e porcentagens com base no Painel real | Claude + você | Revisão de domingo |
| **6** | Abrir para as outras áreas (Vida pessoal, Finanças, Ideias) | Todos | — |
