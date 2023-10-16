<script setup lang="tsx">
  import Risks from './components/Risks.vue';
  import Savings from './components/Savings.vue';
  import Investing from './components/Investing.vue'
</script>

<template>
  <h1> Investimento - Afinal, o que é? </h1>
  <br>
  <img src="./assets/fluxo-de-caixa-de-investimentos.jpg" alt="Foto de um gráfico ilustrativo"/>
  
  <div id="text_contet">
    <p> Investimento refere-se ao ato de alocar recursos, como dinheiro, tempo ou esforço, em um ativo, projeto ou empreendimento, com o objetivo de obter um retorno ou ganho no futuro. </p>
    <p> Geralmente, as pessoas investem para aumentar sua riqueza, proteger contra a inflação, alcançar objetivos financeiros específicos (como aposentadoria, educação dos filhos, etc.) ou simplesmente para diversificar seus ativos. </p>
  </div>
  
  <Risks />
  
  <Savings />

  <Investing />
</template>

<style>
  img:hover, p:hover, li:hover, ol:hover, input:hover {
    -webkit-filter: drop-shadow(0 0 2em #ffffff);
    -moz-filter: drop-shadow(0 0 2em #ffffff);
    filter: drop-shadow(0 0 2em #ffffff);
  }
</style>