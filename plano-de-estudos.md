# Plano de Ação — Dev, Backend e IA

> Objetivo dos próximos 3 meses: **ler o codebase do trabalho e escrever features do zero** (JS/TS), **lidar com banco/filas/CI-CD** no dia a dia, e **usar IA como revisor/multiplicador** — não como autor.
>
> 📚 Fontes de estudo (primária × secundária) consolidadas em [`recursos.md`](recursos.md).

---

## 1. Diagnóstico

| Força | Gargalo |
|---|---|
| Rust com arquitetura limpa (domain/ports/infra) | Dependência de IA como "digitador" |
| TypeScript intermediário (tipos, unions, genéricos) | Falta o modelo mental de JavaScript por baixo |
| Muita amplitude (Rust, C, Lua, Nix, TS) | Pouca consolidação — superfície, não profundidade |
| Já tem disciplina de estudo (cs-studies) | Plano gigante demais pra sustentar |

O código TS já é bom (usa genéricos, discriminated unions, `Extract`). O que falta não é sintaxe — é a **camada de baixo** (runtime/JS) e as **práticas de engenharia** (ler código, depurar, escrever do zero). IA idem: **uso, mas nunca estudei** — falta o modelo mental de como a ferramenta funciona. E os temas de **backend/infra** (banco, filas, CI/CD) aparecem no trabalho e precisam entrar de forma enxuta.

---

## 2. Rotina semanal

| Bloco | Frequência | Duração | O que é |
|---|---|---|---|
| Drill diário (JS) | 5×/semana | 30–40 min | Fundamentos de JS, **sem IA** |
| Bloco de projeto | 1×/semana | 3–4h | Escrever do zero, ler código, debuggar — **IA só como revisor** |
| Bloco backend/infra | 1×/semana | 1–1,5h | SQL, filas, CI/CD — aplicado no trabalho |
| Bloco de IA | 1×/semana | 1–1,5h | Fundamentos + dominar OpenCode/Claude Code (semanas 1–4), depois vira hábito |
| Trilha Rust | 1×/semana | 30–60 min | Manter o que gosto, leve |

Total ~9,5h, com folga até 10h+. O bloco de IA encolhe depois da semana 4 e **vira técnica aplicada** nas outras sessões. Se apertar, a primeira trilha a encolher é a de Rust.

---

## 3. Como usar IA (as duas faces)

A trilha de IA não substitui as regras de guardrail — ela depende delas. Você só julga se uma resposta é boa se entende o código.

### Regras de aprendizado (evitar dependência)
1. IA é tutor, não digitador.
2. 15–30 min de luta antes de pedir.
3. Reescrever, não copiar.
4. Explicar de volta: todo código aceito, você explica linha por linha.
5. Prática (katas) é 100% sem IA.
6. IA pra gerar exercícios e revisões, não respostas.

### Técnicas de performance (tirar mais valor)
1. **Plano antes de código** — peça o desenho/plano, aprove, só então deixe escrever.
2. **Contexto de qualidade** — arquivo certo, erro exato, stack trace, o que já tentou. Lixo no contexto = resposta ruim + custo alto.
3. **Critérios de aceite** — diga o que "pronto" significa e peça pra revisar contra isso.
4. **Iterar e criticar** — "aponte 3 problemas", "dê uma alternativa".
5. **Few-shot** — mostre 1–2 exemplos do teu código como referência.
6. **Saber quando parar** — se a conversa piorar, reinicie com um resumo em vez de arrastar contexto poluído.

---

## 4. Trilha Dev

### Fase 0 — Semana 1: Setup (rápido)
- [ ] **Setup:** Node + debugger no Neovim (`nvim-dap` + `nvim-dap-ui`) funcionando (breakpoint, call stack, watch).
- [ ] Log de progresso criado (`progresso.md`).
- [ ] *(Opcional)* Teste de nivelamento antes/depois, só se quiser medir evolução — não é obrigatório, já que vamos ver tudo do zero.

### Fase 1 — Semanas 2–6: O modelo mental de JavaScript
Revisitar o básico com profundidade, nessa ordem:
1. Tipos e coerção (`==`/`===`, truthy/falsy, `NaN`)
2. Escopo, hoisting, `let`/`const`, temporal dead zone
3. Closures (a fundo)
4. `this` (as 4 regras) e arrow functions
5. Protótipos e classes (sugar syntax)
6. Funções de ordem superior (`map`/`filter`/`reduce`), iteradores
7. **Event loop:** call stack, task queue, microtasks, promises, async/await "desaçucarado"
8. Módulos ESM/CJS e o que o bundler (Vite) faz por cima
9. Erros: `try/catch/finally`, propagação, erro em async

**Método por tópico:** ler → 2–3 exercícios do zero (sem IA) → nota de 3–5 linhas.
**Recurso principal:** *You Don't Know JS* (YDKJS, 2ª ed., grátis no GitHub). Referência: MDN e javascript.info.

### Fase 2 — Semanas 7–9: TypeScript profundo
- [ ] `unknown` vs `any`, narrowing, type guards, generics, mapped/conditional types, `satisfies`, `as const`.
- [ ] `tsconfig` a fundo (o que `strict`, `noUncheckedIndexedAccess` fazem).
- [ ] **Type erasure:** tipo não existe em runtime — diferença entre compilador e Node.
- [ ] Prática: resolver [type-challenges](https://github.com/type-challenges/type-challenges) (fáceis → médios), sem IA.

### Fase 3 — Transversal (da semana 3 em diante, contínua): Ler código + depurar
- [ ] **Leitura (1×/semana, 30–45 min):** pegar um arquivo do codebase do trabalho (não o meu) e traçar: entry point → fluxo. Anotar. Confirmar no debugger.
- [ ] **Debuggar com breakpoint, nunca `console.log` primeiro.** No `nvim-dap`: breakpoint condicional, call stack, watch, step into/over.
- [ ] Recurso: *The Programmer's Brain* (Felienne Hermans) — capítulos de leitura de código.

### Fase 4 — Contínua: Escrever do zero (projetos mensais)
Um projeto pequeno por mês, **100% sem IA na escrita** (IA só pra review):
- [ ] **Mês 1 (JS puro):** CLI em Node — mini grep ou parser de CSV. Sem framework.
- [ ] **Mês 2 (TS):** utilitário tipado — `debounce`/`throttle`, fila de promessas ou mini state manager. Com testes (vitest).
- [ ] **Mês 3 (React/TS):** reescrever uma parte pequena do app do trabalho de forma independente.
- [ ] Regra: commits pequenos, testes, PR pra si mesmo.

### Trilha Rust (apoio)
- [ ] 1 kata por semana (Exercism/rustlings) ou 1 capítulo do Rust Book que faltou (16–21), ou melhorar o `weekly`.

---

## 5. Trilha Backend/Infra (enxuta)

Objetivo: as 3 coisas que você precisa **no trabalho**, sem a teoria pesada — SQL/banco, CI/CD, filas. Aplique direto no contexto real (banco do trabalho, projeto do trabalho). **CAP theorem fica de fora** por ora (teoria de sistemas distribuídos).

### Módulo B1 — SQL e Postgres (~4 semanas)
- [ ] `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`
- [ ] `JOIN` (INNER/LEFT) e `GROUP BY` + `HAVING`, agregações
- [ ] Subqueries e CTEs (`WITH`)
- [ ] Índices: o que são, quando ajudam, `EXPLAIN`
- [ ] Transactions: ACID, `BEGIN`/`COMMIT`/`ROLLBACK`, isolamento básico
- [ ] Constraints e modelagem mínima (PK/FK, normalização na prática)
- [ ] **Aplicado:** rodar e entender as queries do banco do trabalho (ou do `weekly`, sqlx + Postgres); saber o que o ORM/query builder gera
- [ ] Recurso: SQLZoo + "Use the Index, Luke"

### Módulo B2 — CI/CD e GitHub Actions (~3 semanas)
- [ ] CI vs CD, por que pipeline
- [ ] GitHub Actions: workflow, job, step, action, trigger, secrets, environments
- [ ] Workflow real: lint + test + build
- [ ] Deploy básico: ambientes (dev/prod), aprovação, rollback
- [ ] **Aplicado:** criar o CI de um projeto do trabalho (ou do teu repo)
- [ ] Recurso: docs do GitHub Actions + o workflow do teu `cs-studies` como base

### Módulo B3 — Filas (message queues) (~4 semanas)
- [ ] Por que filas: desacoplar, retry, backpressure, trabalho async
- [ ] Producer/consumer, acknowledgement, redelivery
- [ ] Dead letter queue (DLQ) e retry com backoff
- [ ] Idempotência do consumer (por que importa)
- [ ] Ferramenta: Redis (já usa) ou BullMQ (TS) / SQS
- [ ] **Aplicado:** modelar/implementar uma fila simples num projeto do trabalho
- [ ] Recurso: docs do BullMQ/SQS

**Como encaixar:** um bloco de ~1–1,5h/semana, aplicando direto nas tarefas reais do trabalho. Isso é estudo que vira trabalho — não é tempo "extra" jogado fora.

---

## 6. Trilha IA

### Parte A — Fundamentos mínimos (semanas 1–3, dedicado)
1. [ ] **O que um LLM faz de verdade:** prediz o próximo token; não "pensa". Consequências: alucina, é literal, só sabe o que está no contexto.
2. [ ] **Tokens e janela de contexto:** o que o modelo "vê", por que contexto demais = ruído + custo.
3. [ ] **System prompt × user prompt × histórico:** como cada um pesa.
4. [ ] **Parâmetros:** temperatura, `max_tokens` — quando mexer.
5. [ ] **O loop do agente:** prompt → monta contexto (arquivos, ferramentas) → chama o modelo → modelo decide chamar tool (ler, rodar) → resultado volta → modelo decide de novo.
6. [ ] **Permissões e riscos:** o que o agente *pode* fazer (ler/escrever, shell, web) e o perigo de deixar solto.

### Parte B — Técnicas de uso (contínua)
As 6 técnicas da seção 3, uma por semana, aplicadas de propósito nas sessões de dev.

### Parte C — Dominar as ferramentas (OpenCode + Claude Code)
**OpenCode** (o que já uso):
- [ ] `opencode.json`: `model`, `default_agent`, `permissions`, `instructions`, `references`, `agents`, `commands`, `mcp`, `skills`.
- [ ] **`AGENTS.md` / `instructions` / `references`** — contexto de projeto que se repete (ganho nº 1 de produtividade).
- [ ] **Subagentes** — explorar/ler código em paralelo sem poluir a sessão principal.
- [ ] **MCP** — conectar fontes externas via `opencode mcp add <nome> --url <url>`.
- [ ] **Permissions** — controlar o que o agente pode fazer.
- [ ] **Skills e commands** — automatizar fluxos recorrentes.
- [ ] **API** — `opencode api` pra automatizar fora do TUI.
- [ ] Ler a doc oficial (opencode.ai/docs), uma seção por semana, testando na hora.

**Claude Code:**
- [ ] `CLAUDE.md` (contexto de projeto), slash commands, MCP, hooks, permissões.

### Parte D — Custo/latência e a API (depois da base, ~1h/semana)
1. [ ] **Escolha de modelo:** grande pra raciocínio/arquitetura; pequeno/rápido pra tarefa mecânica.
2. [ ] **Prompt caching:** reaproveitar o prefixo (system + instruções fixas) corta custo e latência.
3. [ ] **Contar tokens:** estimar o custo de um prompt antes de mandar.
4. [ ] **API na prática:** function calling, structured output (JSON schema), streaming.
5. [ ] **Medir:** anotar tokens/custo por tarefa, antes/depois.

---

## 7. Metas de 3 meses

### Dev
- **Mês 1:** explicar os 9 tópicos de JS sem consultar + resolver 2 exercícios de cada, sem IA.
- **Mês 2:** 5+ type-challenges + ler e documentar 4 arquivos do codebase do trabalho.
- **Mês 3:** 2 projetos pequenos sem IA + depurar 1 bug real só com breakpoint.

### Backend
- **Mês 1:** SQL do zero até `JOIN` + transaction; explicar uma query real do trabalho.
- **Mês 2:** CI/CD — pipeline funcional (lint + test + build) num projeto do trabalho.
- **Mês 3:** filas — modelar/implementar uma fila com retry/idempotência.

### IA
- **Mês 1:** explicar o loop agente→tool→modelo + criar `AGENTS.md`/`CLAUDE.md` no projeto do trabalho + usar "plano antes de código" em toda tarefa.
- **Mês 2:** dominar permissions/MCP/subagentes + aplicar prompt caching e escolha de modelo + registrar 5 técnicas aplicadas no log.
- **Mês 3:** automatizar algo com a API (function calling/structured output) + medir custo/latência antes/depois e documentar o ganho.

---

## 8. Fora do escopo (por ora)

Backlog opcional — só depois de consolidar o básico:
- **CAP theorem** e teoria de sistemas distribuídos (volta junto com o `cs-studies`).
- O `cs-studies` completo (OSTEP, redes, Cormen).
