<template>

  <div class="heading">
    <h2>Calculator</h2>
  </div>

  <div class="calculatorContainer">
  
    <div class="calculatorScreen">
      <p id="userInput">0</p>
    </div>
  
    <div class="keyboard">

      <div class="key number">7</div>
      <div class="key number">8</div>
      <div class="key number">9</div>
      <div class="key operator">/</div>

      <div class="key number">4</div>
      <div class="key number">5</div>
      <div class="key number">6</div>
      <div class="key operator">×</div>

      <div class="key number">1</div>
      <div class="key number">2</div>
      <div class="key number">3</div>
      <div class="key operator">-</div>

      <div class="key number number-empty"></div>
      <div class="key number">0</div>
      <div class="key number">.</div>
      <div class="key operator">+</div>

    </div>
      
    <div class="controls">
      <div class="key buttonCE">CE</div>
      <div class="key buttonequal">=</div>
    </div>
  </div>
  </template>
  
<style scoped lang="scss">

.calculatorContainer {
  max-width: 310px;
  background-color: rgb(44, 48, 81);
  padding: 15px;
  border-radius: 20px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.calculatorScreen {
  background-color: #373C67;
  padding: 20px 15px;
  border-radius: 16px;
  text-align: right;
  font-size: 20px;
}

.keyboard {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
    .operator {
      color: #EB8A30;
    }
}

.key {
  background-color: #373C67;
  border-radius: 16px;
  padding-block: 10px;
  padding-inline: 21px;
  text-align: center;
  color: #E8E8EC;
  font-family: "Lato", sans-serif;
  font-weight: 700;
  font-size: 20px;

    &:hover {
      cursor: pointer;
    }
  }

.controls {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
    .buttonCE {
      background-color: #373C67;
      color: #1B54E9;
    }
    .buttonequal {
      background-color: #1B54E9
    }
}
</style>

<script setup>

/// The backgroundColor of each button is: rgb(55, 60, 103);
</script>