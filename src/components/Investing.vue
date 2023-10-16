<script setup lang="tsx">
  import { ref, Ref } from 'vue';

  const invesmentBuyPrice: Ref<number> = ref(5000.00);
  const invesmentMonthlyRent: Ref<number> = ref(1000.00);
  const invenstmenteSellPrice: Ref<number> = ref(250000);
  const timeOfInvenstmentInYears: Ref<number> = ref(5);
  const invesmentBuySellCosts: Ref<number> = ref(10000);

    function formatPrice(value: any){ 
        let val = (value/1).toFixed(2).replace('.', ',')
        return val.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ".")
    }
</script>

<template>
  <h2>Quanto meu dinheiro renderia?</h2>
  <br />

  <h3> Com um imóvel </h3>
  <div id="text_contet">
    <div>
      <label for="sellPrice"> Por quanto quer vender depois de {{ timeOfInvenstmentInYears }} anos: </label>
      <input min="0" type="number" id="sellPrice" v-model="invenstmenteSellPrice"/>
    </div>
    
    <div>
      <label for="monthlyRent"> Quanto quer cobrar de aluguel: </label>
      <input min="0" type="number" id="monthlyRent" v-model="invesmentMonthlyRent"/>
    </div>

    <div>
      <label for="buyPrice"> Qual o preço do imóvel: </label>
      <input min="0" type="number" id="buyPrice" v-model="invesmentBuyPrice"/>
    </div>

    <div>
      <label for="investmentYears"> Quantos anos quer investir: </label>
      <input min="0" type="number" id="investmentYears" v-model="timeOfInvenstmentInYears"/>
    </div>

    <div>
      <label for="buySellCosts"> Quanto seria o custo associado à compra e venda: </label>
      <input min="0" type="number" id="buySellCosts" v-model="invesmentBuySellCosts"/>
    </div>
  
    <p>Você teria R${{ formatPrice(invesmentMonthlyRent * 12 * timeOfInvenstmentInYears) }} retornados de aluguel, ao longo de {{ timeOfInvenstmentInYears }} anos, e se vendesse, teria R${{ formatPrice(invenstmenteSellPrice - invesmentBuyPrice - invesmentBuySellCosts) }} de retorno.</p>
  </div>
</template>
