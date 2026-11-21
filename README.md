# Superpowers

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


Superpowers Ã© uma metodologia completa de desenvolvimento de software para seus agentes de cÃ³digo, construÃ­da sobre um conjunto de skills composÃ¡veis e algumas instruÃ§Ãµes iniciais que garantem que seu agente as utilize.

## Como funciona

Tudo comeÃ§a no momento em que vocÃª inicializa seu agente de cÃ³digo. Assim que ele percebe que vocÃª estÃ¡ construindo algo, ele *nÃ£o* simplesmente sai escrevendo cÃ³digo. Em vez disso, ele dÃ¡ um passo atrÃ¡s e pergunta o que vocÃª realmente quer fazer.

Depois de extrair uma especificaÃ§Ã£o da conversa, ele a apresenta em partes pequenas o suficiente para vocÃª ler e absorver de verdade.

ApÃ³s vocÃª aprovar o design, seu agente monta um plano de implementaÃ§Ã£o claro o bastante para ser seguido por um engenheiro jÃºnior entusiasmado, sem bom gosto, sem julgamento, sem contexto do projeto e com aversÃ£o a testes. O plano enfatiza TDD verdadeiro com ciclo vermelho/verde, YAGNI (You Aren't Gonna Need It) e DRY.

Em seguida, quando vocÃª diz "vai", ele inicia um processo de *desenvolvimento orientado a subagentes*, fazendo com que agentes trabalhem em cada tarefa de engenharia, inspecionando e revisando o trabalho deles, e avanÃ§ando. NÃ£o Ã© raro o Claude conseguir trabalhar autonomamente por algumas horas sem desviar do plano que vocÃª elaborou.

Tem muito mais coisa, mas esse Ã© o nÃºcleo do sistema. E como as skills sÃ£o ativadas automaticamente, vocÃª nÃ£o precisa fazer nada especial. Seu agente de cÃ³digo simplesmente tem Superpowers.


## PatrocÃ­nio

Se o Superpowers te ajudou a fazer coisas que geram dinheiro e vocÃª estiver disposto, ficaria muito grato se considerasse [patrocinar meu trabalho opensource](https://github.com/sponsors/obra).

Obrigado!

- Jesse


## InstalaÃ§Ã£o

**Nota:** A instalaÃ§Ã£o varia conforme a plataforma.

### Marketplace Oficial do Claude Code

O Superpowers estÃ¡ disponÃ­vel no [marketplace oficial de plugins do Claude](https://claude.com/plugins/superpowers).

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
- VocÃª verÃ¡ `Superpowers` na seÃ§Ã£o Coding.
- Clique no `+` ao lado do Superpowers e siga as instruÃ§Ãµes.


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

**DocumentaÃ§Ã£o detalhada:** [docs/README.opencode.md](docs/README.opencode.md)

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

## O Fluxo de Trabalho BÃ¡sico

1. **brainstorming** - Ativado antes de escrever cÃ³digo. Refina ideias brutas atravÃ©s de perguntas, explora alternativas e apresenta o design em seÃ§Ãµes para validaÃ§Ã£o. Salva o documento de design.

2. **using-git-worktrees** - Ativado apÃ³s aprovaÃ§Ã£o do design. Cria um workspace isolado em um novo branch, executa o setup do projeto e verifica uma baseline limpa de testes.

3. **writing-plans** - Ativado com o design aprovado. Divide o trabalho em tarefas pequenas (2 a 5 minutos cada). Cada tarefa tem caminhos de arquivo exatos, cÃ³digo completo e etapas de verificaÃ§Ã£o.

4. **subagent-driven-development** ou **executing-plans** - Ativado com o plano. Despacha um novo subagente por tarefa com revisÃ£o em dois estÃ¡gios (conformidade com a spec e depois qualidade do cÃ³digo), ou executa em lotes com checkpoints humanos.

5. **test-driven-development** - Ativado durante a implementaÃ§Ã£o. Aplica o ciclo VERMELHO-VERDE-REFATORAR: escrever teste que falha, ver ele falhar, escrever cÃ³digo mÃ­nimo, ver ele passar, commitar. Deleta cÃ³digo escrito antes dos testes.

6. **requesting-code-review** - Ativado entre tarefas. Revisa em relaÃ§Ã£o ao plano e reporta problemas por severidade. Problemas crÃ­ticos bloqueiam o progresso.

7. **finishing-a-development-branch** - Ativado quando as tarefas sÃ£o concluÃ­das. Verifica os testes, apresenta opÃ§Ãµes (merge/PR/manter/descartar) e limpa a worktree.

**O agente verifica as skills relevantes antes de qualquer tarefa.** Fluxos obrigatÃ³rios, nÃ£o sugestÃµes.

## O Que EstÃ¡ IncluÃ­do

### Biblioteca de Skills

**Testes**
- **test-driven-development** - Ciclo VERMELHO-VERDE-REFATORAR (inclui referÃªncia de antipadrÃµes de teste)

**Debugging**
- **systematic-debugging** - Processo de causa raiz em 4 fases (inclui tÃ©cnicas de rastreamento de causa raiz, defesa em profundidade e espera baseada em condiÃ§Ãµes)
- **verification-before-completion** - Garante que o problema foi realmente corrigido

**ColaboraÃ§Ã£o**
- **brainstorming** - Refinamento de design socrÃ¡tico
- **writing-plans** - Planos de implementaÃ§Ã£o detalhados
- **executing-plans** - ExecuÃ§Ã£o em lotes com checkpoints
- **dispatching-parallel-agents** - Fluxos de trabalho com subagentes concorrentes
- **requesting-code-review** - Checklist prÃ©-revisÃ£o
- **receiving-code-review** - Respondendo ao feedback
- **using-git-worktrees** - Branches de desenvolvimento paralelo
- **finishing-a-development-branch** - Fluxo de decisÃ£o merge/PR
- **subagent-driven-development** - IteraÃ§Ã£o rÃ¡pida com revisÃ£o em dois estÃ¡gios (conformidade com a spec e qualidade do cÃ³digo)

**Meta**
- **writing-skills** - Crie novas skills seguindo as melhores prÃ¡ticas (inclui metodologia de teste)
- **using-superpowers** - IntroduÃ§Ã£o ao sistema de skills

## Superpowers vs. BMAD

Duas das principais metodologias de desenvolvimento com agentes de IA â€” abordagens diferentes para problemas diferentes.

| DimensÃ£o | BMAD | Superpowers |
|---|---|---|
| **Modelo mental** | Time de agentes com roles fixos (PM, Arquiteto, Dev, UX...) | Skills composÃ¡veis injetadas em um Ãºnico agente |
| **Escopo** | Ciclo completo: ideia â†’ PRD â†’ arquitetura â†’ stories â†’ deploy | Fase tÃ©cnica: planejamento, implementaÃ§Ã£o, TDD, revisÃ£o |
| **Artefatos** | PRD, Architecture Doc, Story Files | Plano de tarefas, spec document, branches de worktree |
| **Foco central** | OrquestraÃ§Ã£o de personas e documentaÃ§Ã£o estruturada | TDD, subagents, qualidade de cÃ³digo |
| **DependÃªncias** | Framework prÃ³prio com configuraÃ§Ã£o | Zero dependÃªncias â€” sÃ³ prompt |
| **PÃºblico** | Times que querem processo Ã¡gil completo | Devs solo/dupla com agente de cÃ³digo |
| **Filosofia** | "Guie a IA com roles e documentos" | "Automatize boas prÃ¡ticas de engenharia via skills" |

**BMAD** Ã© um processo de negÃ³cio completo â€” comeÃ§a com o Analyst definindo o problema, passa pelo PM, Arquiteto, Scrum Master, e sÃ³ entÃ£o chega ao Dev implementando story por story. Ideal para times que querem estrutura Ã¡gil formal.

**Superpowers** Ã© mais cirÃºrgico â€” nÃ£o define personas, define *comportamentos tÃ©cnicos*: TDD antes do cÃ³digo, plano antes da execuÃ§Ã£o, subagentes com revisÃ£o em 2 estÃ¡gios. VocÃª ainda Ã© o PM e o arquiteto â€” o agente sÃ³ Ã© mais disciplinado na hora de implementar.

**Na prÃ¡tica:** os dois sÃ£o complementares. BMAD decide *o que construir*, Superpowers garante *como construir bem*.

## Filosofia

- **Desenvolvimento Orientado a Testes** - Escreva testes primeiro, sempre
- **SistemÃ¡tico ao invÃ©s de ad-hoc** - Processo ao invÃ©s de adivinhaÃ§Ã£o
- **ReduÃ§Ã£o de complexidade** - Simplicidade como objetivo principal
- **EvidÃªncia ao invÃ©s de afirmaÃ§Ãµes** - Verifique antes de declarar sucesso

Leia [o anÃºncio original de lanÃ§amento](https://blog.fsck.com/2025/10/09/superpowers/).

## Contribuindo

O processo geral de contribuiÃ§Ã£o para o Superpowers estÃ¡ abaixo. Tenha em mente que geralmente nÃ£o aceitamos contribuiÃ§Ãµes de novas skills e que qualquer atualizaÃ§Ã£o de skills deve funcionar em todos os agentes de cÃ³digo que suportamos.

1. FaÃ§a um fork do repositÃ³rio
2. Mude para o branch 'dev'
3. Crie um branch para o seu trabalho
4. Siga a skill `writing-skills` para criar e testar skills novas e modificadas
5. Envie um PR, tendo o cuidado de preencher o template de pull request

Veja `skills/writing-skills/SKILL.md` para o guia completo.

## Atualizando

As atualizaÃ§Ãµes do Superpowers dependem um pouco do agente de cÃ³digo, mas geralmente sÃ£o automÃ¡ticas.

## LicenÃ§a

LicenÃ§a MIT â€” veja o arquivo LICENSE para detalhes.

## Comunidade

O Superpowers Ã© construÃ­do por [Jesse Vincent](https://blog.fsck.com) e o restante da equipe da [Prime Radiant](https://primeradiant.com).

- **Discord**: [Junte-se a nÃ³s](https://discord.gg/35wsABTejz) para suporte da comunidade, perguntas e para compartilhar o que vocÃª estÃ¡ construindo com o Superpowers
- **Issues**: https://github.com/obra/superpowers/issues
- **AnÃºncios de lanÃ§amento**: [Cadastre-se](https://primeradiant.com/superpowers/) para ser notificado sobre novas versÃµes

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>