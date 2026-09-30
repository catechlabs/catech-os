---
name: reuniao
description: >
  Transforma a transcrição ou as anotações de uma reunião em resumo, decisões e tarefas
  (com responsável e prazo). Use quando o usuário chamar /reuniao, colar ou arrastar uma
  transcrição, ata, gravação transcrita ou anotações soltas, ou disser "resume essa reunião",
  "o que ficou decidido", "quais as tarefas dessa call", "faz a ata".
---

# /reuniao · resumo, decisões e tarefas

Entrada: transcrição, ata ou anotações (texto colado ou arquivo). Saída: uma ata curta que dá
pra ler em 1 minuto e agir em cima. **Fiel ao que foi dito: nunca inventar decisão, dono ou prazo.**

## Antes de começar

1. Ler a transcrição inteira. Se estiver truncada, ilegível ou sem falantes, dizer isso antes.
2. Descobrir o projeto: se a reunião é de um cliente/projeto que tem pasta (seção 3 do
   `AGENTS.md`), ler o `contexto.md` e o `andamento.md` dela pra entender nomes, siglas e o que
   já estava combinado. Sem projeto claro, perguntar em uma linha.
3. Data da reunião: pegar da transcrição ou do nome do arquivo; se não achar, perguntar.
   Sempre data absoluta (AAAA-MM-DD), nunca "ontem".

## Saída

```markdown
# Reunião · [tema] · AAAA-MM-DD
**Participantes:** [nomes citados] · **Fonte:** [caminho do arquivo ou "colado na conversa"]

## Resumo
[3 a 5 linhas: por que a reunião aconteceu, o que foi discutido, onde terminou.]

## Decisões
- [decisão] · por quê: [motivo dito na reunião] · quem decidiu: [nome, se claro]

## Tarefas
| O quê | Quem | Prazo | Origem |
|---|---|---|---|
| [verbo + entrega concreta] | [nome ou "sem dono"] | [AAAA-MM-DD ou "sem prazo"] | [trecho ou minuto] |

## Em aberto
- [dúvida ou ponto sem conclusão, e quem deveria resolver]
```

## Regras de qualidade

- **Decisão ≠ opinião ≠ ideia.** Só entra em "Decisões" o que foi fechado. Proposta sem
  aceite vai pra "Em aberto".
- **Tarefa começa com verbo e diz o entregável** ("Enviar proposta revisada", não "proposta").
  Dono ou prazo não dito: escrever "sem dono" / "sem prazo", nunca chutar. Prazo relativo
  ("sexta") vira data absoluta usando a data da reunião.
- Prefira cortar a incluir: conversa lateral, cumprimentos e repetição ficam de fora.
- Trecho ambíguo ou contraditório: citar as duas versões em "Em aberto", sem escolher.
- Números, nomes e valores copiados exatamente como aparecem.
- Se a reunião foi com cliente e o texto vai sair pra fora (ata enviada), ler a marca antes
  (gatilho da seção 4 do `AGENTS.md`).

## Depois de entregar

- Mostrar a ata na conversa e perguntar onde salvar. Destino padrão: a pasta do projeto
  (`<projeto>/reunioes/AAAA-MM-DD-<tema>.md`, criando a pasta com `mkdir -p`). A transcrição
  bruta também vai pra pasta do projeto, e o essencial é destilado no `contexto.md` dele
  **com data e caminho da fonte**.
- Decisão com motivo → `_memoria/decisoes.md` e pendência que vale continuidade → `agora.md`
  saem pelo `/atualizar` no fim da sessão; não escrever direto agora. Avisar: "anotado, vai
  no /atualizar".
- Oferecer: "quer o rascunho do email de follow-up pros participantes?"
