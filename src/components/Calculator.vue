<template>
    <div>
        <h1>Calculator</h1>
     <div class="calc-display">
       <input class="calc-input" v-model.number="operand1"/>
       <p class="calc-func">{{ operator }}</p>
       <input class="calc-input" v-model.number="operand2"/>
       <p class="calc-func">=</p>
       <p class="calc-result">{{ result }}</p>
     </div>
     <div class="keyboard">
        <button @click="addition">+</button>
        <button @click="subtraction">-</button>
        <button @click="division">/</button>
        <button @click="multiplication">*</button>
        <button @click="exponentiation">^</button>
        <button @click="wholeDivision">//</button>
        <button @click="remainder">%</button>
     </div>
  </div>
</template>

<script>
export default {
  name: 'Calculator',
  data: () => ({
    operand1: null,
    operand2: null,
    result: 0,
    operator: '',
  }),
  methods: {
    addition() {
      this.result = this.operand1 + this.operand2;
      this.operator='+';
    },
    subtraction() {
      this.result = this.operand1 - this.operand2;
      this.operator='-';
    },
    division() {
      this.result = this.operand1 / this.operand2;
      this.operator='/';
    },
    multiplication() {
      this.result = this.operand1 * this.operand2;
      this.operator='*';
    },
    exponentiation() {
      this.result = Math.pow(this.operand1, this.operand2);
      this.operator='^';
    },
    wholeDivision() {
      this.result = (this.operand1 - this.operand1 % this.operand2) / this.operand2;
      this.operator='//';
    },
    remainder() {
      this.result = this.operand1 % this.operand2;
      this.operator='%';
    }
  },
}
</script>