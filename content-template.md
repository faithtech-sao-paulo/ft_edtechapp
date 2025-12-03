# Template para Criação de Conteúdo

Use este template para organizar seu texto antes de converter para JSON.

## 🎯 Planejamento da Lição

**Curso:** _____________________
**Lição:** _____________________
**Tempo Estimado:** _____ minutos
**Objetivo:** _____________________

---

## 📝 Estrutura (Ciclo E.R.A.)

### DROP 1: GANCHO (10 segundos)
**Objetivo:** Capturar atenção com pergunta instigante ou fato curioso

**Mensagem 1:**
```
[Texto da mensagem - máx 280 caracteres]
Exemplo: "Você sabia que 80% dos adultos têm medo de matemática? 🤔"
```

**Mensagem 2 (opcional):**
```
[Texto de continuação]
Exemplo: "Vamos descobrir por que isso acontece e como superar!"
```

**Botão de Ação:** "Vamos lá!" / "Quero saber!" / "Continuar"

---

### DROP 2: CONCEITO (30-60 segundos)
**Objetivo:** Explicar o conceito usando storytelling

**História/Contexto:**
```
[Conte uma história curta que ilustre o conceito]
Exemplo: "Maria precisava calcular o troco no mercado..."
```

**Explicação do Conceito:**
```
[Explique em 1-2 parágrafos curtos, com negrito e emojis]
Exemplo: "Ela usou a **técnica do arredondamento** 💡"
```

**Mensagens:**
1. ___________________________________________
2. ___________________________________________
3. ___________________________________________

**XP por ler:** 5 pontos

**Botão de Ação:** "Entendi!" / "Faz sentido!" / "Próximo"

---

### DROP 3: REFLEXÃO (Quiz sobre a história)
**Objetivo:** Verificar compreensão do conceito

**Pergunta Principal:**
```
[Pergunta sobre POR QUÊ o conceito funciona]
Exemplo: "Por que a técnica de Maria foi útil?"
```

**Opção A (Correta):**
- Texto: ___________________________________________
- Feedback: ___________________________________________
  (Exemplo: "Exatamente! 🎉 Números redondos são mais fáceis...")
- XP: 10 pontos

**Opção B (Incorreta):**
- Texto: ___________________________________________
- Feedback: ___________________________________________
  (Exemplo: "Não é bem isso! Tente pensar em... 💪")
- XP: 2 pontos

**Opção C (Incorreta):**
- Texto: ___________________________________________
- Feedback: ___________________________________________
- XP: 2 pontos

---

### DROP 4: AÇÃO (Desafio Prático)
**Objetivo:** Aplicar o conceito em problema similar

**Contexto do Desafio:**
```
[Apresente um problema prático similar]
Exemplo: "Agora é sua vez! João comprou..."
```

**Mensagens:**
1. "Agora é sua vez! 🚀"
2. ___________________________________________
3. ___________________________________________

**Pergunta:**
```
[Pergunta do desafio]
```

**Opção A (Correta):**
- Texto: ___________________________________________
- Feedback: ___________________________________________
  (Exemplo: "Perfeito! 🔥 Você está dominando!")
- XP: 15 pontos

**Opção B (Incorreta):**
- Texto: ___________________________________________
- Feedback: ___________________________________________
- XP: 3 pontos

**Opção C (Incorreta):**
- Texto: ___________________________________________
- Feedback: ___________________________________________
- XP: 3 pontos

---

### DROP 5: REFORÇO (Conclusão)
**Objetivo:** Celebrar conquista e reforçar aprendizado

**Mensagens:**
1. "Parabéns! Você completou o Drop! 🎊"
2. ___________________________________________
   (Exemplo: "Agora você sabe usar **arredondamento** no dia a dia!")
3. ___________________________________________
   (Exemplo: "Continue praticando e ficará automático! 🧠⚡")

**XP Bônus:** 20 pontos

**Botão de Ação:** "Próxima lição" / "Continuar"

---

## 🔄 Checklist de Qualidade

Antes de converter para JSON, verifique:

- [ ] Cada balão tem no máximo 280 caracteres
- [ ] Usei **negrito** para destacar conceitos-chave
- [ ] Inclui emojis para tornar mais visual (mas não exagerei)
- [ ] A história é relatable (algo do dia a dia do aluno)
- [ ] Feedbacks são encorajadores (mesmo quando erram)
- [ ] Progressão clara: Gancho → Conceito → Reflexão → Ação → Reforço
- [ ] Total da lição: 2-5 minutos de leitura
- [ ] XP distribuído: ~50 pontos totais por lição completa

---

## 📋 Conversão para JSON

Depois de preencher este template, use a seguinte estrutura JSON:

```json
{
  "id": "lesson-XX",
  "title": "[TÍTULO DA LIÇÃO]",
  "estimatedTime": "[X] minutos",
  "drops": [
    // DROP 1: GANCHO
    {
      "type": "gancho",
      "sender": "professor",
      "messages": [
        {"text": "[SUA MENSAGEM 1]", "delay": 0},
        {"text": "[SUA MENSAGEM 2]", "delay": 1000}
      ],
      "interaction": {
        "type": "continue",
        "button": "[SEU BOTÃO]"
      }
    },

    // DROP 2: CONCEITO
    {
      "type": "conceito",
      "sender": "professor",
      "messages": [
        {"text": "[MENSAGEM 1]", "delay": 0},
        {"text": "[MENSAGEM 2]", "delay": 1500},
        {"text": "[MENSAGEM 3]", "delay": 2000}
      ],
      "interaction": {
        "type": "continue",
        "button": "[SEU BOTÃO]"
      },
      "xp": 5
    },

    // DROP 3: REFLEXÃO
    {
      "type": "reflexao",
      "sender": "professor",
      "messages": [
        {"text": "[PERGUNTA]", "delay": 0}
      ],
      "interaction": {
        "type": "quiz",
        "question": "[PERGUNTA PRINCIPAL]",
        "options": [
          {
            "id": "a",
            "text": "[OPÇÃO A]",
            "correct": true,
            "feedback": "[FEEDBACK A]"
          },
          {
            "id": "b",
            "text": "[OPÇÃO B]",
            "correct": false,
            "feedback": "[FEEDBACK B]"
          },
          {
            "id": "c",
            "text": "[OPÇÃO C]",
            "correct": false,
            "feedback": "[FEEDBACK C]"
          }
        ],
        "xpCorrect": 10,
        "xpIncorrect": 2
      }
    },

    // DROP 4: AÇÃO (mesmo formato do DROP 3, mas com xpCorrect: 15)

    // DROP 5: REFORÇO
    {
      "type": "reforco",
      "sender": "professor",
      "messages": [
        {"text": "[MENSAGEM 1]", "delay": 0},
        {"text": "[MENSAGEM 2]", "delay": 1000},
        {"text": "[MENSAGEM 3]", "delay": 2000}
      ],
      "interaction": {
        "type": "complete",
        "button": "Próxima lição",
        "bonusXP": 20
      }
    }
  ]
}
```

---

## 💡 Dicas de Escrita

### ✅ BOM:
- "Maria estava no mercado e precisava calcular..."
- "Você já passou por isso? 🤔"
- "**Dica importante:** Use números redondos!"

### ❌ EVITE:
- Blocos de texto longos (mais de 280 caracteres)
- Linguagem acadêmica demais
- Explicações sem contexto prático
- Feedback negativo ou punitivo

### 🎯 Regra de Ouro:
**Se você não diria isso numa conversa com um amigo, não escreva aqui!**
