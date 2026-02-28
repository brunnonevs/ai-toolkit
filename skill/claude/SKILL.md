# Skills para Claude

Skills são instruções especializadas que melhoram a qualidade das respostas do Claude para tarefas específicas.

---

## O que é uma Skill?

Uma skill é um arquivo de texto (geralmente `SKILL.md`) que contém:
- **Contexto** — explica o domínio ou tarefa
- **Instruções** — como o Claude deve se comportar
- **Exemplos** — inputs e outputs esperados
- **Boas práticas** — dicas condensadas de trial and error

---

## 📋 Template padrão de skill

```markdown
# [Nome da Skill]

## Objetivo
[O que esta skill ensina o Claude a fazer]

## Contexto
[Informações de background que o Claude precisa saber]

## Instruções
1. [Passo ou regra 1]
2. [Passo ou regra 2]
3. [Passo ou regra 3]

## Exemplos

### Exemplo 1
**Input:** [o que o usuário pede]
**Output esperado:** [como o Claude deve responder]

## Boas práticas
- [Dica 1]
- [Dica 2]

## Erros comuns a evitar
- [Erro 1]
- [Erro 2]
```

---

## Como usar uma skill

Cole o conteúdo da skill no início da sua conversa com o Claude, ou use como system prompt via API.

---

## Skills disponíveis

| Nome | Descrição | Arquivo |
|------|-----------|---------|
| *(em breve)* | *(adicione suas skills aqui)* | - |
