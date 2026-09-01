---
marp: true
title: MoveUni — Pitch
description: Pitch da ideia MoveUni
paginate: true
theme: default
class: lead
---

<!--
Apresentação de slides em Markdown (Marp).
Exportar: `marp docs/pitch.md --pdf` (ou --pptx / --html)
ou use a extensão "Marp for VS Code".
-->

# MoveUni

### Encontre gente pra jogar. Sem grupo de WhatsApp.

Um app que conecta estudantes por esporte, nível e disponibilidade — e fecha as partidas sozinho.

---

## O problema

- Organizar esporte na faculdade é **manual e caótico**: grupos de mensagem, corrente de "quem topa?".
- As **janelas livres** entre aulas são curtas e nunca batem entre as pessoas.
- **Nível misturado**: iniciante cai em jogo avançado — experiência ruim pros dois lados.
- Quem organiza **cansa de divulgar** o mesmo horário em vários canais toda semana.

> Muita gente quer jogar. A partida simplesmente não acontece.

---

## A ideia

O estudante cadastra **uma vez**:

1. **Esportes** que pratica
2. **Nível** em cada esporte — iniciante / intermediário / avançado
3. **Disponibilidade** de dias e horários

E o MoveUni faz o resto: agrupa, forma os times, fecha a partida e avisa todo mundo.

---

## Como funciona

```
  Estudante marca:  esporte + nível + disponibilidade
                          │
                          ▼
     Motor de matchmaking cruza horário × esporte × nível
                          │
             ┌────────────┴────────────┐
             ▼                         ▼
     Fecha 2 times pro jogo    Fecha grupo de corrida
             └────────────┬────────────┘
                          ▼
   Evento entra no calendário  +  notificação de confirmação
```

Duas atividades possíveis no mesmo horário? **Vence a que tem mais interessados.**

---

## Por que é diferente

| | Grupo de mensagem / planilha | MoveUni |
|---|---|---|
| Formar time | Na mão, "quem topa?" | **Automático** por disponibilidade |
| Nível | Só descobre jogando | **Explícito** por esporte; nível médio à vista |
| Horário | Renegociado toda semana | **Calendário** com entrada aberta |
| Organizador | Divulga em vários canais | **Cria uma vez**, os outros se incluem |

---

## Para quem é

**🎓 Lucas, o Calouro Casual — 19**
Sem turma fixa, agenda irregular. Quer jogar com gente do seu nível sem organizar nada.

**🏐 Marina, a Atleta Competitiva — 22**
Joga vôlei avançado. Precisa saber o **nível médio da partida antes de entrar**.

**🏃 Rafael, o Organizador de Corrida — 24**
Corre todo dia. Quer marcar o horário **uma vez** e deixar os outros se incluírem.

---

## O produto

**Essencial**

- Perfil esportivo + disponibilidade por dia e horário
- Agrupamento automático e fechamento da partida ao atingir o mínimo
- Nível por esporte; nível médio exibido quando o grupo é misto
- Calendário de eventos e entrada em partidas com vaga

**A seguir**

- Notificações de confirmação · filtro por esporte / nível / horário
- Priorização da atividade com mais interessados

---

## Como sabemos que entrega

- **Rápido**: sugestão de agrupamento em até **3 segundos** após marcar disponibilidade.
- **Mobile-first**: marcar disponibilidade em no máximo **3 toques** desde a tela inicial.
- **Seguro**: login por e-mail institucional, senha criptografada.
- **Confiável**: fechamento de partida e confirmação de presença são persistidos de forma consistente.

---

## Por baixo do capô

- **Cliente-servidor, monólito modular** — simples de evoluir, fácil de manter.
- Web **mobile-first**, roda no navegador em Android e iOS — sem app nativo.
- Núcleo: **motor de matchmaking** (horário × esporte × nível), calendário e notificações.
- Organização em camadas (**MVC + casos de uso**) sobre banco **relacional**.
- Stack de implementação: **Python** (Flask / FastAPI) + banco SQL.

---

## Modelo de dados

```
USUARIO ──< USUARIO_ESPORTE >── ESPORTE
   │                              │
   ├──< DISPONIBILIDADE           └──< EVENTO
   │                                    │
   ├──< PARTICIPACAO >──────────────────┘
   │
   └──< NOTIFICACAO
```

Entidades centrais: **Usuário, Esporte, Disponibilidade, Evento, Participação, Notificação.**

---

## Roadmap

| Fase | Entrega |
|---|---|
| **1 — Fundação** | Perfil, disponibilidade, matchmaking, fechamento de partida, calendário |
| **2 — Experiência** | Notificações, filtros, edição de perfil, entrada em eventos |
| **3 — Escala** | Priorização por interesse, níveis mistos, crescimento de usuários simultâneos |

---

## Time

| | | |
|---|---|---|
| **Gabriel Mendonça** | Produto & Dev | [@MagiMahou](https://github.com/MagiMahou) |
| **Timóteo Stifft** | Produto & Dev | [@timoteostifft](https://github.com/timoteostifft) |

---

<!-- _class: lead -->

# MoveUni

### Menos organização. Mais jogo.

Obrigado — perguntas?
