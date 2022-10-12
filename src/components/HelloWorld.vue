<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <table>
      <textarea rows="3" cols="20" v-model="result"></textarea>
      <br>
      <button @click="del()">del</button>
      <button @click="clear()">clear</button>
      <br>
      <button @click="pick('7')">7</button>
      <button @click="pick('8')">8</button>
      <button @click="pick('9')">9</button>
      <button @click="pick('+')">+</button>
      <br>
      <button @click="pick('4')">4</button>
      <button @click="pick('5')">5</button>
      <button @click="pick('6')">6</button>
      <button @click="pick('-')">-</button>
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
    </table>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      result: ''
    }
  },
  methods: {
    pick (num) {
      this.result += num
      console.log(num)
    },
    clear () {
      this.result = ''
    },
    del () {
      this.result = this.result.substring(0,this.result.length-1)
    },
    calc () {
      console.log(this.result)
      this.result = eval(this.result)
      // 不转字符串的化，进行del操作回报错this.result.substring is not a function
      this.result = this.result.toString()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button{
    width: 50px;
    height: 50px;
    border: 1px solid black;
    text-align: center;
    border-radius: 5px;
}
</style>
