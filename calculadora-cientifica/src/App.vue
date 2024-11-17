<template>
  <div id="app">
    <h1>Calculadora Científica</h1>
    <div class="calculator">
      <input type="text" v-model="display" disabled />
      <div class="buttons">
        <button @click="clear">C</button>
        <button @click="append('(')">(</button>
        <button @click="append(')')">)</button>
        <button @click="append('/')">/</button>
        <button @click="append('7')">7</button>
        <button @click="append('8')">8</button>
        <button @click="append('9')">9</button>
        <button @click="append('*')">*</button>
        <button @click="append('4')">4</button>
        <button @click="append('5')">5</button>
        <button @click="append('6')">6</button>
        <button @click="append('-')">-</button>
        <button @click="append('1')">1</button>
        <button @click="append('2')">2</button>
        <button @click="append('3')">3</button>
        <button @click="append('+')">+</button>
        <button @click="append('0')">0</button>
        <button @click="append('.')">.</button>
        <button @click="calculate">=</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      display: ''
    };
  },
  methods: {
    append(character) {
      this.display += character;
    },
    clear() {
      this.display = '';
    },
    calculate() {
      try {
        this.display = eval(this.display);
      } catch (e) {
        this.display = 'Error';
      }
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}

.calculator {
  display: inline-block;
  text-align: left;
}

input {
  width: 100%;
  height: 40px;
  font-size: 24px;
  text-align: right;
  margin-bottom: 10px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  height: 40px;
  font-size: 18px;
}
</style>
