# 🚀 Guia Rápido - ConversaLearn

## Como Testar em 2 Minutos

### 1️⃣ Iniciar Servidor Local

Escolha um método:

**Windows (com Python):**
```cmd
python -m http.server 8000
```

**macOS/Linux:**
```bash
python3 -m http.server 8000
```

**Node.js (qualquer sistema):**
```bash
npx http-server
```

### 2️⃣ Acessar no Navegador

Abra: **http://localhost:8000**

### 3️⃣ Experimentar a Demo

A demo já vem com uma lição completa sobre **Técnicas de Cálculo Mental**!

Você verá:
- ✅ Interface de chat com balões
- ✅ Professor virtual guiando
- ✅ Sistema de XP e streaks
- ✅ Perguntas interativas
- ✅ Feedback imediato
- ✅ Barra de progresso

---

## 🎮 Funcionalidades da Demo

### Gamificação Ativa:
1. **XP (Pontos)**: Cada ação ganha pontos
   - Ler conteúdo: +5 XP
   - Acertar quiz: +10-15 XP
   - Completar lição: +20 XP bônus

2. **Streaks (Ofensivas)**: Dias consecutivos estudando
   - 🔥 Aparece quando atinge 3+ dias

3. **Modo "Em Chamas"**:
   - 5 acertos seguidos = XP em dobro

4. **Barra de Progresso**:
   - Mostra % da lição completada

### Persistência:
- Seu progresso é salvo automaticamente
- Funciona offline após primeiro carregamento
- Pode usar como PWA (app nativo)

---

## 📝 Como Adicionar Seu Conteúdo

### Método 1: Editar o JSON Diretamente

1. Abra [content-structure.json](content-structure.json)
2. Copie a estrutura de uma lição existente
3. Modifique os textos
4. Recarregue a página

### Método 2: Usar o Template

1. Abra [content-template.md](content-template.md)
2. Preencha as lacunas com seu conteúdo
3. Converta para JSON seguindo o exemplo
4. Cole no `content-structure.json`

---

## 🎨 Personalizar Visual

### Mudar Cores

Edite em [styles.css](styles.css), linha 9-16:

```css
:root {
    --primary-color: #6366f1;    /* Roxo → Troque por outra cor */
    --success-color: #10b981;    /* Verde de sucesso */
    --error-color: #ef4444;      /* Vermelho de erro */
}
```

### Mudar Ícone do Professor

Em [styles.css](styles.css), linha ~146:

```css
.message.professor::before {
    content: '🤖'; /* Troque por: 👨‍🏫 👩‍🏫 🦉 etc */
}
```

---

## 📱 Testar no Celular

### Opção 1: Servidor Local na Rede

1. Descubra seu IP local:
   - Windows: `ipconfig` (procure "IPv4")
   - Mac/Linux: `ifconfig` (procure "inet")

2. No celular, acesse: `http://SEU_IP:8000`
   - Exemplo: `http://192.168.1.100:8000`

3. Adicione à tela inicial para virar PWA!

### Opção 2: Deploy Online (GitHub Pages)

1. Faça commit dos arquivos
2. Vá em Settings > Pages
3. Selecione branch main
4. Acesse `https://seuusuario.github.io/ft_edtechapp`

---

## 🔧 Resolver Problemas Comuns

### "Erro ao carregar conteúdo"
- ✅ Verifique se `content-structure.json` está na mesma pasta
- ✅ Veja o console do navegador (F12) para erros

### "Service Worker não registrado"
- ✅ Precisa estar em HTTPS ou localhost
- ✅ Navegador precisa suportar Service Workers

### "Progresso não salva"
- ✅ Verifique se localStorage está habilitado
- ✅ Modo anônimo pode bloquear

### "Página em branco"
- ✅ Abra o console (F12) e veja erros
- ✅ Confirme que todos os arquivos estão presentes

---

## 📊 Exemplo de Fluxo Completo

```
USUÁRIO ABRE O APP
    ↓
📱 Carrega interface de chat
    ↓
🤖 Professor envia gancho (pergunta instigante)
    ↓
👤 Usuário clica "Vamos lá!"
    ↓
🤖 Professor explica conceito (storytelling)
    ↓
❓ Aparece quiz de reflexão
    ↓
✅/❌ Usuário responde e recebe feedback
    ↓
⭐ Ganha XP (atualiza header)
    ↓
🎯 Desafio prático (aplicar conceito)
    ↓
✅ Acerta e ganha mais XP
    ↓
🎊 Mensagem de parabéns + XP bônus
    ↓
🔥 Atualiza streak se for dia novo
    ↓
💾 Salva tudo no localStorage
```

---

## 🎯 Próximos Passos Sugeridos

### Nível 1 (Básico):
1. ✏️ Editar textos da lição demo
2. 🎨 Mudar cores do tema
3. 🤖 Trocar emoji do professor

### Nível 2 (Intermediário):
1. ➕ Adicionar nova lição no JSON
2. 📚 Criar um curso completo (5-10 lições)
3. 🏆 Adicionar mais tipos de feedback

### Nível 3 (Avançado):
1. 🔔 Implementar notificações push
2. 📊 Sistema de badges/conquistas
3. 👥 Ranking e compartilhamento social
4. 🌙 Modo escuro

---

## 💡 Dicas para Criar Conteúdo Eficaz

### ✅ Faça:
- Use histórias do dia a dia
- Mantenha balões com max 280 caracteres
- Dê feedback encorajador (mesmo em erros)
- Use emojis com moderação
- Teste em celular (é o dispositivo principal)

### ❌ Evite:
- Blocos de texto longos
- Linguagem muito técnica
- Punições por erros (reduz motivação)
- Vídeos/imagens pesadas (quebra o low-data)

### 🎯 Regra de Ouro:
**"Se levou mais de 5 minutos, divida em 2 lições!"**

---

## 📞 Ajuda e Suporte

- 📖 Leia o [README.md](README.md) completo
- 📝 Use o [content-template.md](content-template.md)
- 🔍 Veja exemplos no [content-structure.json](content-structure.json)
- 🐛 Encontrou bug? Abra issue no GitHub

---

## 🎉 Boas Práticas

1. **Teste sempre no celular**: É onde a maioria usará
2. **Comece pequeno**: 3-5 lições por curso
3. **Itere rápido**: Publique, teste, melhore
4. **Ouça feedback**: Usuários reais são o melhor teste
5. **Mantenha simples**: A simplicidade é o diferencial

---

Bom desenvolvimento! 🚀💜
