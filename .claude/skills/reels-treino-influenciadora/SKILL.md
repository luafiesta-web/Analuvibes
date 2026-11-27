---
name: reels-treino-influenciadora
description: Montar Reels/TikTok verticais (30–40 s) de influenciadora mostrando um treino para marca de academia (ex. Bibi × BOOM Fit Club) a partir de brutos de iPhone, com música da moda, corte no beat, mix de respiração e motion graphics criativo e clean. Mockup sempre antes do render.
---

# Reels de treino para influenciadora (padrão Bibi × BOOM Fit Club)

## Quando usar
Vídeos curtos verticais (Reels/TikTok, 30–40 s) de influenciadora mostrando um treino para uma marca de academia ou plataforma de aulas, a partir de brutos gravados no iPhone, com música da moda, corte no beat e motion graphics da marca.

## Regras de ouro
- **Mockup antes de qualquer render.** Nada é renderizado sem aprovação. O mockup usa quadros reais gerados pelo mesmo código do render final, para o vídeo sair igual ao que foi aprovado.
- **Motion nunca cobre o rosto.** Detectar o rosto em cada quadro (só o da pessoa, ignorando rostos em telas ao fundo) e posicionar o texto fora dele. Se não couber, o texto some naquele quadro em vez de cobrir o rosto. Registrar e informar qualquer quadro crítico.
- **Só takes da pessoa sozinha.** Nada de instrutora, outros alunos ou terceiros no quadro; recortar (punch-in) se preciso.
- **Só execução correta dos exercícios.** Ex.: no coice com caneleira, só chute para trás, nunca a perna indo para o lado. Na dúvida, perguntar ao editor.
- **Avisar logo de cara quando algo for provisório** (ex.: cortes num BPM estimado antes de ter a música).
- **História:** gancho forte, começo, meio e fim, e CTA final que convida, não que desafia ("Você teria coragem?" afasta; "Bora fazer esse treino comigo?" aproxima). O produto/plano fica implícito.

## Cor e material
- O iPhone grava em **HDR HLG** (bt2020, arib-std-b67). Converter para SDR do jeito certo, senão a imagem fica lavada e acinzentada:
  `zscale=w=1080:h=1920:filter=lanczos:t=linear:npl=203,format=gbrpf32le,zscale=p=bt709,tonemap=hable:desat=0,zscale=t=bt709:m=bt709:r=tv,format=yuv420p`
  Sempre conferir com `ffprobe` (color_transfer) antes de processar.
- **Manter a cor original da câmera.** Não aplicar grade por cima. Fundo sempre com contraste, sem névoa branca e sem flashes brancos.
- Analisar os brutos com contact sheets (ffmpeg tile), mapear takes bons, takes proibidos (outras pessoas, execução errada) e momentos de exaustão (respiração ofegante, mão no rosto).

## Música e corte
- Medir o BPM e as batidas reais da faixa (librosa). Achar os drops pela energia de grave por batida. Escolher os trechos mais animados e editar a música sempre em início de compasso (crossfade de ~20 ms).
- Montar o vídeo em batidas (não em segundos), para tudo — cortes, textos, SFX — cair no beat.
- Abrir o vídeo direto no 1º drop; a parte "Realidade" na subida/breakdown; a mensagem de saúde no 2º drop.
- Cortes de 1 batida e colcheias; semicolcheias só como virada antes de um drop. Alternar planos abertos e fechados.
- Gancho legível: texto na tela por pelo menos 2,5 s, sobre um close sem cortes no meio do texto.
- Checar a letra: evitar trechos com palavrão. Música comercial pode ser silenciada em publi; ter versão alternativa sem música.

## Áudio
- Mix música + respiração original: fôlego audível no gancho; na "Realidade", música abafada (passa-baixa ~500 Hz) e respiração na frente; risada original no CTA. Passa-alta ~120 Hz no áudio da câmera. Avisar que o áudio da sala pode ter música da aula ou voz da instrutora.
- SFX discretos: whoosh na entrada de texto, pop nos selos, impacto no drop, batimento cardíaco na realidade, sino quando o timer fecha.
- Volume final no padrão Instagram: cerca de -14 LUFS, pico abaixo de -1 dB.

## Estética do motion — criativa, circular, clean
- **Recorte da pessoa** quadro a quadro com modelo de vídeo (Robust Video Matting, ONNX), recalculado em todo quadro (nunca pular quadros) e aquecendo o modelo no 1º quadro de cada take, para colocar elementos atrás dela sem atraso no movimento.
- **Palavra gigante atrás do corpo:** nome do exercício (AGACHAMENTO, AFUNDO, CANIVETE, CANOA, COICE) enorme atrás dela, alternando cheio limão e contorno branco a cada batida, entrando com escala no beat; subtítulo pequeno no topo (ex. "COM SALTO").
- **Anel orbital:** texto ("Aula ao vivo · de qualquer lugar") girando em volta da cintura, metade passando atrás e metade na frente, como anel de planeta.
- **Ondas de batimento:** anéis circulares saindo de trás dela a cada batida do coração na parte "Realidade".
- **Selo circular giratório** no CTA e **timer circular** enchendo até 40:00 no canto superior esquerdo.
- **Evitar poluição:** nada de letreiro correndo atrás com o mesmo texto repetido na frente. Menos elementos, mais impacto.
- **Identidade BOOM:** amarelo-limão neon #E4FF3A, preto #0B0B0B e branco; fontes Anton (títulos) e Archivo (apoio); logo oficial no formato exato (pedir SVG ou PNG grande ao cliente), em limão no card final com @boomfitclub.
- Respeitar a zona segura do Instagram (topo 14%, base 20%, direita 12%).

## Roteiro base (cerca de 40 s)
1. Gancho no drop: "Treino de perna + abdômen em 40 minutos".
2. Aula ao vivo: "De qualquer lugar" (telão com alunos treinando de casa; o plano fica implícito).
3. Exercícios: agachamento com salto, afundo alternado, abdominal canivete, abdominal canoa, coice com caneleira.
4. Realidade: câmera lenta, respiração, "Resultado exige esforço."
5. 2º drop: "Não pule o treino de perna" + circulação, sustentação, longevidade.
6. CTA: "Bora fazer esse treino comigo?" + "Salva pra fazer em casa".
7. Card final com o logo da marca.

## Fluxo de trabalho
1. Ver o perfil da marca e extrair a identidade visual.
2. Analisar os brutos e mapear os takes.
3. Mockup do roteiro.
4. Mockup do motion com quadros reais.
5. Aprovação do editor e da influenciadora.
6. Render.
7. Checagens: rosto livre, contraste, volume, duração, takes proibidos.
8. Entregar e salvar na pasta do projeto.
