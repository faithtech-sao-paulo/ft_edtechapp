::01: O Conceito Central: "Conversational Learning" (Aprendizado Conversacional)
Para evitar blocos densos de texto que cansam a vista e desmotivam, a metodologia deve simular uma conversa. O WebApp não deve parecer um livro digital, mas sim um chat interativo.

A Interface: Visual de aplicativo de mensagens (balões de texto).

O "Professor": Um bot ou personagem guia que "envia" o conteúdo em pílulas.

A Interação: O usuário não apenas lê; ele precisa "responder" para a conversa avançar (clicando em opções pré-definidas).

::02: Estrutura do Micro-Learning (A Regra dos 3 Minutos)
Para adultos ocupados, cada sessão deve durar entre 2 a 5 minutos. Dividiremos o conteúdo em "Drops de Conhecimento".

Estrutura de um Drop (Unidade de Aula):

O Gancho (10 seg): Uma pergunta instigante ou uma situação problema enviada pelo "bot".

Ex: "Você sabia que [fato curioso]? Vamos descobrir por quê?"

O Conceito (30-60 seg): Explicação curta em texto (máximo de 280 caracteres por balão). Uso de negrito e emojis para quebrar a monotonia.

A Verificação Rápida (Interação): O usuário deve responder a uma pergunta de múltipla escolha ou "Verdadeiro/Falso" para desbloquear o próximo balão de texto.

O Reforço (Feedback Imediato): Se acertar, ganha pontos e elogio. Se errar, recebe uma explicação corretiva imediata (sem punição severa).

::03: Gamificação Estratégica (O "Estilo Duolingo")
Para manter a consistência sem usar gráficos pesados, focaremos em gatilhos psicológicos e números.

Barra de Progresso Visível: Mostre o quanto falta para acabar a lição atual. Isso reduz a ansiedade.

Ofensiva (Streaks): O contador de dias seguidos estudando. É o maior motivador de consistência. Perder a ofensiva dói mais do que perder pontos.

XP (Pontos de Experiência): Cada balão lido = 1 XP. Cada exercício certo = 10 XP.

Vidas/Energia (Opcional): Para adultos, o sistema de "perder vidas" pode ser frustrante. Sugiro focar em Recompensas (ex: acertar 5 seguidas ativa o modo "Em Chamas" com pontos em dobro).

::04: Metodologia de Ensino: O Ciclo E.R.A.
Para que o texto ensine de verdade, use o ciclo Exposição, Reflexão, Ação:

Exposição (Storytelling): Não jogue a teoria direto. Comece com uma história curta.

Ex: "Maria precisava calcular o troco, mas estava sem calculadora. Ela usou a técnica do arredondamento."

Reflexão (Quiz): Pergunte sobre a história.

Ex: "Por que a técnica de Maria foi útil?"

Ação (Desafio): Peça para o usuário resolver um problema similar.

Ex: "Agora é sua vez: João comprou um pão de R$ 3,80..."

::05: Adaptação Tecnológica (Low-Tech & Low-Data)
Para atender usuários com baixa estrutura:

PWA (Progressive Web App): O site se comporta como app, mas não exige download pesado na loja de aplicativos.

Modo Offline (Cache First): O app baixa os textos da semana inteira na primeira conexão (são apenas KBs de texto). O usuário pode fazer as lições no ônibus sem gastar 4G, e o app sincroniza o progresso quando recuperar o Wi-Fi.

Zero Mídia Pesada: Evite vídeos e imagens de alta resolução. Use ícones SVG (vetoriais) e CSS para dar cor. O foco é a tipografia.