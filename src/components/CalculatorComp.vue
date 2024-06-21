<template>

  <div class="heading">
    <h1>Calculator</h1>
  </div>

  <div class="calculatorContainer">
  
    <div class="calculatorScreen">
      <p>{{ userInput }}</p>
    </div>
  
    <div class="keyboard">

      <div class="key number" @click="clickingNumbers('7')">7</div>
      <div class="key number" @click="clickingNumbers('8')"> 8 </div>
      <div class="key number" @click="clickingNumbers('9')">9</div>
      <div class="key operator" @click="clickingOperators('/')">/</div>

      <div class="key number" @click="clickingNumbers('4')">4</div>
      <div class="key number" @click="clickingNumbers('5')">5</div>
      <div class="key number" @click="clickingNumbers('6')">6</div>
      <div class="key operator" @click="clickingOperators('*')">×</div>

      <div class="key number" @click="clickingNumbers('1')">1</div>
      <div class="key number" @click="clickingNumbers('2')">2</div>
      <div class="key number" @click="clickingNumbers('3')">3</div>
      <div class="key operator" @click="clickingOperators('-')">-</div>


      <div class="key number number-empty"></div>
      <div class="key number" @click="clickingNumbers('0')">0</div>
      <div class="key number" @click="clickingNumbers('.')">.</div>
      <div class="key operator" @click="clickingOperators('+')">+</div>

    </div>
      
    <div class="controls">
      <div class="key buttonCE" @click="ceScreen('ce')">CE</div>
      <div class="key buttonequal" @click="makingEqual('=')">=</div>
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
  font-size: 20px;
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
import { ref } from 'vue';


let userInput= ref('0');


//Make a function for the numbers

const clickingNumbers = (num) => {


  if(userInput.value==='0'){
    userInput.value = num;
  } else{
    userInput.value += num;
  }
};

//Make a function for our operators

const clickingOperators = (op) => {
  if(userInput.value === '0'){
    userInput.value = '0';
  }else{
    userInput.value += op
  }
};

//Equal function, wich make my operations

const makingEqual = (eq) => {

  try{
    userInput.value= eval(userInput.value)
  } catch(error){
    userInput.value= 'Error';
  }

};

//CE function, wich delete my userInput.value content;

const ceScreen = (ce) => {
 userInput.value= '0'
};







///write a function wich regulate the operators





</script>



