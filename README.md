# Cobrinha 3D

Jogo da cobrinha em 3D no navegador. Three.js, sem build e sem CDN.

## Como jogar

Abra o `index.html` com duplo clique. Não precisa de servidor.

- **Jogar** começa a partida; **Dificuldade** escolhe o nível; **Configurações**
  liga ou desliga o som e a pausa ao sair da aba.
- Setas ou WASD. No celular, deslize o dedo. **P** pausa.
- **Fácil** (meta 15), **Médio** (25) e **Difícil** (40). Bater a meta dá um token.
- A **maçã vermelha** é só ponto. As coloridas dão poder: **azul** escudo,
  **roxa** lento, **dourada** pontos em dobro.
- **Obstáculos** caem do céu ao longo da partida; a marca no chão avisa onde.
- Ao morrer dá para **reviver** uma vez, com um token ou 10 pontos do banco.

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
