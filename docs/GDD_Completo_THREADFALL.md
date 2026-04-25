# Game Design Document (GDD) Consolidado: THREADFALL

## 1. Visão Geral do Projeto

**Título:** THREADFALL
**Gênero:** Metroidvania Hardcore 2D
**Plataforma:** PC (C++ / SFML)
**Conceito Central:** Um jogo de plataforma de combate focado em *skill* e *morphs* de sombra, ambientado em um mundo pós-apocalíptico onde a realidade foi desfeita. O protagonista, KNOTFALL, uma sombra viva, busca recuperar suas memórias e decidir o destino final da existência.

## 2. Narrativa e Lore (Expandida)

### 2.1. A Cosmologia dos Fios

A realidade, **Aethel**, era uma tapeçaria tecida por **Fios** de energia conceitual. Os **Tecedores** eram os guardiões dessa tapeçaria, seres de luz e sombra que mantinham a harmonia. Os **Nós Primordiais** ancoravam conceitos fundamentais. O Panteão dos Deuses observava de longe, indiferente.

### 2.2. O Threadfall

O colapso (Threadfall) foi causado pela apatia dos Deuses, permitindo que a entropia desmantelasse os Fios. Em um ato final, os Tecedores tentaram um ritual de sacrifício que falhou, transformando-os em **Nós Falhos** (os Bosses) e desfazendo o mundo. KNOTFALL é uma **Lágrima de Sombra**, a personificação da dor coletiva, despertada para decidir o destino da realidade.

### 2.3. Progressão Narrativa

A história é contada através de monólogos internos, descrições de itens e **Fragmentos de Memória** obtidos ao derrotar os Nós Falhos. Cada fragmento revela a verdade sobre o passado de KNOTFALL e a causa do colapso. A jornada culmina no Panteão, onde o jogador faz a escolha final entre os três desfechos:

| Final | Escolha | Desfecho |
| :--- | :--- | :--- |
| **1. Vazio** | Aceitar a solidão | KNOTFALL se dissolve na chuva de Fios, a ilusão humana persiste vazia. |
| **2. Deuses** | Conquistar o poder | KNOTFALL assume o estado "Eu Sou a Morte" e destrói o Panteão, tornando-se o novo deus do caos. |
| **3. Sacrifício** | Reconectar a vida | KNOTFALL se sacrifica para refazer a tapeçaria, restaurando a vida (Final Canônico). |

## 3. Design de Personagem: KNOTFALL

KNOTFALL é uma silhueta negra pura com olhos *glow* brancos intensos. Sua natureza é fluida, permitindo **Morphs** (transformações corporais) que servem como habilidades de combate e exploração.

### 3.1. Morphs Principais (Desbloqueados por Bosses)

| Morph | Boss que Dropa | Função Primária |
| :--- | :--- | :--- |
| **Garras/Espada** | Guardião do Portão | Combate *melee* rápido e combos. |
| **Chicotes/Foice** | Tecelã Submersa | Ataque de longo alcance e controle de área. |
| **Asas Etéreas** | Coro do Sacrifício | Mobilidade aérea, *dash* e *wall-ride*. |
| **Escudo/Defesa** | Guardião Axiomático | *Block* e *Parry* com *i-frames* (janelas de invencibilidade). |

### 3.2. Feedback de Dano (Sprite Aprovada)

O feedback visual de dano deve ser sutil para manter a silhueta. Ao receber dano, o corpo de sombra de KNOTFALL deve **recolher-se ligeiramente**, com **pequenas partículas de sombra se desprendendo** do ponto de impacto. Os olhos *glow* brancos devem **piscar ou tremer** momentaneamente. Isso garante que o jogador receba feedback sem quebrar a consistência visual do personagem.

## 4. Design de Inimigos e Bosses (Assets Aprovados)

Os inimigos são manifestações corrompidas dos Fios e dos Tecedores. O estilo visual é de silhuetas negras complexas com múltiplos olhos *glow* brancos.

### 4.1. Bosses (Nós Falhos)

| Boss | Drop de Morph | Descrição e Comportamento Sugerido | Asset |
| :--- | :--- | :--- | :--- |
| **Guardião do Portão** | Garras/Espada | Massa de fios e ferramentas quebradas. Ataca com *slams* pesados e projéteis de sombra. Requer *parry* para abrir janelas de dano. | `boss_1_gatekeeper.png` |
| **Tecelã Submersa** | Chicotes/Foice | Entidade fluida e tentacular. Ataca com *sweeps* de longo alcance e *grapples*. O combate ocorre em plataformas instáveis. | `boss_2_submerged_weaver.png` |
| **Coro do Sacrifício** | Asas Etéreas | Amálgama de silhuetas humanoides. Ataca com ondas de choque sônicas e múltiplos braços. Requer uso de *dash* aéreo para evitar ataques de área. | `boss_3_choir_of_sacrifice.png` |

### 4.2. Inimigos Comuns (Nós Menores)

| Inimigo | Comportamento Sugerido | Asset |
| :--- | :--- | :--- |
| **Shadow Crawler** | Inimigo terrestre rápido e agressivo. Ataca com investidas e saltos. Deve ser abatido rapidamente devido à sua alta velocidade. | `enemy_shadow_crawler_v2.png` |
| **Thread Floater** | Inimigo aéreo que flutua lentamente. Ataca com projéteis de fios lentos. Deve ser priorizado para limpar o espaço aéreo. | `enemy_thread_floater.png` |

## 5. Guia de Implementação Técnica: Cenários Parallax

O cenário é composto por múltiplas camadas de imagens estáticas que se movem em velocidades diferentes (Parallax Scrolling) para criar a ilusão de profundidade e animação.

### 5.1. Estrutura de Camadas Aprovadas

O cenário de **Ruínas da Cidade Silenciosa** será montado com 3 camadas principais:

| Camada | Arquivo | Velocidade de Movimento (Exemplo) | Interatividade |
| :--- | :--- | :--- | :--- |
| **Layer 1 (Fundo Distante)** | `layer_1_fundo_distante.png` | 10% da velocidade do jogador | Não Interativo |
| **Layer 2 (Midground)** | `layer_midground_ruins.png` | 50% da velocidade do jogador | Não Interativo |
| **Layer 3 (Foreground/Plataformas)** | `layer_foreground_platforms.png` | 100% da velocidade do jogador | **Totalmente Interativo** |

### 5.2. Implementação no SFML (C++)

Para implementar o efeito Parallax, você deve usar a classe `sf::Sprite` para cada camada e ajustar sua posição no *Game Loop* com base na posição da câmera e na velocidade de movimento definida para a camada.

**Exemplo de Cálculo de Posição (Simplificado):**

```cpp
// Defina a velocidade de cada camada (LayerSpeed)
float layer1Speed = 0.1f; // 10%
float layer2Speed = 0.5f; // 50%
float layer3Speed = 1.0f; // 100%

// Posição da Câmera (View)
sf::Vector2f cameraPos = view.getCenter();

// Cálculo da Posição para a Camada 1 (Fundo Distante)
// O fundo se move menos que a câmera, criando profundidade
float layer1X = cameraPos.x * layer1Speed;
layer1Sprite.setPosition(layer1X, layer1Sprite.getPosition().y);

// O mesmo cálculo deve ser aplicado para a Camada 2 (Midground)
float layer2X = cameraPos.x * layer2Speed;
layer2Sprite.setPosition(layer2X, layer2Sprite.getPosition().y);

// A Camada 3 (Foreground) se move na mesma velocidade da câmera (100%)
// e contém as colisões e objetos interativos.
```

### 5.3. Interatividade da Camada 3

Conforme solicitado, a **Camada 3** (Foreground) deve ser totalmente interativa. Isso significa que todos os elementos visíveis nela devem ter:

1.  **Hitboxes de Colisão:** Para o movimento do KNOTFALL.
2.  **Objetos Destrutíveis:** Fios, pilares quebrados e destroços devem ter um componente de vida. KNOTFALL pode usar ataques de foice ou *morphs* de espada para destruí-los, revelando caminhos ou itens.
3.  **Fios Quebráveis:** Os fios que ligam as plataformas devem ser *rigidbodies* que podem ser puxados ou cortados pelo KNOTFALL, ativando *chain reactions* (efeitos em cadeia) no cenário.

## 6. Estrutura do Arquivo ZIP (Final)

O arquivo ZIP final (`THREADFALL_Assets_Expandidos.zip`) terá a seguinte estrutura de pastas, combinando seus arquivos originais com os novos assets aprovados:

```
/THREADFALL_Projeto_Expandido/
├── /assets/
│   ├── /cenarios/
│   │   └── /parallax_layers/
│   │       ├── layer_1_fundo_distante.png
│   │       ├── layer_midground_ruins.png
│   │       └── layer_foreground_platforms.png
│   ├── /sprites/
│   │   ├── /knotfall/
│   │   │   ├── [Seus sprites originais de KNOTFALL]
│   │   │   └── [Seus spritesheets de animação originais]
│   │   ├── /bosses/
│   │   │   ├── boss_1_gatekeeper.png
│   │   │   ├── boss_2_submerged_weaver.png
│   │   │   └── boss_3_choir_of_sacrifice.png
│   │   └── /inimigos/
│   │       ├── enemy_shadow_crawler_v2.png
│   │       └── enemy_thread_floater.png
│   └── /ui/
│       └── Item_Spool_Core.png
├── /docs/
│   ├── GDD_Completo_THREADFALL.md  <-- Este documento
│   ├── KNOTFALL.txt                <-- Seu arquivo original
│   ├── o final dos deuses...txt     <-- Seu arquivo original
│   └── [Outros arquivos de texto originais]
└── README.md
```

## 7. Próximos Passos

Este GDD e os assets fornecem uma base sólida para iniciar o desenvolvimento no VS Code. O próximo passo lógico seria:

1.  Configurar o ambiente C++/SFML no VS Code.
2.  Implementar o sistema de câmera e o Parallax Scrolling (usando o guia acima).
3.  Implementar o KNOTFALL com as animações básicas e o sistema de Morphs.
4.  Criar o primeiro nível usando a **Camada 3** como base de colisão.
5.  Implementar o primeiro inimigo (Shadow Crawler) e o primeiro Boss (Guardião do Portão).

Com este pacote, você tem a visão, a história e os assets visuais necessários para começar a programar.
