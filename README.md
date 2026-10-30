# Ouroboros

Jogo da cobrinha em 3D no navegador. Three.js, sem build e sem CDN.

## Como jogar

Abra o `index.html` com duplo clique. Não precisa de servidor.

A tela de entrada é a **pele da cobra que você está vestindo**, em close — e as
escamas são peças de verdade, em relevo, cada uma pegando a luz sozinha (não é
textura pintada). O padrão da cobra vestida reaparece ali, escama por escama.

**Segure o JOGAR para entrar.** A barra do botão e a entrada da cobra são o
mesmo valor: enquanto ela enche, o close encolhe até ser a cobra de verdade,
com a cabeça na frente, e a câmera recua até o tabuleiro. A partida começa com
a barra cheia e ela já inteira lá dentro. Soltar no meio desfaz tudo e devolve
o close. O botão enche com a textura da cobra que você veste — trocou no
vestiário, o botão muda. Dificuldade, Vestiário e Configurações não disparam
nada.

- **Jogar** começa a partida; **Dificuldade** escolhe o nível; **Configurações**
  liga ou desliga o som e a pausa ao sair da aba.
- Setas ou WASD. No celular, deslize o dedo. **P** pausa.
- **Fácil** (meta 15), **Médio** (25) e **Difícil** (40). Bater a meta dá um token.
- A **maçã vermelha** é só ponto. As coloridas dão poder: **azul** escudo,
  **roxa** lento, **dourada** pontos em dobro.
- **Obstáculos** são pedras que caem do céu ao longo da partida; a marca no chão
  avisa onde. Com o escudo, bater numa pedra a estilhaça; bater no muro faz a
  cobra deslizar rente a ele em vez de morrer.
- Ao morrer dá para **reviver** uma vez, com um token ou 10 pontos do banco.
- **Vestiário** com 30 cobras. As 24 primeiras vêm dos **pontos somados na
  vida** (que nunca se gastam); as 6 últimas, de **desafios** — comer 5 maçãs
  de poder numa partida, chegar a 20 pontos sem usar poder, quebrar 10
  obstáculos com o escudo, ficar 3 minutos viva, jogar 50 partidas e bater a
  meta dos três níveis. A cobra que você veste aparece no jogo inteiro.

## Arquivos

```
index.html             a página
jogo.src.js            a fonte do jogo
jogo.js                gerado a partir da fonte (é o que a página carrega)
three.module.min.js    Three.js 0.170.0, entrada do empacotamento
```

**Editou `jogo.src.js`? Regere o `jogo.js`:**

```bash
npx esbuild jogo.src.js --bundle --minify --format=iife --outfile=jogo.js
```

Módulo ES é bloqueado em `file://`, por isso a página carrega um `<script>`
comum em vez de importar o Three.js direto. É o que faz o duplo clique
funcionar.
