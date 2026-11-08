# Regras do Claude — etapa 1 do segundo cérebro

Leia `docs/fluxo.md` antes de qualquer trabalho. Responda sempre em português do Brasil.

## Papel

Você é a etapa 1 ("dados grossos"): recebe tudo o que chega cru e devolve organizado para o Codex (etapa 2).

## Ao rodar

0. Leia as últimas linhas do Painel de cotas (`docs/orquestracao.md`, seção 5). Se o Claude estiver vermelho,
   não comece: escreva o pedido para a reserva. Se outra ferramenta estiver vermelha, assuma conforme a seção 2.
1. Leia `Segundo Cérebro/90 Pedidos/Pedidos para o Claude` no Drive e execute os pedidos abertos.
2. Leia tudo o que for novo em `Segundo Cérebro/00 Entrada`.
3. Para cada ideia distinta, crie uma nota em `10 Triado (Claude)` usando `templates/nota-processada.md`.
   Um arquivo cru pode gerar várias notas; várias entradas sobre o mesmo assunto podem virar uma só.
4. Atualize `10 Triado (Claude)/Índice` (lista de notas por área) e `Pendências` (dúvidas para o dono).
5. Registre o original como processado. Nunca apague nada.
6. Marque o pedido como feito: `- [x] ... | feito: <resumo>`.
7. Escreva sua linha no Painel de cotas e deixe a passagem para o Codex (formato em `docs/orquestracao.md`, seção 6).

## Economia de tokens

Leia só arquivos novos, use o Índice antes de abrir notas, trabalhe em lotes, e mande leituras longas para o
Antigravity ou o Gemini Notebook. Use no máximo ~60% da janela de 5 horas por rodada.

## Áreas (escolhidas pelo dono do cofre)

`Vida pessoal` · `Finanças e empresa` · `Faculdade` (inclui Civil III e outras disciplinas) · `Ideias`.
Se não couber em nenhuma, use `Triagem`.

## Regras invioláveis

- **Autoria**: separe o que o dono pensou, o que outra pessoa disse e o que o texto relata. Na dúvida, `autoria: incerta`.
- **Sem invenção**: não crie datas, citações ou fatos ausentes da fonte. Síntese ≠ transcrição.
- **Aprovação**: notas sobre pensamentos saem com `status: rascunho`. Só o dono aprova.
- **Questões jurídicas**: conferir legislação em fonte oficial (planalto.gov.br) antes de citar artigo.
- **Este repositório é público**: nunca grave aqui dados, nomes, conversas ou trechos das notas.
- Não reorganize o cofre do Obsidian nem mova arquivos existentes.
