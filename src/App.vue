<script setup lang="ts">
  import { Ref, ref} from 'vue';

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
  <h1> Investimento - Afinal, o que é? </h1>
  <br>
  <img src="./assets/fluxo-de-caixa-de-investimentos.jpg" alt="Foto de um gráfico ilustrativo"/>
  
  <div id="text_contet">
    <p> Investimento refere-se ao ato de alocar recursos, como dinheiro, tempo ou esforço, em um ativo, projeto ou empreendimento, com o objetivo de obter um retorno ou ganho no futuro. </p>
    <p> Geralmente, as pessoas investem para aumentar sua riqueza, proteger contra a inflação, alcançar objetivos financeiros específicos (como aposentadoria, educação dos filhos, etc.) ou simplesmente para diversificar seus ativos. </p>
  </div>

  <h1> E quais são as formas de investir?</h1>
  <img src="./assets/Criptoativos.jpg" alt="Foto de uma Bitcoin sendo pega por uma mão de uma carteira">
  <br />

  <p> Os investementos podem assumir diversas formas, incluindo:</p>
  <div id="text_contet">
    <ol>
      <li>Mercado Financeiro: Isso envolve investir em instrumentos financeiros como ações, títulos, fundos mútuos, entre outros.</li>
      <li>Empreendedorismo: Investir em um negócio próprio ou em um empreendimento de terceiros.</li>
      <li>Educação e Habilidades: Investir em educação e desenvolvimento de habilidades para aumentar seu potencial de ganhos no longo prazo.</li>
      <li>Arte e Colecionáveis: Investir em obras de arte, antiguidades ou outros itens colecionáveis que possam se valorizar ao longo do tempo.</li>
      <li>Metais Preciosos: Investir em ouro, prata ou outros metais preciosos que são considerados como reservas de valor.</li>
      <li>Criptomoedas: Investir em moedas digitais como o Bitcoin, Ethereum, etc.</li>
      <li>Pensão e Previdência: Contribuir para fundos de pensão ou planos de previdência para garantir uma fonte de renda na aposentadoria.</li>
      <li>Emprestar Dinheiro: Emprestar dinheiro a indivíduos ou empresas em troca de juros ou participação nos lucros.</li>
      <li>Desenvolvimento Pessoal: Investir em si mesmo, seja em saúde, bem-estar, ou coaching.</li>
    </ol>
  </div>

  <h1> E a poupança, é ou não é investimento?</h1>
  <img src="./assets/quanto-rendem-50-mil-na-poupanca-1.jpg" alt="Foto de um porquinho com moeads do lado" />
  <br />

  <div id="text_contet">
    <p>A poupança é frequentemente considerada uma forma de investimento, mas é importante notar que ela possui algumas características distintas em comparação com outros tipos de investimentos.</p>
    <p>A principal diferença reside no retorno financeiro que a poupança oferece. Ela é considerada uma opção de investimento de baixo risco, mas também proporciona um retorno relativamente baixo em termos de juros. </p>
    <p>Nos últimos anos, em muitos lugares do mundo, as taxas de juros para contas de poupança têm sido bastante baixas, o que significa que o crescimento do dinheiro investido é limitado.</p>
    <p>Por outro lado, outros tipos de investimentos, como ações, títulos, fundos mútuos, imóveis e até mesmo algumas formas de empreendedorismo, podem oferecer potencial de retorno muito mais elevado, mas geralmente vêm acompanhados de um nível de risco maior.</p>
    <p>sso significa que há a possibilidade de ganhar mais dinheiro, mas também a possibilidade de perder parte ou a totalidade do investimento.</p>
    <p>Além disso, a poupança é altamente líquida, o que significa que você pode acessar o seu dinheiro a qualquer momento sem enfrentar penalidades significativas. </p>
    <p> Outros tipos de investimentos, como títulos ou imóveis, podem ser menos líquidos e requerem um período de tempo mais longo para maturação ou venda.</p>
    <p>Em resumo, a poupança pode ser considerada um tipo de investimento, mas é uma opção de baixo risco e baixo retorno. Outros tipos de investimentos oferecem um espectro mais amplo de oportunidades e riscos, e a escolha dependerá dos objetivos e tolerância ao risco de cada pessoa.</p>
    <p>Portanto, enquanto a poupança é uma forma válida de guardar dinheiro, para quem busca aumentar significativamente sua riqueza ao longo do tempo, muitas vezes é necessário considerar outras opções de investimento.</p>
  </div>
  <p>A poupança é frequentemente considerada uma forma de investimento, mas é importante notar que ela possui algumas características distintas em comparação com outros tipos de investimentos.</p>

  <h1>Quanto meu dinheiro renderia?</h1>
  <br />

  <h2> Com um imóvel </h2>
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

<style scoped>
img:hover {
  -webkit-filter: drop-shadow(0 0 2em #646cffaa);
  -moz-filter: drop-shadow(0 0 2em #646cffaa);
  filter: drop-shadow(0 0 2em #646cffaa);
}

p:hover {
  -webkit-filter: drop-shadow(0 0 2em #646cff8a);
  -moz-filter: drop-shadow(0 0 2em #646cffaa);
  filter: drop-shadow(0 0 2em #646cff8a);
}
</style>
