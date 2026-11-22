# Progresso

Log de progresso do plano. Marque os checkboxes conforme avança. Atualize a data ao lado de cada seção concluída.

## Como usar
- Registre no fim de cada sessão: o que estudou, onde parou, o que travou.
- Mantenha 3–5 linhas por tópico na seção "Notas".

---

## Fase 0 — Setup (Semana 1, rápido)

- [ ] Node + debugger no Neovim (nvim-dap + nvim-dap-ui) funcionando
- [ ] Log de progresso criado
- [ ] (Opcional) Teste de nivelamento antes/depois

## Fase 1 — Modelo mental de JavaScript (Semanas 2–6)

Cada tópico: **ler → 2–3 exercícios do zero (sem IA) → nota de 3–5 linhas**.

- [ ] 1. Tipos e coerção (`==`/`===`, truthy/falsy, `NaN`)
- [ ] 2. Escopo, hoisting, `let`/`const`, temporal dead zone
- [ ] 3. Closures (a fundo)
- [ ] 4. `this` (as 4 regras) e arrow functions
- [ ] 5. Protótipos e classes
- [ ] 6. Funções de ordem superior, iteradores
- [ ] 7. Event loop: call stack, task/microtask, promises, async/await
- [ ] 8. Módulos ESM/CJS e o bundler (Vite)
- [ ] 9. Erros: `try/catch/finally`, propagação, erro em async

**Teste de saída da fase:** explicar os 9 tópicos sem consultar + 2 exercícios de cada, sem IA.

- [ ] Teste de saída concluído

## Fase 2 — TypeScript profundo (Semanas 7–9)

- [ ] `unknown` vs `any`, narrowing, type guards, generics, mapped/conditional types, `satisfies`, `as const`
- [ ] `tsconfig` a fundo (`strict`, `noUncheckedIndexedAccess`, etc.)
- [ ] Type erasure (compilador vs runtime)
- [ ] 5+ type-challenges (fáceis → médios), sem IA

## Fase 3 — Ler código + depurar (contínua)

Semana a semana:

- [ ] Semana 3 — 1 arquivo do codebase lido e documentado
- [ ] Semana 4 — 1 arquivo lido + confirmado no debugger
- [ ] Semana 5 — 1 arquivo lido
- [ ] Semana 6 — 1 arquivo lido (total 4+ até o fim do mês 2)
- [ ] Breakpoint condicional, call stack, watch, step into/over dominados
- [ ] 1 bug real depurado só com breakpoint (meta do mês 3)

## Fase 4 — Escrever do zero (projetos mensais)

- [ ] Mês 1 — CLI em Node (mini grep ou parser de CSV), sem framework
- [ ] Mês 2 — Utilitário tipado em TS com testes (vitest)
- [ ] Mês 3 — Reescrever parte do app do trabalho em React/TS
- [ ] Regra aplicada em todos: commits pequenos + testes + PR pra si mesmo

## Trilha Rust (apoio)

- [ ] Semana 1
- [ ] Semana 2
- [ ] Semana 3
- [ ] Semana 4
- [ ] Semana 5
- [ ] Semana 6
- [ ] Semana 7
- [ ] Semana 8
- [ ] Semana 9
- [ ] Semana 10
- [ ] Semana 11
- [ ] Semana 12

## Trilha Backend/Infra (enxuta)

### Módulo B1 — SQL e Postgres
- [ ] SELECT, WHERE, ORDER BY, LIMIT
- [ ] JOIN (INNER/LEFT) e GROUP BY + HAVING, agregações
- [ ] Subqueries e CTEs (WITH)
- [ ] Índices (o que são, quando ajudam, EXPLAIN)
- [ ] Transactions (ACID, BEGIN/COMMIT/ROLLBACK)
- [ ] Constraints e modelagem mínima (PK/FK)
- [ ] Aplicado: entender as queries do banco do trabalho (ou do weekly)
- [ ] Recurso: SQLZoo + "Use the Index, Luke"

### Módulo B2 — CI/CD e GitHub Actions
- [ ] CI vs CD
- [ ] Workflow, job, step, action, trigger, secrets, environments
- [ ] Workflow real: lint + test + build
- [ ] Deploy básico (dev/prod, aprovação, rollback)
- [ ] Aplicado: CI de um projeto do trabalho
- [ ] Recurso: docs do GitHub Actions

### Módulo B3 — Filas (message queues)
- [ ] Por que filas (desacoplar, retry, backpressure)
- [ ] Producer/consumer, acknowledgement, redelivery
- [ ] DLQ e retry com backoff
- [ ] Idempotência do consumer
- [ ] Ferramenta: Redis / BullMQ / SQS
- [ ] Aplicado: fila simples num projeto do trabalho
- [ ] Recurso: docs do BullMQ/SQS

## Trilha IA

### Parte A — Fundamentos (semanas 1–3)
- [ ] 1. LLM prediz próximo token (não "pensa")
- [ ] 2. Tokens e janela de contexto
- [ ] 3. System prompt × user prompt × histórico
- [ ] 4. Parâmetros (temperatura, max_tokens)
- [ ] 5. O loop do agente (contexto → modelo → tool → resultado)
- [ ] 6. Permissões e riscos

### Parte B — Técnicas de uso (uma por semana)
- [ ] Plano antes de código
- [ ] Contexto de qualidade
- [ ] Critérios de aceite
- [ ] Iterar e criticar
- [ ] Few-shot
- [ ] Saber quando parar

### Parte C — Ferramentas
OpenCode:
- [ ] `opencode.json` (model, agent, permissions, instructions, references, mcp, skills)
- [ ] `AGENTS.md` / `instructions` / `references` no projeto do trabalho
- [ ] Subagentes
- [ ] MCP (`opencode mcp add`)
- [ ] Permissions
- [ ] Skills e commands
- [ ] `opencode api`
- [ ] Doc oficial lida (1 seção/semana)

Claude Code:
- [ ] `CLAUDE.md`
- [ ] Slash commands
- [ ] MCP e hooks
- [ ] Permissões

### Parte D — Custo/latência e API
- [ ] Escolha de modelo por tarefa
- [ ] Prompt caching
- [ ] Contagem de tokens / estimativa de custo
- [ ] Function calling + structured output + streaming
- [ ] Medição de custo/latência antes/depois (meta do mês 3)

---

## Metas mensais

### Mês 1
- [ ] 9 tópicos de JS explicáveis sem consultar + 2 exercícios cada, sem IA
- [ ] SQL do zero até JOIN + transaction; explicar uma query real do trabalho
- [ ] Explicar o loop agente→tool→modelo
- [ ] `AGENTS.md`/`CLAUDE.md` criados no projeto do trabalho
- [ ] "Plano antes de código" em toda tarefa

### Mês 2
- [ ] 5+ type-challenges resolvidos
- [ ] 4 arquivos do codebase lidos e documentados
- [ ] Pipeline CI/CD funcional (lint+test+build) no projeto do trabalho
- [ ] Permissions/MCP/subagentes dominados
- [ ] Prompt caching + escolha de modelo aplicados
- [ ] 5 técnicas de IA registradas no log

### Mês 3
- [ ] 2 projetos pequenos sem IA
- [ ] 1 bug real depurado só com breakpoint
- [ ] Fila modelada/implementada com retry/idempotência
- [ ] 1 automação com a API (function calling/structured output)
- [ ] Custo/latência medidos antes/depois e documentados

---

## Notas

<!-- Adicione 3–5 linhas por tópico/sessão aqui. Exemplo:
### 2026-XX-XX — Closures
- Entendi que closure captura a variável (referência), não o valor.
- Travou: diferença entre let e var no loop. Rever com exercício.
-->
