# ✍️ Sistema de Criação de Conteúdo - ConversaLearn

## Visão Geral

Sistema que permite **qualquer pessoa** criar suas próprias lições conversacionais sem precisar editar JSON manualmente!

### 🎯 Características

- ✅ **Interface Visual** - Cola texto, vê JSON em tempo real
- ✅ **Limite de 1000 caracteres** - Mantém lições curtas (micro-learning)
- ✅ **Salvo no Cache** - Usa localStorage do navegador
- ✅ **Preview em Tempo Real** - Vê o JSON enquanto digita
- ✅ **Contador de Caracteres** - Sabe quanto falta
- ✅ **Exemplo Incluído** - Clica e carrega exemplo para editar
- ✅ **Teste Direto** - Botão que leva pro webapp com sua lição

## 📁 Arquivos Criados

### 1. [content-creator.html](content-creator.html)
Interface visual de criação de conteúdo com:
- Textarea para colar texto
- Preview JSON em tempo real
- Contador de caracteres (máx 1000)
- Botões: Limpar, Carregar Exemplo, Salvar, Testar
- Status do cache (mostra se tem conteúdo salvo)

### 2. Modificações em [index-neobrutalist.html](index-neobrutalist.html)
- Link "✍️ CRIAR" no menu
- Nova seção destacada "Crie Seu Próprio Conteúdo"
- Menu mobile atualizado

### 3. Modificações em [app.js](app.js)
- Verifica cache primeiro antes de carregar JSON padrão
- Função `clearCustomContent()` global
- Logs no console para debug

### 4. Modificações em [index.html](index.html)
- Indicador visual quando usa conteúdo customizado
- Botão para limpar cache

### 5. Modificações em [styles.css](styles.css)
- CSS para indicador de conteúdo customizado
- Estilo do botão de limpar

## 🚀 Como Usar

### Passo 1: Acessar o Creator

Clique em **"✍️ CRIAR"** na navigation bar ou acesse diretamente:
```
http://localhost:8000/content-creator.html
```

### Passo 2: Escrever o Conteúdo

Cole ou digite seu texto seguindo o formato:

```
LIÇÃO: Nome da Sua Lição
TEMPO: 3 minutos

[GANCHO]
Primeira mensagem chamativa
Segunda mensagem explicando mais
BOTÃO: Vamos lá!

[CONCEITO]
Explicação do conceito principal
Use **negrito** para destacar
Pode usar emojis! 💡
BOTÃO: Entendi!
XP: 5

[QUIZ]
PERGUNTA: Qual a resposta certa?
A) Opção correta | CORRETO | Parabéns! 🎉
B) Opção errada | ERRADO | Tente novamente! 💪
C) Opção errada | ERRADO | Quase! 💡
XP_CORRETO: 10
XP_ERRADO: 2

[REFORÇO]
Parabéns! Você completou! 🎊
Continue assim!
BOTÃO: Finalizar
XP_BONUS: 20
```

### Passo 3: Ver Preview

O JSON é gerado **automaticamente** enquanto você digita!

### Passo 4: Salvar

Clique em **"💾 SALVAR NO CACHE"**

Ou clique em **"🚀 TESTAR NO WEBAPP"** para salvar e abrir direto.

### Passo 5: Testar

Abra o webapp (`index.html`) e sua lição aparecerá!

## 📋 Formato do Texto

### Seções Disponíveis

#### **[GANCHO]** - Chamada inicial
```
[GANCHO]
Mensagem 1 que desperta curiosidade
Mensagem 2 com mais contexto
BOTÃO: Texto do botão
```

#### **[CONCEITO]** - Ensino principal
```
[CONCEITO]
Explicação clara e objetiva
Use **negrito** para destacar
Adicione emojis para engajar 💡
BOTÃO: Entendi!
XP: 5
```

#### **[QUIZ]** ou **[AÇÃO]** - Perguntas interativas
```
[QUIZ]
PERGUNTA: Sua pergunta aqui?
A) Primeira opção | CORRETO | Feedback positivo! 🎉
B) Segunda opção | ERRADO | Feedback construtivo 💪
C) Terceira opção | ERRADO | Dica para tentar novamente 💡
XP_CORRETO: 10
XP_ERRADO: 2
```

**Nota:** Use `[AÇÃO]` para desafios práticos (mesma estrutura).

#### **[REFORÇO]** - Conclusão
```
[REFORÇO]
Mensagem de parabéns! 🎊
Recapitulação do aprendizado
Motivação para continuar!
BOTÃO: Próxima lição
XP_BONUS: 20
```

### Parâmetros Opcionais

- **LIÇÃO:** Nome da lição (padrão: "Lição Personalizada")
- **TEMPO:** Duração estimada (padrão: "3 minutos")
- **XP:** Pontos por ler (padrão: 5)
- **XP_BONUS:** Pontos ao finalizar (padrão: 20)
- **XP_CORRETO:** Pontos ao acertar quiz (padrão: 10)
- **XP_ERRADO:** Pontos ao errar quiz (padrão: 2)

## 💾 Sistema de Cache

### Como Funciona

1. **Salvar:** `localStorage.setItem('conversalearn-custom-content', json)`
2. **Carregar:** WebApp verifica cache ANTES de carregar JSON padrão
3. **Limpar:** Remove do localStorage

### Estrutura Salva

```json
{
  "courses": [{
    "id": "custom-course",
    "title": "Meu Conteúdo Personalizado",
    "lessons": [{ /* sua lição */ }]
  }],
  "metadata": {
    "version": "1.0",
    "custom": true,
    "createdAt": "2025-12-02T..."
  }
}
```

### Verificar Cache Manualmente

No console do navegador (F12):
```javascript
// Ver conteúdo salvo
JSON.parse(localStorage.getItem('conversalearn-custom-content'))

// Limpar cache
localStorage.removeItem('conversalearn-custom-content')
```

## 🎨 Interface do Creator

### Seções da Página

1. **Header Info**
   - Explicação do que é
   - Limite de caracteres
   - Badge de "Salvo automaticamente"

2. **Área de Texto**
   - Textarea com placeholder exemplo
   - Contador de caracteres (fica vermelho perto do limite)
   - Botões: Limpar, Carregar Exemplo

3. **Preview JSON**
   - Background preto (terminal-style)
   - Texto verde (Matrix-style)
   - Atualiza em tempo real

4. **Ações**
   - Salvar no Cache
   - Testar no WebApp

5. **Status do Cache**
   - Mostra se tem conteúdo salvo
   - Data de criação
   - Tamanho em bytes
   - Botão para limpar

## 🔍 Indicador Visual no WebApp

Quando usa conteúdo customizado:

```
┌──────────────────────────────────────────┐
│ ConversaLearn    🔥 0  ⭐ 0             │
├──────────────────────────────────────────┤
│ ████████████████░░░░░░░ 60% completo     │
├──────────────────────────────────────────┤
│ 📝 Conteúdo Personalizado        [✕]    │ ← INDICADOR
└──────────────────────────────────────────┘
```

- **Fundo amarelo** (#fbbf24)
- **Botão [✕]** para limpar conteúdo customizado
- **Sticky** (aparece sempre no topo)

## ⚠️ Limitações

### Máximo de 1000 Caracteres

**Por quê?**
- Mantém lições curtas (micro-learning)
- Evita sobrecarga do localStorage
- Força criador a ser conciso

**Dica:** Se precisar de mais, crie múltiplas lições!

### Apenas 1 Lição por Vez

Atualmente, o sistema suporta apenas UMA lição customizada por vez.

**Solução futura:** Sistema de múltiplas lições salvas.

### Não Valida Sintaxe Estritamente

O parser é tolerante. Se algo der errado:
- Verifica console (F12)
- Compara com exemplo
- Tenta novamente

## 📊 Estatísticas do Sistema

### Tamanho Estimado

- **Texto (1000 chars):** ~1KB
- **JSON gerado:** ~3-5KB
- **Total no cache:** ~5KB

### Navegadores Suportados

- ✅ Chrome 80+
- ✅ Firefox 75+
- ✅ Safari 13+
- ✅ Edge 80+

## 🎓 Casos de Uso

### 1. **Pastor criando série de sermões**
```
LIÇÃO: O Amor de Deus - Parte 1
[GANCHO] Você sabe quanto Deus te ama?
[CONCEITO] João 3:16...
```

### 2. **Professor de escola dominical**
```
LIÇÃO: História de Davi e Golias
[GANCHO] Um garoto contra um gigante...
[QUIZ] Qual era a arma de Davi?
```

### 3. **Líder de célula**
```
LIÇÃO: Perdão na Prática
[GANCHO] Como perdoar quem te machucou?
[AÇÃO] Pense em alguém...
```

### 4. **Evangelista**
```
LIÇÃO: O Plano de Salvação
[GANCHO] Se você morresse hoje...
[CONCEITO] Todos pecaram...
```

## 🔧 Troubleshooting

### "Erro ao salvar"
- Verifique se tem espaço no localStorage (limite ~5-10MB)
- Limpe cache antigo
- Reduza tamanho do texto

### "JSON mal formado"
- Verifique sintaxe (compare com exemplo)
- Não use caracteres especiais estranhos
- Confira | (pipes) nos quizzes

### "Webapp não carrega conteúdo"
- Abra console (F12) e veja logs
- Confirme que salvou no cache
- Tente limpar e salvar novamente

### "Preview não atualiza"
- Recarregue a página
- Limpe cache do navegador (Ctrl+Shift+Delete)
- Tente outro navegador

## 🚀 Próximas Melhorias

- [ ] Suporte a múltiplas lições
- [ ] Import/Export de JSON
- [ ] Validação de sintaxe em tempo real
- [ ] Editor visual (arrastar e soltar)
- [ ] Biblioteca de templates
- [ ] Compartilhar lições (QR code)
- [ ] Estatísticas de uso

## 📞 Feedback

Encontrou bug ou tem sugestão?
- Teste no console (F12)
- Documente o erro
- Compartilhe conosco!

---

**"E o que de mim, entre muitas testemunhas, ouviste, confia-o a homens fiéis, que sejam idôneos para também ensinarem os outros."** - 2 Timóteo 2:2

✍️ Capacite outros a ensinar! 🙏
