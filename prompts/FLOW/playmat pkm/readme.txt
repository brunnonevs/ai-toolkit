========================================
  POKEMON PLAYMAT PROMPT - README
========================================

OBJETIVO
--------
Transformar cartas do Pokemon TCG em artes 16:9 para impressao de playmat.
O prompt le a carta anexada como input e gera a ilustracao automaticamente.

COMO USAR
---------
1. Abra o Google Flow (ou gerador compativel com input de imagem)
2. Anexe a foto da carta Pokemon usando o botao +
3. Cole o conteudo do prompt escolhido no campo de texto
4. Gere - o modelo le a carta e monta a arte sozinho

ARQUIVOS
--------
pokemon-playmat-prompt-v1.1.txt  ->  Estilo AQUARELA
pokemon-playmat-prompt-v1.2.txt  ->  Estilo PIXEL ART

DIFERENCA ENTRE AS VERSOES
---------------------------
v1.1 - Watercolor (Aquarela)
  Arte em estilo aquarela com reticula halftone sutil.
  Resultado mais suave e pictorico. Ideal para playmats com visual artistico.
  A reticula se mantem - otima para impressao em 300 dpi apos upscale.

v1.2 - Dithered Pixel Art
  Arte em estilo pixel art retro, GBA/SNES-era.
  Dithering mais intenso, visual nostalgico de Game Boy Advance.
  Ideal para quem quer o visual retro mais pronunciado.

O QUE O PROMPT FAZ AUTOMATICAMENTE
------------------------------------
- Identifica se a carta e Pokemon ou Trainer/Supporter/Item
- Le: nome, HP, tipo de energia, ataques, custo de energia, dano, ilustrador e numero
- Gera a arte 16:9 com o Pokemon (ou Trainer) como protagonista
- Monta o HUD estilo Ruby e Sapphire com os dados lidos da carta

HUD - LAYOUT
------------
  [NOME]                          [HP XX (icone tipo)]
  
        (arte - sujeito ao centro)
  
        [(icone) Ataque 1         20]
        [(icone)(icone) Ataque 2  40]
                          Illus. xxx / 000/000

  - Trainer/Supporter: sem caixa de HP, efeito resumido em ate 6 palavras
  - Custo de energia: circulos coloridos com icone branco, repetidos por energia
  - Ataque sem dano: exibe -

HUD - TAMANHOS FIXOS
---------------------
  Nome e HP:     8% da altura da imagem
  Caixa ataques: 18% da altura, 50% da largura, centralizada
  Margens:       ~2% das bordas

COMPOSICAO
----------
  Wide shot - sujeito ocupa ~50% da altura do frame
  Cenario visivel em todos os lados (ceu, chao, ambiente)
  AR fixo: 16:9

FRAME
-----
  Borda cinza estilo bezel de Game Boy Advance
  A arte fica dentro do frame

FLUXO DE PRODUCAO RECOMENDADO
------------------------------
  1. Gerar no Flow com o prompt (v1.1 ou v1.2)
  2. Fazer upscale para 300 dpi (ex: Topaz Gigapixel, Magnific, krea.ai)
  3. Enviar para impressao do playmat

HISTORICO DE VERSOES
---------------------
  v1.0  - Prompt base: pixel art, HUD Ruby/Sapphire, frame GBA, custo de energia
  v1.1  - Estilo aquarela, zoom out (wide shot 50%), suporte a cartas Trainer
  v1.2  - Igual ao 1.1, estilo pixel art de volta

========================================
