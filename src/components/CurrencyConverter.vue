<script setup>
import { ref } from 'vue';
import Freecurrencyapi from '@everapi/freecurrencyapi-js';

const inputAmount = ref(0);
const inputFromCurrency = ref('USD');
const inputToCurrency = ref('EUR');
const result = ref(null);
const isConverting = ref(false);

const freecurrencyapi = new Freecurrencyapi('fca_live_mttqkBS6GLC1kWULIW86L76swGrAWlWmURwD2WQU');

const currencies = ref([
  { code: 'EUR', name: 'Euro (€)' },
  { code: 'USD', name: 'Dollar ($)' },
  { code: 'JPY', name: 'Yen (¥)' },
  { code: 'HNL', name: 'Honduran Lempira (Honduras)' },
]);

const convertCurrency = async () => {
  isConverting.value = true;
  try {
    const response = await freecurrencyapi.latest({
      base_currency: inputFromCurrency.value,
      currencies: inputToCurrency.value
    });

    const rate = response.data[inputToCurrency.value];
    result.value = {
      amount: inputAmount.value,
      fromCurrency: inputFromCurrency.value,
      toCurrency: inputToCurrency.value,
      convertedAmount: (inputAmount.value * rate).toFixed(4)
    };
  } catch (error) {
    console.error('Error fetching the conversion rate:', error);
  } finally {
    isConverting.value = false;
  }
};
</script>

<template>
  <div class="heading">
    <h2>Currency Converter</h2>
  </div>

  <div class="currency-converter">
    <div>
      <label for="amount">Amount</label>
      <input id="amount" v-model="inputAmount" type="number" placeholder="Enter amount" />
    </div>
    <div>
      <label for="fromCurrency">From</label>
      <select id="fromCurrency" v-model="inputFromCurrency">
        <option v-for="currency in currencies" :key="currency.code" :value="currency.code">
          {{ currency.name }}
        </option>
      </select>
    </div>
    <div>
      <label for="toCurrency">To</label>
      <select id="toCurrency" v-model="inputToCurrency">
        <option v-for="currency in currencies" :key="currency.code" :value="currency.code">
          {{ currency.name }}
        </option>
      </select>
    </div>
    <button :disabled="isConverting" @click="convertCurrency">Convert</button>
    <div v-if="result">
      <p class="from">{{ result.amount }} {{ result.fromCurrency }} = </p>
      <p class="to">{{ result.convertedAmount }} {{ result.toCurrency }}</p>
    </div>
  </div>
</template>
  


<style lang="scss" scoped>
.currency-converter {
max-width: 310px;
background-color: rgb(44, 48, 81);
padding: 15px;
border-radius: 20px;
display: flex;
flex-direction: column;
gap: 20px;

  input, select {
    width: 100%;
    background-color: #373C67;
    padding: 15px;
    border-radius: 16px;
    border: none;
    font-size: 18px;
    color: #E8E8EC;
      &:hover {
        cursor: pointer;
      }
  }
}

label, .from {
  color: #969BC1;
  font-family: "Lato", sans-serif;
  font-weight: 700;
  font-size: 15px;
}

.to {
  color: #E8E8EC;
  font-family: "Lato", sans-serif;
  font-weight: 700;
  font-size: 18px;
}

button {
  background-color: #1B54E9;
  border-radius: 16px;
  padding-block: 15px;
  padding-inline: 21px;
  text-align: center;
  color: #E8E8EC;
  font-family: "Lato", sans-serif;
  font-weight: 700;
  font-size: 16px;
  border: none;
  margin-top: 10px;

    &:hover {
      cursor: pointer;
    }
  }

</style>
  