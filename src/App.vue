<template>
  <div id="app">
    <img src="./assets/logo.png">
    <hello></hello>
    <display :data="count"/>
    <count-button increase="incre"/>
  </div>
</template>

<script>
import Hello from './components/Hello'
import Display from './components/Display'
import CountButton from './components/CountButton'

export default {
  name: 'app',
  components: {
    Hello,
    Display,
    CountButton
  },
  data () {
    return {
      count: 0
    }
  },
  methods: {
    incre: function () {
      this.count = this.count + 1
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
