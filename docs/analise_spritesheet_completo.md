# Análise Completa do Spritesheet de Animações - KNOTFALL

## Visão Geral

Este documento analisa o spritesheet completo de animações do personagem KNOTFALL, contendo todas as animações essenciais para o gameplay. O spritesheet está organizado em categorias funcionais claramente rotuladas, facilitando a implementação no engine SFML.

---

## Categoria 1: Estados de Idle e Movimentação (Linha Superior)

### Tired (Cansado)
**Descrição:** Animação de idle quando o personagem está com pouca vida ou stamina. A postura é ligeiramente curvada para frente, com partículas de sombra mais fracas e dispersas. O cabelo/capa pende para baixo, sugerindo exaustão.

**Uso no Jogo:** Ativada quando a vida do jogador está abaixo de 30%, servindo como feedback visual do estado crítico sem necessidade de olhar constantemente para a barra de vida.

### Angry (Irritado)
**Descrição:** Postura mais agressiva e tensa, com o corpo ligeiramente inclinado para frente em posição de combate. Partículas de sombra mais intensas e agitadas. Transmite energia contida pronta para explodir.

**Uso no Jogo:** Pode ser usado durante sequências de combate intenso ou como transição para ataques especiais carregados.

### Idle (Parado)
**Descrição:** Postura neutra e relaxada, o estado padrão do personagem quando não está em ação. Partículas de sombra fluem suavemente ao redor. O cabelo/capa balança levemente com movimento de respiração.

**Uso no Jogo:** Animação loop principal quando o jogador não está pressionando nenhum botão. Deve ter ciclo de 2-3 segundos com respiração sutil.

### Turn (Virar) - Três Frames
**Descrição:** Sequência de três frames mostrando a transição completa do personagem virando de direção. Os frames capturam o movimento de rotação com a capa esvoaçando dinamicamente.

**Uso no Jogo:** Ativada quando o jogador muda rapidamente de direção horizontal. Os três frames criam uma transição suave e natural, evitando o "flip" instantâneo que quebraria a imersão.

---

## Categoria 2: Ataques Terrestres (Segunda Linha)

### Combo Attacks (Ataques em Combo)
**Frame 1 - Preparação:** Personagem recua ligeiramente, acumulando energia. Espada/lâmina começa a se formar.

**Frame 2 - Execução:** Ataque horizontal amplo com grande quantidade de partículas de sombra seguindo o rastro da lâmina. Movimento explosivo e dinâmico.

**Uso no Jogo:** Sistema de combo de 2-3 hits. Primeiro clique = preparação, segundo clique = execução. Timing entre os cliques afeta o dano e permite combos mais elaborados.

### Aeralse Attacks (Ataques Aéreos Ascendentes)
**Frame 1:** Personagem salta com foice/lâmina curva em movimento ascendente.

**Frame 2:** Continuação do movimento com grande rastro de sombra, criando um arco de ataque.

**Uso no Jogo:** Ataque anti-aéreo ou launcher que lança inimigos para cima. Útil para iniciar combos aéreos ou atingir inimigos voadores.

### Aerial Attacks (Ataques Aéreos)
**Descrição:** Duas poses de ataque executadas enquanto o personagem está no ar. Grande quantidade de partículas indicando movimento rápido e força.

**Uso no Jogo:** Ataques executáveis durante pulo ou dash aéreo. Podem ser encadeados com outros movimentos aéreos para combos complexos.

---

## Categoria 3: Defesa e Reação (Terceira Linha)

### Aerial Attacks (Continuação)
**Descrição:** Frame adicional de ataque aéreo com movimento descendente, criando um slam attack.

**Uso no Jogo:** Ataque aéreo para baixo que causa impacto ao atingir o chão, possivelmente com área de efeito.

### Block & Parry (Bloqueio e Aparar)
**Frame 1 - Block:** Personagem se contrai, formando uma barreira de sombra defensiva. Postura compacta e protegida.

**Frame 2 - Parry:** Explosão de partículas indicando deflexão bem-sucedida de ataque inimigo. Movimento mais expansivo que o block.

**Uso no Jogo:** 
- **Block:** Segurar botão de defesa reduz dano recebido
- **Parry:** Pressionar defesa no timing exato do ataque inimigo causa parry perfeito, abrindo oportunidade de contra-ataque e possivelmente ativando slowmotion

### Knockback & Stun (Recuo e Atordoamento)
**Descrição:** Personagem sendo lançado para trás com grande quantidade de partículas de impacto. Postura descontrolada indicando perda temporária de controle.

**Uso no Jogo:** Animação ativada quando o jogador recebe hit de ataque pesado de boss ou inimigo forte. Durante esta animação, o jogador perde controle temporariamente, criando consequência real para erros.

---

## Categoria 4: Estados Críticos (Quarta Linha)

### Block & Parry (Variação Defensiva)
**Descrição:** Versão alternativa ou continuação da animação de defesa, com o personagem completamente envolvido em sombra protetora.

**Uso no Jogo:** Pode representar um estado de defesa prolongada ou escudo de sombra ativado por habilidade especial.

### Knocked Down & Rising (Derrubado e Levantando)
**Frame 1 - Knocked Down:** Personagem caído no chão, completamente horizontal com grande quantidade de partículas de impacto.

**Frame 2 - Rising:** Processo de se levantar, corpo ainda baixo mas começando a se erguer com sombras se reorganizando.

**Frame 3 - Standing Up:** Quase de pé, retornando à postura de idle.

**Uso no Jogo:** Sequência ativada após receber dano massivo ou combo de inimigo. Durante os frames de "knocked down", o jogador é vulnerável. O timing de "rising" pode ter janela de invencibilidade (i-frames) para evitar combos infinitos.

---

## Categoria 5: Morte e Respawn (Linha Inferior)

### Death & Respawn (Morte e Renascimento)
**Sequência Completa (4 frames):**

**Frame 1 - Death Start:** Personagem começa a se dissolver, corpo perdendo coesão com partículas se dispersando violentamente.

**Frame 2 - Dissolution:** Corpo quase completamente desfeito em sombra pura, apenas os olhos glow ainda visíveis.

**Frame 3 - Respawn Start:** Sombras começam a se reagrupar, formando uma massa densa no ponto de respawn.

**Frame 4 - Reformation:** Personagem se reconstrói gradualmente, silhueta se tornando sólida novamente.

**Uso no Jogo:** 
- Frames 1-2 tocam no local da morte
- Tela escurece ou fade to black
- Jogador respawna no último Nó de Fios salvo
- Frames 3-4 tocam no local de respawn
- Transição suave de volta ao controle do jogador

**Narrativa:** A dissolução e reforma reforçam a natureza etérea de KNOTFALL como uma sombra viva, não um ser físico tradicional. A morte não é permanente porque ele é feito de sombra que pode se reconstituir.

---

## Análise Técnica para Implementação

### Dimensões e Padronização
Todos os sprites parecem ter dimensões consistentes, facilitando a implementação no engine. A altura visual do personagem é mantida constante em aproximadamente 128 pixels, permitindo hitboxes consistentes.

### Partículas e Efeitos
Cada animação incorpora partículas de sombra que devem ser implementadas como layer separada para otimização. As partículas seguem padrões específicos:
- **Idle/Walk:** Partículas sutis e lentas
- **Combat:** Partículas explosivas e direcionais
- **Defense:** Partículas formando barreiras
- **Death:** Partículas dispersando em todas as direções

### Sistema de Transições
O spritesheet foi projetado pensando em transições suaves entre estados:
- Idle → Turn → Walk
- Walk → Jump → Aerial Attack
- Any State → Block → Parry → Counter
- Any State → Hit → Knockback → Knocked Down → Rising → Idle

### Frames e Timing Recomendados

| Animação | Frames | FPS Sugerido | Duração Total | Loop |
|----------|--------|--------------|---------------|------|
| Idle | 6 | 6 | 1s | Sim |
| Turn | 3 | 12 | 0.25s | Não |
| Combo Attack | 2 | 15 | 0.13s | Não |
| Aerial Attack | 3 | 12 | 0.25s | Não |
| Block | 1 | - | Hold | Hold |
| Parry | 2 | 30 | 0.06s | Não |
| Knockback | 1 | - | 0.5s | Não |
| Knocked Down | 3 | 8 | 0.37s | Não |
| Death | 4 | 10 | 0.4s | Não |
| Respawn | 4 | 10 | 0.4s | Não |

### Hitboxes e Hurtboxes
Cada frame precisa de hitbox (área de ataque) e hurtbox (área vulnerável) definidas:
- **Idle/Walk:** Hurtbox compacta ao redor do corpo central
- **Attacks:** Hitbox estendida seguindo a trajetória da arma/sombra
- **Block:** Hurtbox reduzida, possivelmente com área de parry na frente
- **Knockback/Death:** Hurtbox desativada ou reduzida drasticamente

### Considerações de Gameplay
Este spritesheet suporta um sistema de combate profundo com:
- Combos terrestres e aéreos
- Sistema de defesa ativo (block/parry)
- Consequências reais para erros (knockback, knocked down)
- Feedback visual claro de estados (tired, angry)
- Morte e respawn cinematográficos

A variedade de animações permite criar um gameplay no estilo "soulsvania" com alta skill ceiling, onde dominar os timings de parry e encadear combos aéreos separa jogadores iniciantes de veteranos.
