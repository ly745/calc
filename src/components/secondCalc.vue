<template>
  <div>
      {{result}}
      <br>
      {{ num1 || num2 }}
      <br>
      <button @click="del()">del</button>
      <button @click="clear()">clear</button>
      <br>
      <button @click="pick('7')">7</button>
      <button @click="pick('8')">8</button>
      <button @click="pick('9')">9</button>
      <button @click="add('+')">+</button>
      <br>
      <button @click="pick('4')">4</button>
      <button @click="pick('5')">5</button>
      <button @click="pick('6')">6</button>
      <button @click="reduce('-')">-</button>
      <br>
      <button @click="pick('1')">1</button>
      <button @click="pick('2')">2</button>
      <button @click="pick('3')">3</button>
      <button @click="pick('*')">*</button>
      <br>
      <button @click="pick('0')">0</button>
      <button @click="pick('.')">.</button>
      <button @click="calc()">=</button>
      <button @click="pick('/')">/</button>
      <br>
  </div>
</template>
<script>
export default {
  name: 'APP',
  data () {
    return {
        num1: '',
        num2: '',
        result: '',
        fh: ''
    }
  },
  methods: {
    pick (num1) {
        this.num1 = num1
        this.result += num1
    },
    add (add) {
        this.fh = '+'
        this.num1 = add
        this.result += add
    },
    calc () {

    },
    clear () {
        this.num1 = 0
        this.num2 = 0
        this.result = 0
    }
  },
  created () {
  },
  mounted () {
  },
}
</script>
<style scoped>
button{
    width: 50px;
    height: 50px;
    border: 1px solid black;
    text-align: center;
    border-radius: 5px;
}
</style>
