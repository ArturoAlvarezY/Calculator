<script setup>
import Calculator from './components/CalculatorComp.vue';
import TheWeather from './components/TheWeather.vue';
import CurrencyConverter from './components/CurrencyConverter.vue';
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <!-- <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div> -->
  </header>

  <main>
    <!-- <TheWelcome /> -->
     <TheWeather />
     <Calculator />
     <CurrencyConverter/>
  </main>
</template>

<style lang="scss">
/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@400;700&display=swap');

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


</style>