<script setup lang="tsx">
import { ref, Ref } from 'vue';

//Poupança
let savingsInitialInvestedPrice: Ref<number> = ref(1000.00);
let savingsTaxesFees: Ref<number> = ref(2);
let savingsInYears: Ref<number> = ref(5);

//Ações
let sharesInvestedPrice: Ref<number> = ref(1000.00);
let sharesRevenue: Ref<number> = ref(7.0);
let sharesInYears = 5;

//Imóvel
const immobilePrice: Ref<number> = ref(5000.00);
const immobileRentInAMont: Ref<number> = ref(1000.00);
const imobileSellPrice: Ref<number> = ref(250000);
const immobileInvestmentInYears: Ref<number> = ref(5);
const immobileBuyAndSellCost: Ref<number> = ref(10000);

function formatPrice(value: any) {
  let val = (value / 1).toFixed(2).replace('.', ',')
  return val.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ".")
}
</script>

<template>
  <h2 id="investing">Quanto meu dinheiro renderia?</h2>

  <h3> Com um imóvel </h3>

  <div id="text_contet house">
    <div>
      <label for="sellPrice"> Por quanto quer vender depois de {{ immobileInvestmentInYears }} anos: </label>
      <input min="0" type="number" id="sellPrice" v-model="imobileSellPrice" />
    </div>

    <div>
      <label for="monthlyRent"> Quanto quer cobrar de aluguel: </label>
      <input min="0" type="number" id="monthlyRent" v-model="immobileRentInAMont" />
    </div>

    <div>
      <label for="buyPrice"> Valor do imóvel: </label>
      <input min="0" type="number" id="buyPrice" v-model="immobilePrice" />
    </div>

    <div>
      <label for="investmentYears"> Quantos anos quer investir: </label>
      <input min="0" type="number" id="investmentYears" v-model="immobileInvestmentInYears" />
    </div>

    <div>
      <label for="buySellCosts"> Quanto seria o custo associado à compra e venda: </label>
      <input min="0" type="number" id="buySellCosts" v-model="immobileBuyAndSellCost" />
    </div>

    <p>Você teria R${{ formatPrice(immobileRentInAMont * 12 * immobileInvestmentInYears) }} retornados de aluguel, ao
      longo de {{ immobileInvestmentInYears }} anos, e se vendesse, teria R${{ formatPrice(imobileSellPrice -
        immobilePrice - immobileBuyAndSellCost) }} de retorno.</p>
  </div>

  <div id="text_contet actions">
    <h3>Ações</h3>
    <div>
      <label for="actionsInvestedPrice">Valor inicial a ser investido: </label>
      <input min="0" type="number" id="actionsInvestedPrice" v-model="sharesInvestedPrice" />
    </div>

    <div>
      <label for="actionsRevenue">Taxa anual de rendimento das ações: </label>
      <input min="0" type="number" id="actionsRevenue" v-model="sharesRevenue" />
    </div>

    <div>
      <label for="actionsInYears">Período do investimento: </label>
      <input min="0" type="number" id="actionsInYears" v-model="sharesInYears" />
    </div>
    <p>
      Você teria R${{ formatPrice((sharesInvestedPrice * Math.pow(1 + (sharesRevenue / 100), sharesInYears)).toFixed(2))
      }}
      em ações, se tivesse investido {{ sharesInvestedPrice }} em {{ sharesInYears }} com a taxa anual de {{ sharesRevenue
      }}%.
    </p>
  </div>

  <div>
    <h3> Poupança </h3>
    <div id="text_contet savings">
      <div>
        <label for="savingsnIntialPrice">Valor inicial a ser investido: </label>
        <input min="0" type="number" id="savingsnIntialPrice" v-model="savingsInitialInvestedPrice" />
      </div>

      <div>
        <label for="savingsInYears">Período guardando: </label>
        <input min="0" type="number" id="savingsInYears" v-model="savingsInYears" />
      </div>

      <div>
        <label for="savingsTaxesFees">Taxa anual de juros: </label>
        <input min="0" type="number" id="savingsTaxesFees" v-model="savingsTaxesFees" />
      </div>
      <p> Você teria R${{ formatPrice((savingsInitialInvestedPrice * Math.pow(1 + (savingsTaxesFees / 100),
        savingsInYears)).toFixed(2)) }} na poupança, se tivesse guardado ao longo de {{ savingsInYears }}, com a taxa
        anual
        de juros a {{ savingsTaxesFees }}%. </p>
    </div>
  </div>
</template>
