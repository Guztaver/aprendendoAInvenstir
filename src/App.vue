<script setup lang="tsx">
import Risks from './components/Risks.vue';
import Savings from './components/Savings.vue';
import Investing from './components/Investing.vue'
import WhatIs from './components/WhatIs.vue'
import AboutUs from './components/AboutUs.vue'
</script>

<template>
  <h1>Investimento: A Alocação Estratégica de Recursos para o Futuro</h1>

  <img src="./assets/fluxo-de-caixa-de-investimentos.jpg" alt="Foto de um gráfico ilustrativo" />

  <label for="navigator">
    <p><b>Os tópicos abordados serão:</b></p>
  </label>

  <ol id="navigator">
    <li><a href="#invest">O que é investir?</a></li>
    <li><a href="#risks">E quais são as formas de investir?</a></li>
    <li><a href="#savings">E a poupança, é ou não é investimento?</a></li>
    <li><a href="#investing">Quanto meu dinheiro renderia?</a></li>
  </ol>

  <hr>

  <WhatIs />

  <Risks />

  <Savings />

  <Investing />

  <hr>

  <AboutUs />
</template>

<style></style>
