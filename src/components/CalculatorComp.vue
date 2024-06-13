<template>

  <div class="calculatorContainer">
    <div class="about">
      <h1>This is a calculator page!!!</h1>
    </div>
  
    <div class="calculatorScreen">
      <p id="userInput">0</p>
    </div>
  
    <div class="keyboard">

      <div class="number">7</div>
      <div class="number">8</div>
      <div class="number">9</div>
      <div class="operator">/</div>

      <div class="number">4</div>
      <div class="number">5</div>
      <div class="number">6</div>
      <div class="operator">×</div>

      <div class="number">1</div>
      <div class="number">2</div>
      <div class="number">3</div>
      <div class="operator">-</div>

      <div class="number-empty"></div>
      <div class="number">0</div>
      <div class="number">.</div>
      <div class="operator">+</div>

    </div>
      
    <div class="row5">
      <div class="buttonCE">CE</div>
      <div class="buttonequal">=</div>
    </div>
  </div>
  </template>
  
<style scoped lang="scss">

.calculatorContainer {
  background-color: rgb(44, 48, 81);
  padding: 15px;
}

.calculatorScreen {
  border: 1px solid red;
}

.keyboard {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;

    div {
      background-color: #373C67;
      border-radius: 16px;
      padding-block: 10px;
      padding-inline: 21px;
      text-align: center;
      color: #E8E8EC;
      font-size: 20px;
    }
}
</style>

<script setup>

/// The backgroundColor of each button is: rgb(55, 60, 103);
</script>