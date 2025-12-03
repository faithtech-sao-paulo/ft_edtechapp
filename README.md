# ConversaLearn - Aprendizado Conversacional

WebApp educacional baseado em micro-learning com interface de chat interativo, inspirado no Duolingo e metodologias de aprendizado conversacional.

## 🎯 Funcionalidades Principais

### 1. **Interface de Chat Interativo**
- Experiência de aprendizado em formato de conversa
- Balões de mensagem estilo WhatsApp
- Professor virtual (bot) que guia o aprendizado
- Animações suaves e feedback visual

### 2. **Gamificação Completa**
- **XP (Pontos de Experiência)**: Ganhe pontos por cada ação
- **Streaks (Ofensivas)**: Contador de dias consecutivos estudando
- **Modo "Em Chamas"**: XP em dobro após 5 acertos seguidos
- **Barra de Progresso**: Visualização clara do avanço na lição
- **Feedback Imediato**: Respostas instantâneas para cada interação

### 3. **Micro-Learning (Regra dos 3 Minutos)**
- Lições divididas em "Drops" de 2-5 minutos
- Conteúdo em pílulas de até 280 caracteres
- Verificações rápidas entre conceitos
- Estrutura E.R.A. (Exposição, Reflexão, Ação)

### 4. **PWA com Modo Offline**
- Funciona como aplicativo nativo
- Cache First: conteúdo disponível offline
- Sincronização automática quando online
- Consumo mínimo de dados (apenas texto e SVG)

## 📁 Estrutura de Arquivos

```
ft_edtechapp/
├── index.html              # Interface principal
├── styles.css              # Estilos (zero imagens pesadas)
├── app.js                  # Lógica da aplicação
├── content-structure.json  # Conteúdo educacional
├── manifest.json           # Configuração PWA
├── sw.js                   # Service Worker (offline)
└── README.md              # Documentação
```

## 🚀 Como Usar

### 1. Servidor Local

Para testar localmente, use qualquer servidor HTTP simples:

```bash
# Python 3
python -m http.server 8000

# Node.js (http-server)
npx http-server

# PHP
php -S localhost:8000
```

Acesse: `http://localhost:8000`

### 2. Criar Conteúdo Educacional

Edite o arquivo [content-structure.json](content-structure.json) seguindo a estrutura:

```json
{
  "courses": [
    {
      "id": "seu-curso",
      "title": "Nome do Curso",
      "lessons": [
        {
          "id": "lesson-01",
          "title": "Nome da Lição",
          "drops": [
            {
              "type": "gancho",
              "sender": "professor",
              "messages": [
                {
                  "text": "Pergunta instigante ou gancho",
                  "delay": 0
                }
              ],
              "interaction": {
                "type": "continue",
                "button": "Vamos lá!"
              }
            }
          ]
        }
      ]
    }
  ]
}
```

## 📚 Tipos de Drops (Unidades de Ensino)

### 1. **Gancho** (10 segundos)
```json
{
  "type": "gancho",
  "sender": "professor",
  "messages": [
    {
      "text": "Você sabia que [fato curioso]?",
      "delay": 0
    }
  ],
  "interaction": {
    "type": "continue",
    "button": "Vamos lá!"
  }
}
```

### 2. **Conceito** (30-60 segundos)
```json
{
  "type": "conceito",
  "sender": "professor",
  "messages": [
    {
      "text": "Explicação curta com **negrito** e emojis 💡",
      "delay": 0
    }
  ],
  "interaction": {
    "type": "continue",
    "button": "Entendi!"
  },
  "xp": 5
}
```

### 3. **Reflexão** (Quiz)
```json
{
  "type": "reflexao",
  "sender": "professor",
  "messages": [
    {
      "text": "Pergunta reflexiva sobre o conceito",
      "delay": 0
    }
  ],
  "interaction": {
    "type": "quiz",
    "question": "Qual a resposta correta?",
    "options": [
      {
        "id": "a",
        "text": "Opção correta",
        "correct": true,
        "feedback": "Exatamente! 🎉"
      },
      {
        "id": "b",
        "text": "Opção incorreta",
        "correct": false,
        "feedback": "Não é isso! Tente novamente 💪"
      }
    ],
    "xpCorrect": 10,
    "xpIncorrect": 2
  }
}
```

### 4. **Ação** (Desafio Prático)
Mesmo formato do tipo "reflexao", mas com problema prático para resolver.

### 5. **Reforço** (Conclusão)
```json
{
  "type": "reforco",
  "sender": "professor",
  "messages": [
    {
      "text": "Parabéns! Você completou! 🎊",
      "delay": 0
    }
  ],
  "interaction": {
    "type": "complete",
    "button": "Próxima lição",
    "bonusXP": 20
  }
}
```

## 🎨 Personalização

### Cores (em `styles.css`)
```css
:root {
    --primary-color: #6366f1;      /* Cor principal */
    --secondary-color: #8b5cf6;    /* Cor secundária */
    --success-color: #10b981;      /* Cor de sucesso */
    --error-color: #ef4444;        /* Cor de erro */
}
```

### Ícone do Professor
No arquivo `styles.css`, linha com `.message.professor::before`, altere o emoji:
```css
content: '🤖'; /* Substitua por qualquer emoji */
```

## 💾 Sistema de Progresso

O progresso é salvo automaticamente no **localStorage** do navegador:
- XP acumulado
- Dias de ofensiva (streak)
- Última data de estudo

### Resetar Progresso
No console do navegador:
```javascript
localStorage.clear();
location.reload();
```

## 📱 Instalação como App

1. Abra o webapp no navegador mobile (Chrome/Safari)
2. Clique em "Adicionar à tela inicial"
3. O app funcionará offline automaticamente

## 🔧 Tecnologias Utilizadas

- **HTML5** - Estrutura semântica
- **CSS3** - Estilos responsivos (zero imagens)
- **Vanilla JavaScript** - Lógica pura (sem frameworks)
- **PWA** - Progressive Web App
- **Service Worker** - Cache offline
- **LocalStorage** - Persistência de dados

## 📊 Metodologia Pedagógica

Baseado nas instruções do arquivo `insctructions.md`:

1. **Conversational Learning**: Simula uma conversa natural
2. **Micro-Learning**: Sessões de 2-5 minutos
3. **Gamificação Estratégica**: Motivação sem frustração
4. **Ciclo E.R.A.**: Exposição → Reflexão → Ação
5. **Low-Tech**: Funciona em conexões lentas

## 🎯 Próximos Passos

- [ ] Adicionar mais cursos e lições
- [ ] Sistema de níveis e badges
- [ ] Desafios diários
- [ ] Ranking entre usuários (opcional)
- [ ] Notificações push para lembrar de estudar
- [ ] Modo escuro

## 📄 Licença

Projeto educacional open-source. Use e adapte livremente!
