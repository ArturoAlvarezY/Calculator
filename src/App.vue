<script setup>
import Calculator from './components/CalculatorComp.vue';
import TheWeather from './components/TheWeather.vue';
import CurrencyConverter from './components/CurrencyConverter.vue';
</script>

<template>
  <header>
  </header>

  <main>
     <TheWeather />
     <Calculator />
     <CurrencyConverter/>
  </main>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@400;700&display=swap');
main {
  padding-block: 30px;
  margin-inline: auto;
}
h1, h2, h3 {
  font-family: "Montserrat", sans-serif;
  font-optical-sizing: auto;
  font-weight: 700;
  font-style: normal;
  color: #E8E8EC;
}

.lato-regular {
  font-family: "Lato", sans-serif;
  font-weight: 400;
  font-style: normal;
}

input, select {
  font-family: "Lato", sans-serif;
  font-weight: 700;
  font-style: normal;
}

.heading {
  margin-bottom: 15px;
  margin-top: 30px;
}
</style>