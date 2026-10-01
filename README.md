 /* CARREGAMENTO DAS FONTES LOCAIS (@font-face) */
@font-face {
  font-family: 'Glacial Indifference';
  src: url('../fonts/GlacialIndifference-Regular.otf') format('opentype');
  font-weight: normal;
  font-style: normal;
  font-display: swap;
}

@font-face {
  font-family: 'Lovelo Line';
  src: url('../fonts/Lovelo\ Line\ Light\ 300.otf') format('opentype');
  font-weight: bold;
  font-style: normal;
  font-display: swap;
}

/* ---------- Variáveis e Base ---------- */
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html, body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  position: relative;
  overflow-x: hidden; /* Evita rolagens laterais indesejadas */
  background-color: var(--cor-fundo);
  color: var(--cor-texto);
  font-family: var(--fonte-corpo);
  font-size: var(--tamanho-corpo);
}

h1 {
  font-family: var(--fonte-titulo);
  font-size: var(--tamanho-titulo);
}

/* ---------- Margens laterais padrão ---------- */
.header {
  padding-left: 64px;
  padding-right: 64px;
  padding-top: var(--espaco-m);
  padding-bottom: var(--espaco-m);
  position: relative;
  z-index: 10; /* Fica acima das fotos de fundo */
}

/* ---------- Menu ---------- */
.menu ul {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: var(--espaco-g);
  list-style: none;
}

.menu a {
  display: block;
  padding: var(--espaco-p) var(--espaco-m);
  background-color: var(--cor-destaque);
  color: var(--cor-texto-claro);
  font-family: var(--fonte-subtitulo);
  font-size: var(--tamanho-subtitulo);
  text-align: center;
  text-decoration: none;
  border-radius: var(--border-radius-botao);
}

.menu a:hover {
  background-color: var(--cor-destaque-hover);
}

/* ---------- Hero ---------- */
.hero {
  flex: 1; /* Ocupa o espaço livre entre o menu e o rodapé */
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 64px;
  position: relative;
  z-index: 5;
}

.hero__texto {
  color: var(--cor-texto-claro); /* Título em branco */
  position: relative;
  z-index: 6;
}

.hero__texto h1 {
  font-weight: normal;
  line-height: 1.1;
}

.hero__texto p {
  margin-top: var(--espaco-m);
  font-family: var(--fonte-corpo);
  font-size: var(--tamanho-subtitulo);
  color: var(--cor-texto);
}

/* Caixa da colagem */
.hero__figura {
  position: relative;
  flex-shrink: 0;
  height: 60vh;
  aspect-ratio: 1.31 / 1;
  max-width: 48vw;
}

/* Colagem de fotos ao fundo - Cola no topo e na direita da tela */
.hero__fotos {
  position: fixed;   /* Fixa referente à tela total */
  top: 0;            /* Cola no topo absoluto */
  right: 0;          /* Cola na extremidade direita */
  width: 50vw;       /* Ocupa a metade direita da janela */
  height: 100vh;     /* Preenche a altura total da tela */
  object-fit: cover; /* Ajusta sem distorcer a imagem */
  z-index: 1;   
  opacity: 0.9;     /* Fica atrás do menu, do texto e do dente 3D */
}

/* Dente por cima da colagem */
.hero__imagem {
  position: absolute;
  left: 45%;
  top: 55%;
  height: 160%;
  width: auto;
  max-width: none;
  transform: translate(-50%, -50%);
  z-index: 5;        /* Garante que o dente fique à frente do fundo de fotos */
}
