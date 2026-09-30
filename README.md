# CatechLabs OS

O sistema operacional do seu negócio, feito pelo [CatechLabs](https://catechlabs.com.br).

---

## Como instalar

O kit funciona no **Claude Code** e no **Codex** (Windows, Mac ou Linux). Você baixou um zip do kit;
instalar é abrir a pasta e chamar o setup.

**1. Descompacte o zip** onde você guarda seus projetos. Essa pasta vai ser a casa do seu negócio
(pode renomear pra o nome dele, se quiser).

**2. Abra a pasta no seu agente:** no aplicativo do **Claude Code** (ou no VS Code com a
extensão), use "Abrir pasta" e escolha a pasta que você descompactou. No **Codex**, mesma coisa.

**3. Chame o setup:**
- No Claude Code: digite `/setup`
- No Codex (primeira vez): peça `leia e siga o arquivo .claude/skills/setup/SKILL.md`

> Prefere o terminal? Entrar na pasta e rodar `claude` (ou `codex`) dá no mesmo.

O agente vai te fazer algumas perguntas e configurar o sistema pro seu negócio. Em 5 minutos você tem tudo pronto, funcionando nos dois.

## No dia a dia, só três coisas

1. **Abriu o dia:** `/iniciar` (ou só "bora"). Mostra onde você parou e o que está pendente.
2. **Precisa de ajuda com qualquer coisa:** fale com a Beth, sua chief of staff. "Beth, o que faço
   hoje?", "Beth, tenho um problema com X", "Beth, organiza o projeto Y". Ela chama as outras
   skills quando precisa.
3. **Terminou:** `/atualizar` guarda o que rolou. Depois `/syncar`, se o sistema está no GitHub.

Não precisa decorar comando: pedir em português normal funciona, o agente acha a skill certa.

**Pra planejar algo grande** (o trimestre, um lançamento, um projeto novo, reorganizar o
negócio): comece a mensagem com `/plan` (no aplicativo, também dá pra escolher **Plan** no
seletor ao lado do botão de enviar). Nesse modo o **Opus**, o modelo mais forte, pensa e te mostra
o plano; você aprova e o **Sonnet** executa. No dia a dia fica tudo no Sonnet, inclusive o time de
agentes, que é o que cabe no plano Pro (20 dólares). Pra ver quanto do plano já usou: `/usage`
(no aplicativo, o anel ao lado do seletor de modelo).

Não troque o modelo com `/model` neste projeto: a troca vale por cima da configuração do kit e
gasta o limite mais rápido.

---

## O que vem no kit

**Skills prontas pra usar:**
- `/setup`: configura o sistema pro seu negócio (comece por aqui)
- `/iniciar`: abre a sessão: puxa o GitHub, carrega o contexto, anuncia recados e diz onde você parou
- `/atualizar`: fecha a sessão: escreve o diário do dia, o "onde paramos", as decisões e o contexto, e diz o que escreveu onde
- `/syncar`: manda o trabalho pro GitHub e diz o que subiu
- `/novo-projeto`: cria pasta de projeto ou cliente com contexto próprio
- `/mapear`: entrevista você sobre o dia a dia e cria skills personalizadas
- `/compartilhar`: prepara uma pasta de projeto pra sair daqui como repositório próprio (cliente, sócio)
- `/faxina`: varredura mensal: o que envelheceu, o que estourou o teto, o que está fora do lugar. Só relata
- `/beth`: sua chief of staff. "Beth, o que faço hoje?", "Beth, organiza o projeto X", "Beth, tenho um problema", "Beth, revisão da semana", "Beth, prepara a reunião com Y"
- `/reuniao`: transforma a transcrição de uma reunião em resumo, decisões e tarefas
- `/carrossel` `/proposta-comercial` `/slide` `/publicar-site` `/analisar-dados` `/roteiro-post` `/email-profissional`: modelos prontos que o `/mapear` instala com a sua identidade

**A casa, depois do `/setup`:**

```
seu-negocio/
├── AGENTS.md        as regras, o boot, o mapa e a tabela de destinos (o cérebro, com teto de 180 linhas)
├── CLAUDE.md        uma linha: @AGENTS.md
├── _contexto/       o que o sistema sabe do negócio: empresa, preferências, foco, ferramentas, infra, marca/
├── _memoria/        o que aconteceu e por quê: diario/ (um arquivo por dia), decisoes.md, recados/
├── sistema/         o motor do kit: scripts e modelos. Você não precisa abrir
├── .claude/         as skills e o time de agentes (a Beth distribui o trabalho)
└── clientes/ propostas/ conteudo/ ...   as pastas de trabalho, conforme o seu perfil
```

Três comandos que você vai confundir no começo: `/iniciar` lê, `/atualizar` escreve, `/syncar` manda pro GitHub.

**Se você já tinha a versão anterior do kit** (a que tinha `dados/` e `marca/` na raiz): não precisa
mudar nada se o seu sistema te atende. Quando quiser atualizar: descompacte este kit **ao lado** da
sua pasta, abra o agente dentro da sua pasta e peça pra ele ler `sistema/changelog/COMO-ATUALIZAR.md`
do kit novo. Ele mostra o que mudou, aplica no máximo três coisas por vez, e você decide cada uma.

---

## Ficou travado?

Dúvidas: [catechlabs.com.br](https://catechlabs.com.br)
