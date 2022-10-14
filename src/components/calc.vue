<template>
  <div>
      {{result}}
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
        num2: null,
        result: ''
    }
  },
  methods: {
    pick (num) {
        this.result += num
        // console.log(num)
    },
    add (add) {
        this.result += add
        if (this.result.split('+').length-1 !== 1) {
            console.log('第二次');
            this.result = this.result.substring(0,this.result.length-1)
            this.calc()
            this.result += '+'
        }
    },
    reduce (reduce) {
        this.result += reduce
        if (this.result.split('-').length-1 !== 1) {
            console.log('第二次');
            this.result = this.result.substring(0,this.result.length-1)
            this.calc()
            this.result += '-'
        }
    },
    clear () {
        this.result = ''
    },
    calc () {
        console.log('结果', this.result)
        // 加法
        if (this.result.indexOf('+') > 0) {
            const num1 = this.result.substring(0,this.result.indexOf('+'))
            const num2 = this.result.substring(this.result.indexOf('+')+1, this.result.length)
            console.log('num1', num1, 'num2', num2)
            const num3 = Number(num1) + Number(num2)
            // console.log('num3',num3);
            this.result = num3
        } else if (this.result.indexOf('-') > 0) {
            // 减法
            const num1 = this.result.substring(0,this.result.indexOf('-'))
            const num2 = this.result.substring(this.result.indexOf('-')+1, this.result.length)
            console.log('num1', num1, 'num2', num2)
            const num3 = Number(num1) - Number(num2)
            // console.log('num3',num3);
            this.result = num3
        }
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
