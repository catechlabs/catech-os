---
name: analisar-dados
description: >
  Analisa um arquivo de dados (CSV, Excel, JSON, TXT, relatório exportado) e entrega um
  resumo executivo com o que está bom, o que preocupa, números-chave e recomendações.
  Use quando o usuário chamar /analisar-dados, arrastar uma planilha ou export, ou disser
  "analisa esse arquivo", "o que mostram esses dados", "resume esses resultados",
  "por que caiu", "qual campanha/produto está melhor".
---

# /analisar-dados · da planilha à decisão

Parte do modelo do kit (`sistema/templates/skills/analisar-dados.md`), com as verificações
abaixo. Regra de ouro: **todo número do resumo vem do arquivo e pode ser conferido.**

## 1. Entender a pergunta

Ler `_contexto/empresa.md` (o que os dados representam). Se não estiver claro, perguntar em
uma linha: "o que é esse arquivo e qual pergunta você quer responder?" Sem pergunta, o padrão é
"o que está bom, o que preocupa, o que fazer". Se o contexto é óbvio pelo nome ou conteúdo,
seguir sem perguntar.

## 2. Inspecionar antes de concluir

Antes de qualquer análise, olhar e reportar em 1 a 3 linhas: tamanho (linhas × colunas),
período coberto, colunas usadas, e os problemas: vazios, duplicatas, datas ou moedas em
formato misto, totais que não fecham, outliers absurdos. Problema relevante: dizer
**antes** da análise e como foi tratado (ex.: "12 linhas sem valor, ignoradas").

Arquivo grande ou conta não trivial: calcular com código (Python/pandas ou similar) em vez de
somar de cabeça, e reconferir os totais contra os do próprio arquivo, se existirem.

## 3. Analisar

- **Comparar sempre com algo:** período anterior, média, meta, melhor vs pior. Número solto
  não é insight.
- **Bom:** o que subiu, top performers. **Preocupa:** quedas, anomalias, desperdício.
- **Não óbvio:** correlação ou padrão que a leitura rápida não mostra.
- **Correlação não é causa:** escrever "coincide com", não "causou", a não ser que os dados
  provem. Amostra pequena: dizer que é pequena.
- Separar **fato** (está no arquivo) de **hipótese** (interpretação), e marcar a hipótese.

## 4. Saída

```markdown
# Análise · [nome do arquivo] · AAAA-MM-DD

## Resposta curta
[1 a 2 frases que respondem a pergunta. É a única coisa que alguém com pressa lê.]

## O que os dados mostram
[2 a 3 parágrafos em prosa, com os números que sustentam.]

## Funciona · Merece atenção
[duas listas curtas, cada item com o número e a comparação.]

## Números-chave
| Métrica | Valor | Comparação |
|---|---|---|

## 3 recomendações
1. [ação concreta, com o que esperar dela]

## Limites da análise
[dados faltando, amostra, o que não dá pra concluir.]
```

Se um gráfico esclarece mais que a tabela, gerar (a skill `dataviz`, se existir). Um
gráfico simples e legível vale mais que vários.

## Regras

- **Nunca inventar dado** nem preencher lacuna com suposição. O que não está no arquivo: dizer.
- Percentual sempre com a base ("18% de 240 pedidos"); moeda e período explícitos.
- Análise que o usuário lê sem abrir o arquivo original: prosa, não só bullets.
- Tom conforme `_contexto/preferencias.md`. Se sai pra cliente, ler a marca antes.
- Dado pessoal (CPF, email, telefone): não repetir no resumo além do necessário.

## Depois de entregar

Perguntar onde salvar. Destino padrão: pasta do projeto ou cliente (`<projeto>/analises/`,
`mkdir -p`); sem projeto, perguntar (não criar gaveta nova). Análise pontual e trivial: não
salva. Decisão que sair da análise vai pro `/atualizar`. Oferecer o resumo em HTML
pra compartilhar.
