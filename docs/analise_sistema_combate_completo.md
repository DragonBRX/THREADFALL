# Análise Completa: Sistema de Combate - Spritesheet Categorizado

## Visão Geral

Este spritesheet apresenta um sistema de combate abrangente organizado em cinco categorias distintas: **Quick Attack**, **Heavy Attack**, **Special**, **Power Up & Damage**, e uma quinta categoria parcialmente visível. Cada categoria contém múltiplos frames de animação que formam a base do sistema de combate do jogo.

---

## Categoria 1: Quick Attack (Ataque Rápido)

### Composição
Linha superior contendo 4 frames de animação, seguida por uma segunda linha com 3 frames adicionais, totalizando **7 frames** para a sequência completa de ataque rápido.

### Análise Frame por Frame

**Frame 1 - Preparação Inicial:**
Personagem em postura neutra com espada/lâmina começando a se formar no braço esquerdo. Partículas mínimas, corpo ainda relaxado. Este é o frame de transição do idle para o ataque.

**Frame 2 - Acúmulo de Momentum:**
Corpo recua ligeiramente, espada totalmente formada e puxada para trás. Partículas de sombra começam a se acumular ao redor da arma. Preparação para o golpe.

**Frame 3 - Início do Swing:**
Movimento explosivo iniciado, espada começando a cortar o ar horizontalmente. Rastro de sombra visível seguindo a trajetória. Corpo em rotação.

**Frame 4 - Pico do Ataque:**
Máxima extensão do ataque, espada completamente estendida com grande rastro de partículas. Este é o frame onde o hitbox tem maior alcance e dano.

**Frame 5 (Segunda Linha, Esquerda) - Dash Attack:**
Personagem em movimento horizontal rápido com grande quantidade de fumaça atrás, indicando velocidade extrema. Espada estendida para frente. Representa um ataque de investida ou dash attack.

**Frame 6 (Segunda Linha, Centro) - Follow-Through:**
Continuação do movimento após o dash, corpo ainda em momentum mas começando a desacelerar. Espada mantida em posição ofensiva.

**Frame 7 (Segunda Linha, Direita) - Recovery:**
Personagem desacelerando completamente, grande quantidade de partículas indicando fricção e parada. Preparação para retornar ao idle ou encadear próximo ataque.

### Características de Gameplay

**Velocidade:** Muito rápida, toda sequência deve durar aproximadamente 0.4-0.6 segundos
**Dano:** Baixo a moderado (30-50 por hit)
**Alcance:** Médio, focado em frente ao personagem
**Recovery:** Curto, permite combos rápidos
**Uso:** Ataque básico spam-able, building de combos, DPS consistente

---

## Categoria 2: Heavy Attack (Ataque Pesado)

### Composição
Três frames mostrando uma sequência de ataque com arma pesada (possivelmente espada grande ou foice).

### Análise Frame por Frame

**Frame 1 - Charge Inicial:**
Personagem em postura baixa e compacta, acumulando energia. Grande quantidade de partículas de sombra sendo sugadas para o corpo. Arma começando a se materializar de forma massiva.

**Frame 2 - Expansão Explosiva:**
Corpo se expande dramaticamente com arma totalmente formada em grande escala. Partículas explodem em todas as direções. Momento de máximo poder acumulado antes da liberação.

**Frame 3 - Execução Devastadora:**
Ataque liberado com força total, personagem em postura agressiva com arma estendida. Explosão massiva de partículas indicando impacto tremendo. Possível shockwave ou área de efeito.

### Características de Gameplay

**Velocidade:** Lenta, sequência completa de 1.2-1.8 segundos
**Dano:** Muito alto (150-250 por hit)
**Alcance:** Grande, área de efeito considerável
**Recovery:** Longo, jogador fica vulnerável após o ataque
**Uso:** Punição de aberturas, quebra de guarda, dano burst
**Mecânica Especial:** Pode requerer charging (segurar botão) para maximizar dano

---

## Categoria 3: Special (Ataques Especiais)

### Composição
Três frames mostrando uma habilidade especial envolvendo asas de sombra.

### Análise Frame por Frame

**Frame 1 - Invocação das Asas:**
Asas massivas de sombra se materializam nas costas do personagem. Postura imponente e central. Grande quantidade de partículas envolvendo todo o corpo. Momento de transformação.

**Frame 2 - Asas Completamente Manifestadas:**
Asas em máxima extensão, criando uma silhueta dramática e intimidadora. Partículas estabilizadas em padrão simétrico. Personagem em postura de poder.

**Frame 3 - Explosão de Energia:**
Personagem completamente envolvido em fumaça e partículas explosivas. As asas podem estar batendo ou liberando energia. Efeito de área massivo.

### Características de Gameplay

**Tipo:** Habilidade especial com custo de recurso (mana/energia/fragmentos)
**Efeito Possível 1:** Ataque de área massivo que atinge todos os inimigos ao redor
**Efeito Possível 2:** Buff temporário que aumenta stats e adiciona asas à movimentação
**Efeito Possível 3:** Transformação temporária para um estado mais poderoso
**Cooldown:** Longo, habilidade ultimate ou semi-ultimate
**Uso:** Situações críticas, múltiplos inimigos, bosses

---

## Categoria 4: Power Up & Damage (Buff e Dano Recebido)

### Composição
Oito frames divididos em duas linhas, mostrando estados de buff/power-up e reações a dano.

### Linha Superior - Power Up (4 frames)

**Frames 1-4: Sequência de Buff/Transformação:**
Personagem progressivamente sendo envolvido por partículas de sombra cada vez mais densas. Cada frame mostra aumento na intensidade do efeito visual, sugerindo acúmulo de poder ou ativação de habilidade especial.

**Frame 1:** Início da ativação, partículas começando a surgir
**Frame 2:** Intensificação, corpo começando a ser obscurecido
**Frame 3:** Pico do efeito, personagem quase totalmente envolvido
**Frame 4:** Estabilização, novo estado de poder ativo

**Uso no Jogo:**
- Animação de ativação de buffs temporários
- Coleta de power-ups ou fragmentos importantes
- Transição para estados especiais (como o estado "Eu Sou a Morte")
- Cura ou regeneração em Nós de Fios

### Linha Inferior - Damage Reactions (4 frames)

**Frames 1-4: Reações a Dano:**
Sequência mostrando o personagem recebendo hits e reagindo com diferentes intensidades.

**Frame 1:** Hit leve, pequeno recuo com poucas partículas
**Frame 2:** Hit moderado, recuo mais pronunciado
**Frame 3:** Hit pesado, corpo claramente impactado
**Frame 4:** Hit crítico ou combo, grande quantidade de partículas de impacto

**Uso no Jogo:**
- Feedback visual quando o jogador recebe dano
- Diferentes animações baseadas na força do ataque inimigo
- Pode incluir invencibility frames (i-frames) curtos após hit para evitar stunlock
- Transição para knockback se o dano for suficientemente alto

---

## Categoria 5: [Parcialmente Visível]

A quinta categoria está parcialmente visível na parte inferior da imagem, mostrando pelo menos 4 frames adicionais. Sem ver os rótulos ou frames completos, é difícil determinar a função exata, mas as poses sugerem possíveis estados de:
- Movimentação especial (dash, dodge)
- Mais variações de ataques
- Estados de status (stun, poison, etc.)
- Animações de vitória ou derrota

---

## Sistema de Combate Integrado

### Fluxo de Combate Básico

```
IDLE → QUICK ATTACK (spam) → HEAVY ATTACK (finisher) → RECOVERY → IDLE
                ↓
         SPECIAL (situacional)
                ↓
         POWER UP (buff) → Enhanced Attacks
```

### Combos Sugeridos

**Combo Rápido:**
Quick Attack (frames 1-4) → Quick Attack (frames 1-4) → Quick Attack (frames 1-4)
- 3 hits rápidos, dano total: 90-150
- Tempo total: ~1.2s
- Uso: DPS consistente, inimigos pequenos

**Combo Pesado:**
Quick Attack (frames 1-4) → Heavy Attack (charge) → Heavy Attack (release)
- Setup rápido seguido de finisher devastador
- Dano total: 200-300
- Tempo total: ~2s
- Uso: Punição após parry, inimigos grandes

**Combo Dash:**
Quick Attack (dash, frames 5-7) → Quick Attack (frames 1-4) → Special
- Aproximação rápida, hits de setup, ultimate
- Dano total: 300-400+
- Tempo total: ~2.5s
- Uso: Iniciar combate, bosses

**Combo Aéreo:**
Jump → Quick Attack (frames 1-4) → Heavy Attack (slam down) → Special (landing)
- Combate vertical completo
- Dano total: 250-350
- Uso: Inimigos voadores, variação de gameplay

---

## Implementação Técnica

### Tabela de Propriedades dos Ataques

| Ataque | Startup | Active | Recovery | Total | Dano | Knockback |
|--------|---------|--------|----------|-------|------|-----------|
| Quick Attack | 3f | 5f | 4f | 12f (0.4s) | 40 | Baixo |
| Quick Dash | 2f | 8f | 6f | 16f (0.53s) | 50 | Médio |
| Heavy Attack | 15f | 10f | 20f | 45f (1.5s) | 200 | Alto |
| Special | 20f | 15f | 25f | 60f (2s) | 300 | Muito Alto |

*Assumindo 30 FPS para cálculos*

### Sistema de Recursos

**Stamina/Energia:**
- Quick Attacks: 10 stamina cada
- Heavy Attack: 30 stamina
- Special: 50 stamina ou recurso especial separado
- Regeneração: 20 stamina/segundo quando não atacando

**Fragmentos de Sombra (Recurso Especial):**
- Coletados de inimigos e bosses
- Necessários para ativar Specials
- Máximo: 100 fragmentos
- Special custa: 50 fragmentos

### Cancelamento de Animações

**Quick Attack:**
- Pode ser cancelado para dodge após frame 8
- Pode ser cancelado para Heavy Attack após frame 10
- Pode ser cancelado para outro Quick Attack após frame 12

**Heavy Attack:**
- Não pode ser cancelado após frame 10 (commitment)
- Pode ser cancelado para dodge durante charge (frames 1-10)

**Special:**
- Não pode ser cancelado após ativação
- Full commitment, requer posicionamento cuidadoso

---

## Balanceamento e Design

### Filosofia de Combate

O sistema apresentado sugere um combate que equilibra:
- **Velocidade vs Poder:** Quick attacks rápidos mas fracos vs Heavy attacks lentos mas devastadores
- **Risco vs Recompensa:** Ataques mais poderosos têm recovery maior, criando janelas de vulnerabilidade
- **Recursos:** Specials limitados por recursos, forçando uso estratégico
- **Skill Expression:** Combos e cancelamentos permitem jogadores habilidosos maximizar DPS

### Curva de Aprendizado

**Iniciante:**
- Spam de Quick Attacks
- Heavy Attacks ocasionais quando inimigo está longe
- Specials usados aleatoriamente

**Intermediário:**
- Combos básicos (Quick → Quick → Heavy)
- Uso de dash attacks para mobilidade
- Specials guardados para situações críticas

**Avançado:**
- Combos complexos com cancelamentos
- Animation canceling para maximizar DPS
- Uso perfeito de i-frames em damage reactions
- Specials usados estrategicamente para quebrar padrões de boss

**Mestre:**
- Combos infinitos ou quase-infinitos
- Parry perfeitos seguidos de punições máximas
- Gerenciamento perfeito de recursos
- No-hit runs possíveis através de domínio completo do sistema

---

## Integração com Outros Sistemas

### Morphs de Sombra
Os ataques mostrados aqui representam provavelmente apenas um "set" de morphs. O jogo menciona 100+ variações de morphs, então estes sprites podem ser:
- Set básico de espada/claws
- Outros sets (asas, tendrils, foice) teriam sprites similares mas com formas diferentes
- Sistema modular permite misturar elementos de diferentes morphs

### Progressão
- Início do jogo: Apenas Quick Attacks disponíveis
- Mid-game: Heavy Attacks desbloqueados após primeiro boss
- Late-game: Specials desbloqueados após múltiplos bosses
- End-game: Todas as variações e combos avançados disponíveis

### Dificuldade
O sistema permite ajustar dificuldade através de:
- Dano recebido (mais ou menos frames de damage reaction)
- Stamina regeneration rate
- Custo de stamina dos ataques
- Janelas de cancelamento (mais generosas ou mais restritas)
