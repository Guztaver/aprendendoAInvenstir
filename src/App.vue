<script setup lang="tsx">
import Risks from './components/Risks.vue';
import Savings from './components/Savings.vue';
import Investing from './components/Investing.vue'
import WhatIs from './components/WhatIs.vue'
import AboutUs from './components/AboutUs.vue'
</script>

<template>
  <header>
    <h1>Investimento: A Alocação Estratégica de Recursos para o Futuro</h1>
    <p>Muitas pessoas não tem ideias de como investir, ou até, o que é investir. Nesse artigo, temos em vista esclarecer o
      que é investir, como investir, e dar exemplos de como investir corretamente!</p>
  </header>

  <main>
    <img src="./assets/fluxo-de-caixa-de-investimentos.jpg" alt="Foto de um gráfico ilustrativo" />

    <label for="navigator">
      <p><b>Os tópicos abordados serão:</b></p>
    </label>

    <section>
      <ol id="navigator">
        <li><a href="#invest">O que é investir?</a></li>
        <li><a href="#risks">E quais são as formas de investir?</a></li>
        <li><a href="#savings">E a poupança, é ou não é investimento?</a></li>
        <li><a href="#investing">Quanto meu dinheiro renderia?</a></li>
        <li><a href="#about_us">Sobre nós</a></li>
      </ol>
    </section>

    <hr>

    <article>
      <WhatIs />
    </article>

    <article>
      <Risks />
    </article>

    <article>
      <Savings />
    </article>

    <article>
      <Investing />
    </article>

    <br />
    <section>
      <p>Para mais informações, visite o site do <a href="https://bcb.gov.br">Banco Central</a>.</p>
    </section>

    <hr>

  </main>

  <footer>
    <section>
      <AboutUs />
    </section>
  </footer>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Merriweather:wght@300&display=swap');

:root {
  display: flex;

  padding-left: 20%;
  padding-right: 20%;
  justify-content: center;

  font-family: 'Merriweather', system-ui, Avenir, Helvetica, Arial, sans-serif;
  line-height: 1.5;
  font-weight: 400;
  font-size: 1.1em;

  background: rgb(254, 249, 236);
  color: rgb(0, 0, 0);

  font-synthesis: none;
  text-rendering: optimizeLegibility;

  max-width: 100%;
  overflow-x: hidden;

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-text-size-adjust: 100%;
}

root:hover {
  -webkit-filter: drop-shadow(0 0 2em #ffb282);
  -moz-filter: drop-shadow(0 0 2em #ffb282);
  filter: drop-shadow(0 0 2em #ffb282);
  transition: all 0.15s ease;
}

@media only screen and (max-width: 844px) {
  :root{
    padding-left: 2%;
    padding-right: 2%;
    font-size: 14px;
    justify-content: flex-start;
  }
}

@media (prefers-color-scheme: dark) {
  :root {
    background: rgb(4, 24, 77);
    color: rgba(255, 255, 255);
  }
  html:hover {
    -webkit-filter: drop-shadow(0 0 2em #631bf0);
    -moz-filter: drop-shadow(0 0 2em #631bf0);
    filter: drop-shadow(0 0 2em #631bf0);
    transition: all 0.15s ease;
  }
  a {
    color: #c4a7fc;
  }
}

a {
  font-weight: 500;
  text-decoration: inherit;
}

body {
  margin: 0;
  place-items: center;
  min-width: 320px;
  min-height: 100vh;
}

img {
  border-radius: 15px;
  margin-right: auto;
  width: 70%;
}

body {
  overflow-x: hidden;
  position: relative;
}

h1, h2 {
  color: #bcb65d;
  font-size: 2.2em;
}

h3 {
  color: #bcb650;
  top: 1%;
  padding-left: 0.5%;
  font-size: 2.2em;
  line-height: 1.1;
}

h2 {
  top: 0.5%;
  padding: 0.5%;
  font-size: 1.8em;
  line-height: 1.0;
}

h3 {
  top: 0.5%;
  padding: 0.5%;
  font-size: 1.4em;
  line-height: 1.0;
}

button {
  border-radius: 8px;
  border: 1px solid transparent;
  padding: 0.6em 1.2em;
  font-size: 1em;
  font-weight: 500;
  font-family: inherit;
  background-color: #1a1a1a;
  cursor: pointer;
  transition: border-color 0.25s;
}


label, input {
  transition: all 0.5s ease;
}


input {
  font-size: 1rem;
  border-style: solid;
  text-align: center;
  border-radius: 8px;
}

button:focus-visible {
  outline: 4px auto -webkit-focus-ring-color;
}

ol {
  list-style: circle;
}

img:hover,
p:hover,
li:hover,
ol:hover,
input:hover
a:hover,
h1:hover, 
h2:hover, 
h3:hover {
  -webkit-filter: drop-shadow(0 0 2em #631bf0);
  -moz-filter: drop-shadow(0 0 2em #631bf0);
  filter: drop-shadow(0 0 2em #631bf0);
  transition: all 0.15s ease;
}

</style>