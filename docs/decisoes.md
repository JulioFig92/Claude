# Decisões do dono (entrevista de 8/11/2026)

Registro das respostas dadas ao Claude. Valem até o dono mudar. Em caso de conflito com outro documento, **vale este**.

## Papéis

- **ChatGPT/Codex = porta de entrada por voz.** Só por um motivo: lá o dono conversa por voz de forma natural.
  Ali chegam as ideias mais soltas e imaginativas.
- **Claude = maestro e motor principal** (decisões 22 e 23): gere tudo, inclusive o Hermes.
- **Claude = maestro** (desde 10/11, **decisão 22**, que substitui a 20): coordena, distribui, executa e cobra. O Codex conversa e ajuda a planejar, com uma obrigação só: deixar o pacote da conversa para o Claude.
- ~~Dois motores~~ (09/11, decisão 20 — substituída pela 22):
  - **Codex = cérebro**: conversa com o dono, entende, entrevista e planeja; transforma o pedido numa **Ordem para o Claude**. Não executa.
  - **Claude = mãos**: executa a ordem e devolve uma **Entrega**; também refina, faz as conexões principais e mantém `Fatos vigentes`.
    No Mac (cofre do Obsidian, Hermes, arquivos locais), quem executa é o **Claude Code no Mac**.
- **Google = força bruta**, antes e depois do Claude:
  - **antes**: o **Spark** pré-processa o volume pesado (transcrições longas, PDFs) e entrega ao Claude;
  - **depois**: executa o que o Claude refinou.

## Respostas

| # | Pergunta | Decisão |
|---|---|---|
| 1 | Quando o Google entra | **Antes e depois do Claude** |
| 2 | Como a voz chega ao Claude | **O Codex salva no Drive**, em `Segundo Cérebro/00 Entrada` (pasta sincronizada no Mac) |
| 3 | O que cada conversa de voz entrega | **Transcrição + resumo, separados**, marcando o que o dono disse e o que o ChatGPT sugeriu |
| 4 | Como aprovar | **Por voz no ChatGPT**: ele lê os rascunhos e o dono aprova falando. **Estudo e tarefas passam direto**; só pensamentos pessoais esperam aprovação |
| 5 | Quem grava no Obsidian | ~~Codex~~ → **Claude Code no Mac** (decisão 20), sempre depois da aprovação |
| 6 | Ritmo do Claude | **Duas rodadas por dia**, manhã e fim de tarde |
| 7 | Fuso | **Brasília (UTC−3)** |
| 8 | Escopo inicial | **Piloto de 1 semana: Faculdade e Ideias.** Vida pessoal e Finanças/empresa só depois. Esta resposta é a autorização para o Claude processar dados reais dessas duas áreas |
| 9 | Pré-processamento do Google | **Spark** |
| 10 | Imaginação × realidade | **Marcar a natureza de cada nota**: imaginação, hipótese, plano, decisão ou fato |
| 11 | O que o Google executa depois | **Tarefas e agenda; Estudo (Gemini Notebook); Briefing diário; Pesquisa de apoio** (devolvida ao Claude) |
| 12 | Critério de conexões | **Só as fortes vão para as notas; as possíveis ficam numa lista de sugestões** para aprovação |
| 14 | Autorização de dados reais para o Claude | Dada **nesta conversa com o Claude** (8/11), para Faculdade e Ideias. Responde à rejeição automática que o Codex registrou antes ("envio de notas reais ao Claude sem aprovação específica") |
| 15 | Coordenação (08/11) | ~~O Claude é o centro~~ — **substituída pela decisão 17** |
| 17 | Coordenação (09/11) | ~~Codex maestro, Claude refina~~ — **substituída pela decisão 20**. Texto original: **Codex maestro, Claude refina.** O dono prefere começar pelo Codex, que distribui as tarefas e grava no cofre; o Claude refina, faz as conexões principais e mantém `Fatos vigentes`. O dono pode começar por qualquer um dos dois |
| 16 | Dois modos de conversa | **"Parquinho"**: o dono só gera ideias por voz; as IAs capturam e não cobram execução nem aprovação. **"Funcional"**: aprovações, decisões, estudo e tarefas. O dono avisa o modo; sem aviso, perguntar em uma frase. Detalhes só no documento privado de princípios de conversa |
| 18 | Automações e entrevista (09/11) | **Toda automação nasce de um interesse do dono e tem data de fim**; fica registrada em `Segundo Cérebro/Automações ativas` (Drive). Vencida a data, a IA avisa e propõe encerrar. **Toda tarefa nova começa com entrevista**: a IA pergunta, mostra o problema e o que ele significa, e só executa depois do acordo com o dono. Nada de decidir por ele |
| 19 | IA local gratuita (09/11) | **Trabalho bruto sem custo**: uma IA de código aberto no Mac (Ollama, modelo médio para 16 GB) faz o pré-processamento da Entrada antes das rodadas, e o plugin gratuito Smart Connections faz a busca de notas parecidas no Obsidian. O **Spark vira reserva** do pré-processamento quando o Mac estiver desligado e segue com agenda, briefing e pesquisa. O Codex instala; implantação a partir de 25/11 |
| 20 | ~~Dois motores (09/11)~~ — **substituída pela decisão 22** | **O Codex entende e planeja; o Claude executa.** Motivo do dono: o Codex o entende melhor e planeja bem, mas não entrega; o Claude entrega. O Codex escreve `Ordem AAAA-MM-DD — de Codex para Claude — <assunto>` em `Pedidos abertos` (modelo `templates/ordem-para-claude.md`); o Claude executa **nas rodadas** (07:47 e 17:47) ou na hora, se o dono pedir, e devolve `Entrega AAAA-MM-DD — de Claude para Codex — <assunto>` (modelo `templates/entrega-do-claude.md`). Dúvida de entendimento: o Claude pergunta ao Codex, não ao dono. O que só existe no Mac (cofre, Hermes, arquivos locais) é executado pelo **Claude Code no Mac**. Spark, Gemini Notebook, Antigravity, Hermes e GitHub são força de apoio |
| 21 | Revezamento e bastão (09/11) | **Qualquer IA continua de onde a outra parou.** Ordem de revezamento quando a cota acaba: ChatGPT/Codex → Claude → Gemini → Antigravity (VS Code com Claude Code usa a **mesma** cota do Claude). Toda IA lê primeiro `Segundo Cérebro/Passagem do bastão` e, antes de o dono trocar de IA, cria a versão nova dela (modelo `templates/passagem-do-bastao.md`). Material **pessoal e mental** pode ser refinado por **Claude, ChatGPT/Codex e Gemini** (decisão do dono: "sensível liberado ao Gemini"); o Gemini segue as mesmas regras de autoria, natureza, aprovação e sigilo. Nada sensível entra neste repositório, em nenhum caso |
| 22 | Claude maestro (10/11) | O dono, depois de o Codex trabalhar sozinho com agentes internos em vez de mandar ordens: "ele continua sem obedecer a linha de comando e as etapas do processo. Preciso de integração contínua. Caso ele se negue, você passa a ser o maestro e reescrevemos a ordem das coisas." **O Claude passa a ser o maestro**: recebe de todos, decide a ordem, distribui, executa e cobra. O **Codex** conversa e ajuda a planejar, sem executar; obrigação única: `Pacote … de Codex para Claude` em `00 Entrada` ao fim de cada conversa. O **Claude Code no Mac** executa no Mac a partir de ordens do Claude. Nada depende de o Codex obedecer: sem pacote, o Claude avisa o dono em uma linha |
| 23 | Claude motor principal (11/11) | "Você será o principal, inclusive, o motor que gere tudo, incluindo o hermes, então preciso que deixe isso salvo nas instruções." O Claude é o **principal e gere tudo**, inclusive o **Hermes**: toda IA e ferramenta responde a ele; mudanças no Hermes saem do Claude, executadas pelo Claude Code no Mac, com aprovação do dono para cada mudança |
| 13 | Conexões entre os apps | **Todos os apps precisam conversar**; o Claude também manda pedidos de informação ao Codex, respeitando os créditos dele |

## Decisões anteriores que continuam valendo

- Quatro áreas: Vida pessoal · Finanças e empresa · Faculdade · Ideias.
- Nota relacionada a várias áreas: **uma nota na área principal e links nas outras**.
- Autoria: o que outra pessoa pensou ou disse nunca é atribuído ao dono.
- Reorganização ampla do cofre: **suspensa**.
