================================================================================
 VIDEO CINEMATOGRAPHER GEM — README
 Agente de Prompt Engineering para Google Veo 2 via Flow
================================================================================

SOBRE O AGENTE
--------------
O Video Cinematographer é um Gem do Google Gemini especializado em transformar
descrições de frames em prompts cinematográficos detalhados para o Google Veo 2
via Flow. Ele nunca gera vídeo ou imagem diretamente — seu único output é texto
técnico pronto para ser colado no Flow.

O agente foi projetado para resolver um problema específico: o Gemini tem viés
para gerar mídia automaticamente, o que consome o limite de 3 gerações diárias.
Este agente contorna isso operando em modo texto puro, com múltiplas proteções
anti-trigger embutidas.


PROBLEMA QUE RESOLVE
--------------------
- Você tem frames de referência (Start Frame / End Frame)
- Precisa de um prompt técnico e cinematográfico para o Flow
- Mas não quer gastar uma geração só para testar um prompt ruim
- E o Gemini fica gerando vídeo quando não devia

O agente resolve os três pontos: escreve o prompt certo, em formato técnico,
sem acionar a geração automática.


COMO USAR
---------
Cole o conteúdo do arquivo "video-cinematographer-gem.txt" como instrução
do seu Gem no Google Gemini (Gemini > Gems > Criar Gem > Instruções).

Depois, use assim:

  Exemplo basico:
    Start Frame: Close-up de uma xicara de cafe sendo preenchida
    End Frame: Vista aerea da mesa com a xicara e as maos de alguem segurando

  Exemplo com contexto extra:
    Start Frame: Drone sobre floresta ao amanhecer
    End Frame: Camera rasante entre as arvores chegando a uma cabana
    Estilo: cinematografico, frio, melancolico

O agente vai fazer ate 3 perguntas rapidas (estilo, pacing, mood) antes de
gerar — a menos que voce ja tenha fornecido essas informacoes ou diga
"so vai".


O QUE O AGENTE ENTREGA
-----------------------
Para cada par de frames, voce recebe:

  [Cinematic Concept]    Nome da estrategia de movimento usada
  [Compatibility Check]  Avaliacao se a transicao e viavel
  [Technical Prompt]     Prompt completo (150-250 palavras, passado narrativo)
  [Camera Specs]         Lente, movimento, iluminacao, frame rate, efeitos
  [Duration Breakdown]   O que acontece em 0-2s / 2-5s / 5-8s
  [Flow Paste-Ready]     Versao limpa, sem formatacao, pronta para colar no Flow

Se quiser so o paste-ready, diga "so o paste" e o agente pula o resto.


ESTRATEGIAS DE MOVIMENTO DISPONIVEIS
--------------------------------------
O agente seleciona automaticamente a melhor estrategia:

  Dynamic Morph         Transformacao organica do mesmo sujeito
  FPV Drone Flow        Travessia rapida entre locais distantes
  Cinematic Dolly/Zoom  Mudanca de perspectiva na mesma cena
  Temporal Warp         Progressao de tempo (vazio>cheio, dia>noite)
  Orbital Reveal        Rotacao/orbita ao redor do sujeito
  Dream Logic Morph     Transicoes surrealistas ou abstratas


PROTECOES ANTI-GERACAO
-----------------------
O agente usa tres camadas de protecao para nao consumir seu limite diario:

  1. Flag de abertura: toda resposta comeca com [TEXT-ONLY PROMPT BLUEPRINT]
  2. Vocabulario seguro: nunca usa "generate", "create", "render" — usa
     "describe", "specify", "blueprint" no lugar
  3. Narracao no passado: "a camera moveu" em vez de "mova a camera"
     (verbos imperativos sao gatilhos de geracao no Gemini)


LIMITACOES CONHECIDAS
---------------------
- Videos sao fixos em 8 segundos (limitacao do Flow, nao do agente)
- O agente nao valida se o prompt gerado sera aceito pelo Veo 2 — isso
  so e descoberto ao colar no Flow
- Frames muito incompativeis (ex: formiga > galaxia) vao receber um aviso,
  mas o agente tenta assim mesmo com a melhor abordagem disponivel


ARQUIVOS DESTE PACOTE
---------------------
  video-cinematographer-gem.txt   System prompt completo — cole no seu Gem
  README.txt                      Este arquivo


VERSAO
------
  v1.1 — Refinado com intake de perguntas, 4 formatos de input,
          validacao integrada ao fluxo e estrategia Dream Logic Morph

================================================================================
