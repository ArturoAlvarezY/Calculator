<template>

  <div class="calculatorContainer">
  <div class="about">
    <h1>This is a calculator page!!!</h1>
  </div>

  <div class="calculatorScreen">
    <p id="userInput">0</p>
  </div>

  <div class="row1">
      <div class="numberButton7">7</div>
      <div class="numberButton8">8</div>
      <div class="numberButton9">9</div>
      <div class="button%">%</div>
  </div>
  
  <div class="row2">
      <div class="numberButton4">4</div>
      <div class="numberButton5">5</div>
      <div class="numberButton6">6</div>
      <div class="buttonX">x</div>
  </div>

  <div class="row3">
      <div class="numberButton1">1</div>
      <div class="numberButton2">2</div>
      <div class="numberButton3">3</div>
      <div class="number-">-</div>
  </div>

  <div class="row4">
      <div class="buttonEmpty"></div>
      <div class="button0">0</div>
      <div class="button.">.</div>
      <div class="button+">+</div>
  </div>

  <div class="row5">
    <div class="buttonCE">CE</div>
    <div class="buttonequal">=</div>
  </div>
</div>
</template>

<style scoped>

.calculatorContainer{

background-color: rgb(44, 48, 81);

}
  .row1, .row2, .row3, .row4, .row5, .calculatorScreen{
      display: flex;
      align-items:center;
      justify-content: center;
  }
</style>

<script setup>

/// The backgroundColor of each button is: rgb(55, 60, 103);
</script>