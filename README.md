ï»¿# Superpowers

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


Superpowers êÂ© uma metodologia completa de desenvolvimento de software para seus agentes de cêÂ³digo, construêÂ­da sobre um conjunto de skills composêÂ¡veis e algumas instruêÂ§êÂµes iniciais que garantem que seu agente as utilize.

## Como funciona

Tudo comeêÂ§a no momento em que vocêÂª inicializa seu agente de cêÂ³digo. Assim que ele percebe que vocêÂª estêÂ¡ construindo algo, ele *nêÂ£o* simplesmente sai escrevendo cêÂ³digo. Em vez disso, ele dêÂ¡ um passo atrêÂ¡s e pergunta o que vocêÂª realmente quer fazer.

Depois de extrair uma especificaêÂ§êÂ£o da conversa, ele a apresenta em partes pequenas o suficiente para vocêÂª ler e absorver de verdade.

ApêÂ³s vocêÂª aprovar o design, seu agente monta um plano de implementaêÂ§êÂ£o claro o bastante para ser seguido por um engenheiro jêÂºnior entusiasmado, sem bom gosto, sem julgamento, sem contexto do projeto e com aversêÂ£o a testes. O plano enfatiza TDD verdadeiro com ciclo vermelho/verde, YAGNI (You Aren't Gonna Need It) e DRY.

Em seguida, quando vocêÂª diz "vai", ele inicia um processo de *desenvolvimento orientado a subagentes*, fazendo com que agentes trabalhem em cada tarefa de engenharia, inspecionando e revisando o trabalho deles, e avanêÂ§ando. NêÂ£o êÂ© raro o Claude conseguir trabalhar autonomamente por algumas horas sem desviar do plano que vocêÂª elaborou.

Tem muito mais coisa, mas esse êÂ© o nêÂºcleo do sistema. E como as skills sêÂ£o ativadas automaticamente, vocêÂª nêÂ£o precisa fazer nada especial. Seu agente de cêÂ³digo simplesmente tem Superpowers.


## PatrocêÂ­nio

Se o Superpowers te ajudou a fazer coisas que geram dinheiro e vocêÂª estiver disposto, ficaria muito grato se considerasse [patrocinar meu trabalho opensource](https://github.com/sponsors/obra).

Obrigado!

- Jesse


## InstalaêÂ§êÂ£o

**Nota:** A instalaêÂ§êÂ£o varia conforme a plataforma.

### Marketplace Oficial do Claude Code

O Superpowers estêÂ¡ disponêÂ­vel no [marketplace oficial de plugins do Claude](https://claude.com/plugins/superpowers).

Instale o plugin pelo marketplace oficial da Anthropic:

```bash
/plugin install superpowers@claude-plugins-official
```

### Claude Code (Marketplace do Superpowers)

O marketplace do Superpowers oferece o Superpowers e outros plugins relacionados para o Claude Code.

No Claude Code, registre o marketplace primeiro:

```bash
/plugin marketplace add obra/superpowers-marketplace
```

Depois instale o plugin desse marketplace:

```bash
/plugin install superpowers@superpowers-marketplace
```

### OpenAI Codex CLI

- Abra a interface de busca de plugins

```bash
/plugins
```

Busque por Superpowers

```bash
superpowers
```

Selecione `Install Plugin`

### OpenAI Codex App

- No aplicativo Codex, clique em Plugins na barra lateral.
- VocêÂª verêÂ¡ `Superpowers` na seêÂ§êÂ£o Coding.
- Clique no `+` ao lado do Superpowers e siga as instruêÂ§êÂµes.


### Cursor (via Plugin Marketplace)

No chat do Cursor Agent, instale pelo marketplace:

```text
/add-plugin superpowers
```

ou busque por "superpowers" no marketplace de plugins.

### OpenCode

Diga ao OpenCode:

```
Fetch and follow instructions from https://raw.githubusercontent.com/obra/superpowers/refs/heads/main/.opencode/INSTALL.md
```

**DocumentaêÂ§êÂ£o detalhada:** [docs/README.opencode.md](docs/README.opencode.md)

### GitHub Copilot CLI

```bash
copilot plugin marketplace add obra/superpowers-marketplace
copilot plugin install superpowers@superpowers-marketplace
```

### Gemini CLI

```bash
gemini extensions install https://github.com/obra/superpowers
```

Para atualizar:

```bash
gemini extensions update superpowers
```

## O Fluxo de Trabalho BêÂ¡sico

1. **brainstorming** - Ativado antes de escrever cêÂ³digo. Refina ideias brutas atravêÂ©s de perguntas, explora alternativas e apresenta o design em seêÂ§êÂµes para validaêÂ§êÂ£o. Salva o documento de design.

2. **using-git-worktrees** - Ativado apêÂ³s aprovaêÂ§êÂ£o do design. Cria um workspace isolado em um novo branch, executa o setup do projeto e verifica uma baseline limpa de testes.

3. **writing-plans** - Ativado com o design aprovado. Divide o trabalho em tarefas pequenas (2 a 5 minutos cada). Cada tarefa tem caminhos de arquivo exatos, cêÂ³digo completo e etapas de verificaêÂ§êÂ£o.

4. **subagent-driven-development** ou **executing-plans** - Ativado com o plano. Despacha um novo subagente por tarefa com revisêÂ£o em dois estêÂ¡gios (conformidade com a spec e depois qualidade do cêÂ³digo), ou executa em lotes com checkpoints humanos.

5. **test-driven-development** - Ativado durante a implementaêÂ§êÂ£o. Aplica o ciclo VERMELHO-VERDE-REFATORAR: escrever teste que falha, ver ele falhar, escrever cêÂ³digo mêÂ­nimo, ver ele passar, commitar. Deleta cêÂ³digo escrito antes dos testes.

6. **requesting-code-review** - Ativado entre tarefas. Revisa em relaêÂ§êÂ£o ao plano e reporta problemas por severidade. Problemas crêÂ­ticos bloqueiam o progresso.

7. **finishing-a-development-branch** - Ativado quando as tarefas sêÂ£o concluêÂ­das. Verifica os testes, apresenta opêÂ§êÂµes (merge/PR/manter/descartar) e limpa a worktree.

**O agente verifica as skills relevantes antes de qualquer tarefa.** Fluxos obrigatêÂ³rios, nêÂ£o sugestêÂµes.

## O Que EstêÂ¡ IncluêÂ­do

### Biblioteca de Skills

**Testes**
- **test-driven-development** - Ciclo VERMELHO-VERDE-REFATORAR (inclui referêÂªncia de antipadrêÂµes de teste)

**Debugging**
- **systematic-debugging** - Processo de causa raiz em 4 fases (inclui têÂ©cnicas de rastreamento de causa raiz, defesa em profundidade e espera baseada em condiêÂ§êÂµes)
- **verification-before-completion** - Garante que o problema foi realmente corrigido

**ColaboraêÂ§êÂ£o**
- **brainstorming** - Refinamento de design socrêÂ¡tico
- **writing-plans** - Planos de implementaêÂ§êÂ£o detalhados
- **executing-plans** - ExecuêÂ§êÂ£o em lotes com checkpoints
- **dispatching-parallel-agents** - Fluxos de trabalho com subagentes concorrentes
- **requesting-code-review** - Checklist prêÂ©-revisêÂ£o
- **receiving-code-review** - Respondendo ao feedback
- **using-git-worktrees** - Branches de desenvolvimento paralelo
- **finishing-a-development-branch** - Fluxo de decisêÂ£o merge/PR
- **subagent-driven-development** - IteraêÂ§êÂ£o rêÂ¡pida com revisêÂ£o em dois estêÂ¡gios (conformidade com a spec e qualidade do cêÂ³digo)

**Meta**
- **writing-skills** - Crie novas skills seguindo as melhores prêÂ¡ticas (inclui metodologia de teste)
- **using-superpowers** - IntroduêÂ§êÂ£o ao sistema de skills

## Superpowers vs. BMAD

Duas das principais metodologias de desenvolvimento com agentes de IA ê¢â¬â abordagens diferentes para problemas diferentes.

| DimensêÂ£o | BMAD | Superpowers |
|---|---|---|
| **Modelo mental** | Time de agentes com roles fixos (PM, Arquiteto, Dev, UX...) | Skills composêÂ¡veis injetadas em um êÂºnico agente |
| **Escopo** | Ciclo completo: ideia ê¢â â PRD ê¢â â arquitetura ê¢â â stories ê¢â â deploy | Fase têÂ©cnica: planejamento, implementaêÂ§êÂ£o, TDD, revisêÂ£o |
| **Artefatos** | PRD, Architecture Doc, Story Files | Plano de tarefas, spec document, branches de worktree |
| **Foco central** | OrquestraêÂ§êÂ£o de personas e documentaêÂ§êÂ£o estruturada | TDD, subagents, qualidade de cêÂ³digo |
| **DependêÂªncias** | Framework prêÂ³prio com configuraêÂ§êÂ£o | Zero dependêÂªncias ê¢â¬â sêÂ³ prompt |
| **PêÂºblico** | Times que querem processo êÂ¡gil completo | Devs solo/dupla com agente de cêÂ³digo |
| **Filosofia** | "Guie a IA com roles e documentos" | "Automatize boas prêÂ¡ticas de engenharia via skills" |

**BMAD** êÂ© um processo de negêÂ³cio completo ê¢â¬â comeêÂ§a com o Analyst definindo o problema, passa pelo PM, Arquiteto, Scrum Master, e sêÂ³ entêÂ£o chega ao Dev implementando story por story. Ideal para times que querem estrutura êÂ¡gil formal.

**Superpowers** êÂ© mais cirêÂºrgico ê¢â¬â nêÂ£o define personas, define *comportamentos têÂ©cnicos*: TDD antes do cêÂ³digo, plano antes da execuêÂ§êÂ£o, subagentes com revisêÂ£o em 2 estêÂ¡gios. VocêÂª ainda êÂ© o PM e o arquiteto ê¢â¬â o agente sêÂ³ êÂ© mais disciplinado na hora de implementar.

**Na prêÂ¡tica:** os dois sêÂ£o complementares. BMAD decide *o que construir*, Superpowers garante *como construir bem*.

## Filosofia

- **Desenvolvimento Orientado a Testes** - Escreva testes primeiro, sempre
- **SistemêÂ¡tico ao invêÂ©s de ad-hoc** - Processo ao invêÂ©s de adivinhaêÂ§êÂ£o
- **ReduêÂ§êÂ£o de complexidade** - Simplicidade como objetivo principal
- **EvidêÂªncia ao invêÂ©s de afirmaêÂ§êÂµes** - Verifique antes de declarar sucesso

Leia [o anêÂºncio original de lanêÂ§amento](https://blog.fsck.com/2025/10/09/superpowers/).

## Contribuindo

O processo geral de contribuiêÂ§êÂ£o para o Superpowers estêÂ¡ abaixo. Tenha em mente que geralmente nêÂ£o aceitamos contribuiêÂ§êÂµes de novas skills e que qualquer atualizaêÂ§êÂ£o de skills deve funcionar em todos os agentes de cêÂ³digo que suportamos.

1. FaêÂ§a um fork do repositêÂ³rio
2. Mude para o branch 'dev'
3. Crie um branch para o seu trabalho
4. Siga a skill `writing-skills` para criar e testar skills novas e modificadas
5. Envie um PR, tendo o cuidado de preencher o template de pull request

Veja `skills/writing-skills/SKILL.md` para o guia completo.

## Atualizando

As atualizaêÂ§êÂµes do Superpowers dependem um pouco do agente de cêÂ³digo, mas geralmente sêÂ£o automêÂ¡ticas.

## LicenêÂ§a

LicenêÂ§a MIT ê¢â¬â veja o arquivo LICENSE para detalhes.

## Comunidade

O Superpowers êÂ© construêÂ­do por [Jesse Vincent](https://blog.fsck.com) e o restante da equipe da [Prime Radiant](https://primeradiant.com).

- **Discord**: [Junte-se a nêÂ³s](https://discord.gg/35wsABTejz) para suporte da comunidade, perguntas e para compartilhar o que vocêÂª estêÂ¡ construindo com o Superpowers
- **Issues**: https://github.com/obra/superpowers/issues
- **AnêÂºncios de lanêÂ§amento**: [Cadastre-se](https://primeradiant.com/superpowers/) para ser notificado sobre novas versêÂµes

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>