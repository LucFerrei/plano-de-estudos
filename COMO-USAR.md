# Como usar este repo

Guia rápido de como operar o plano no dia a dia e como usar IA pra avaliar teu progresso.

---

## 1. Os arquivos e seus papéis

| Arquivo | Papel | Quando abrir |
|---|---|---|
| `plano-de-estudos.md` | O **mapa** (o que e por quê) | 1×/semana, ou quando se perder |
| `progresso.md` | O **diário** (onde estou) | Todo dia, antes e depois da sessão |
| `README.md` | O **lembrete** (rotina + regras) | Quando esquecer o básico |
| `COMO-USAR.md` | Este guia | Quando esquecer a mecânica |

---

## 2. Rotina de uso

1. **Antes da sessão (30s):** abrir `progresso.md`, ver o próximo checkbox não marcado.
2. **Durante:** fazer o drill/projeto (sem IA na escrita).
3. **Depois (2 min):** marcar o checkbox + escrever 3–5 linhas na seção **"Notas"** — o que aprendeu, onde travou.
4. **Domingo (15 min):** revisar a semana, conferir a seção **"Metas mensais"**, e fazer `git commit` + `push`.
5. **Fim do mês:** revisar os **"testes de saída"** de cada fase e as metas do mês.

> A seção **"Notas"** é o que torna o progresso visível. Sem nota, a sessão evapora.

---

## 3. Usar IA pra avaliar progresso

A IA avalia, mas **não responde por você** — ela vira examinadora, não gabarito.

### A. Sabatina (testar se você sabe explicar)
```
Me faça 5 perguntas sobre closures, uma de cada vez.
Só mostre a próxima depois que eu responder.
No fim, me diga onde eu errei e o que ficou raso.
```
Testa *explicação*, que prova entendimento de verdade — não o código.

### B. Revisão das tuas notas
Escreve a explicação *você* (nas Notas), depois:
```
Revise minha explicação sobre event loop. Aponte erros e lacunas.
Seja crítico, não me passe a mão na cabeça.
```

### C. Corrigir teu exercício (sem dar a resposta antes)
Faz o exercício sem IA, cola teu código:
```
Revise meu código, aponte 3 problemas.
Não me mostre a solução ainda — me diga o problema e me deixe corrigir.
```

### D. Gerar prova com gabarito escondido
Ela cria, você resolve, ela corrige:
```
Gere 3 exercícios sobre tipos e coerção em JS.
Guarde as respostas. Eu vou resolver e te mandar pra corrigir.
```

### Ritual semanal
Todo domingo, cola o `progresso.md` (ou um resumo):
```
Avalie meu progresso da semana contra o plano.
O que está raso? O que eu deveria revisar antes de avançar?
```

> **Atenção:** peça sempre pra IA ser **estrita**. O risco é ela dizer "muito bem!" e você achar que domina o que não domina. Termo mágico: *"seja crítico, aponte o que está errado ou incompleto, não elogie."*
