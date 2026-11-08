# Orquestração — todas as ferramentas, respeitando as cotas

Quem faz o quê, quando, e o que acontece quando alguém fica sem cota.
Complementa [`fluxo.md`](fluxo.md) (pastas e regras) e [`decisoes.md`](decisoes.md) (o que o dono decidiu).
Horários em **Brasília (UTC−3)**.

---

## 1. O elenco

| Ferramenta | Papel | Onde roda | Cota |
|---|---|---|---|
| **ChatGPT / Codex** | **Captura por voz** · lê rascunhos em voz alta para aprovação · grava no Obsidian | App no Mac e no celular | Janela de 5 h + teto semanal; créditos extras pagos |
| **Gemini Spark** | **Força bruta antes** (pré-processa a Entrada) e **depois** (tarefas, agenda, briefing, pesquisa) | Nuvem do Google, 24 h | Plano Google AI |
| **Claude** (nuvem, agendado) | **Centro: refina tudo e faz as conexões principais** | Nuvem da Anthropic | Janela de 5 h + teto semanal (mesma conta das suas conversas com o Claude) |
| **Claude Code** (no Mac / VS Code) | Mesmo papel, quando precisar de arquivos do Mac | Seu Mac | Mesma cota acima |
| **Gemini Notebook** | **Estudo**: resumos, áudios e quizzes de Faculdade/OAB a partir de `20 Aprovado` | Nuvem do Google | Plano Google AI |
| **Antigravity** | **Reserva** (assume refino ou gravação se alguém ficar vermelho) · leitura gigante · scripts | Seu Mac | Janela de 5 h + teto semanal no AI Pro; Ultra sem teto semanal |
| **VS Code** | Bancada: ver lado a lado o que as IAs mudaram no repositório e no cofre | Seu Mac | — |
| **GitHub Desktop** | Portão de aprovação das **regras e scripts** (branches `claude/`, `codex/`, `antigravity/`) | Seu Mac | — |

**Princípio:** o Claude é o centro, então **a cota do Claude é a mais preciosa**. Tudo o que for volume, leitura longa,
transcrição ou execução vai para o Google, que tem cota mais folgada e trabalha 24 h. O Claude recebe o material já
pré-processado e gasta a cota só com o que só ele faz: refinar, separar natureza e autoria, conectar.

---

## 2. Roteamento por tipo de tarefa

| Tarefa | Principal | Reserva | Observação |
|---|---|---|---|
| Conversar por voz, capturar ideias | ChatGPT/Codex | Gravar áudio no celular e salvar em `00 Entrada` (o Spark transcreve) | Única razão de o ChatGPT estar no fluxo |
| Transcrever áudio, quebrar textos longos, ler PDFs | Spark | Antigravity | Nunca o Claude |
| **Refinar, marcar natureza e autoria** | **Claude** | Antigravity (tudo sai como `aguarda aprovação`) | Coração do sistema |
| **Conexões principais** | **Claude** | Esperar a próxima rodada do Claude | Não terceirizar |
| Ler rascunhos em voz alta e colher aprovação | ChatGPT | Você lê no Drive | — |
| Gravar no Obsidian | Codex | Antigravity; Claude Code no Mac | Só o que está em `20 Aprovado` |
| Tarefas e agenda | Spark | Claude cria lista em `30 Ação` | — |
| Briefing diário | Spark | Relatório da rodada da manhã do Claude | — |
| Pesquisa de apoio na web | Spark | Claude | Resultado volta para `00 Entrada` |
| Estudo (resumos, áudios, quizzes) | Gemini Notebook | Claude | Fonte: `20 Aprovado` |
| Scripts deste repositório | Antigravity | Codex | Branch própria |

**Quem escreveu não revisa:** se o Antigravity refinar no lugar do Claude, a próxima rodada do Claude revisa.

---

## 3. Rotina diária

```
          06h     08h     10h     12h     14h     16h     18h     20h     22h
Você      ── fala por voz com o ChatGPT quando quiser, o dia todo ──────────────
Spark     ▲pré          ▲briefing     ▲executa    ▲pré           ▲executa  ▲resumo
Claude          ▲RODADA MANHÃ                            ▲RODADA TARDE
ChatGPT                             ▲aprovação por voz                 ▲aprovação
Codex                               ▲grava no cofre                    ▲grava no cofre
```

| Hora | Quem | O que faz |
|---|---|---|
| a qualquer hora | **Você + ChatGPT** | Conversa por voz. No fim, o Codex salva o pacote de voz em `00 Entrada` |
| **06:00** | Spark | Pré-processa tudo o que chegou à Entrada desde a tarde → `05 Pré-processado` |
| **07:47** | **Claude (rodada da manhã, automática)** | Refina, conecta, separa direto × aprovação, escreve relatório |
| **08:30** | Spark | **Briefing** por e-mail: agenda, tarefas, quantas notas aguardam aprovação |
| **12:30** | **Você + ChatGPT** (10 min) | O ChatGPT lê `15 Para aprovar` e `Sugestões de conexão`; você aprova ou corrige por voz |
| **13:00** | Codex | Move o aprovado para `20 Aprovado` e grava no Obsidian; correções viram pedido para o Claude |
| **13:30** | Spark | Executa: tarefas e agenda a partir de `20 Aprovado`; pesquisas pedidas |
| **16:00** | Spark | Pré-processa o que chegou desde a manhã |
| **17:47** | **Claude (rodada da tarde, automática)** | Mesmo trabalho + pedidos de correção + resultados de pesquisa |
| **20:30** | **Você + ChatGPT** (10 min) | Segunda aprovação por voz |
| **21:00** | Codex + Spark | Grava no cofre; executa |
| **23:00** | Spark | Resumo do dia em `30 Ação (Spark)` |

As duas rodadas do Claude ficam **10 horas** uma da outra, então **cada uma usa uma janela de 5 horas própria**,
e entre elas você tem cota livre para conversar com o Claude.

---

## 4. Cotas

### Janela de 5 horas

- Cada rodada do Claude usa **no máximo ~60% da janela**. Se o lote for maior, refina o mais antigo primeiro e deixa o resto para a próxima rodada (registrado no relatório).
- Os outros ~40% ficam para você conversar com o Claude e para urgências.

### Teto semanal

| Situação na quarta-feira | O que fazer |
|---|---|
| Até 50% do teto semanal | Verde — segue a rotina |
| 50–75% | Amarelo — o Spark passa a resumir mais no pré-processamento; o Claude só refina o que for novo e conecta, sem reler |
| Mais de 75% | Vermelho — só a rodada da tarde do Claude; o Antigravity assume a manhã (tudo como `aguarda aprovação`) |

**Sempre guardar ~20% do teto semanal do Claude** para as suas conversas. O Codex gasta pouco (captura e gravação);
se ele esgotar, a captura passa para áudio no celular (seção 6).

### Painel de cotas

A pasta `90 Pedidos e cotas/Relatórios de rodada` **é o painel**: cada ferramenta escreve um relatório por rodada
(modelo em [`templates/relatorio-de-rodada.md`](../templates/relatorio-de-rodada.md)). O Claude agendado
não enxerga o próprio medidor de uso; ele registra o volume processado, e você ou o Codex completam a porcentagem
quando quiserem, olhando o medidor de cada app.

---

## 5. Economia de tokens

1. **Pré-processamento no Google.** O Claude lê `05 Pré-processado` em vez da transcrição bruta sempre que o Spark já tiver passado; volta à fonte só para conferir citação ou autoria.
2. **Só o novo.** Cada rodada lê apenas arquivos criados depois do último relatório do Claude.
3. **Índice antes do cofre.** Conexões partem do `Índice`, não da leitura de todas as notas.
4. **Lotes.** Uma rodada grande custa menos que muitas pequenas.
5. **Passagem curta.** Máximo de 15 linhas entre etapas.
6. **Leitura gigante vai para o Google.** O cofre inteiro ou um PDF enorme → Spark ou Antigravity.

---

## 6. Contingência

| Situação | O que acontece |
|---|---|
| **ChatGPT/Codex sem cota** | Você grava um **áudio no celular** e salva em `00 Entrada`; o Spark transcreve; o Claude refina. A gravação no cofre espera o Codex voltar |
| **Claude sem cota** | A rodada é pulada e registrada; o Spark segue pré-processando. Se passar de um dia, o Antigravity refina com as regras do `CLAUDE.md`, e tudo vai para `15 Para aprovar` |
| **Spark indisponível** | O Claude lê direto da `00 Entrada` (gasta mais) e cria a lista de tarefas em `30 Ação` |
| **Antigravity sem cota** | Leituras gigantes esperam o sábado |
| **Material fora do piloto** | Fica na Entrada, sem processar, citado no relatório |
| **Conflito entre IAs** | Vale a regra mais restritiva; a dúvida vai para `15 Para aprovar` |

---

## 7. Semana

| Dia | Foco |
|---|---|
| Seg–Sex | Rotina da seção 3 |
| Sáb | Gemini Notebook gera estudo da semana (Faculdade/OAB); Antigravity faz leitura do cofre e lista duplicatas → vira pedido para o Claude |
| Dom | Spark monta o plano da semana; o Claude, na rodada da tarde, faz o **relatório semanal** (o que entrou, conexões novas, pendências) |

---

## 8. Implantação

| Fase | O que | Quem | Situação |
|---|---|---|---|
| 0 | Decisões e autorização do piloto | Você | **Feito** (8/11) |
| 1 | Pastas no Drive, pedidos, relatórios, instruções para cada IA | Claude | **Feito** (8/11) |
| 2 | Rodadas automáticas do Claude às 07:47 e 17:47 | Claude | **Ativas** (8/11), rodando na conversa do Claude que já tem o Drive conectado |
| 2b | Teste fictício de ponta a ponta: pacote de voz → 5 notas → 3 direto, 2 para aprovar → pedidos para Spark e Codex | Claude | **Feito** (8/11) |
| 3 | Colar as instruções no Spark e no ChatGPT/Codex; criar o notebook "Faculdade" no Gemini Notebook apontando para `20 Aprovado` | Você | Pendente |
| 4 | Google Drive para desktop no Mac (o Codex grava na Entrada por ele) | Você | **Já instalado**: a pasta Documents do Mac está sincronizada |
| 4b | Mapa do cofre v1 (Faculdade e Ideias), feito pelo Claude a partir da cópia "Cofre de ensaio" no Drive | Claude | **Feito** (8/11); o Codex só confere diferenças com o cofre ativo |
| 5 | Piloto de 1 semana: Faculdade e Ideias | Todos | Começa quando a fase 3 terminar |
| 6 | Revisão do piloto no domingo; abrir Vida pessoal e Finanças/empresa se você aprovar | Você + Claude | — |
