<template>
  <div id="app">
    <div class="FlexCol">
      <div>
        <h1 class="Display">{{total}}</h1>
      </div>
      <div class="FlexRow">
        <button class="Button" @click="numberPress(7)">7</button>
        <button class="Button" @click="numberPress(8)">8</button>
        <button class="Button" @click="numberPress(9)">9</button>
        <button class="Button" @click="add()">+</button>
      </div>
      <div class="FlexRow">
        <button class="Button" @click="numberPress(4)">4</button>
        <button class="Button" @click="numberPress(5)">5</button>
        <button class="Button" @click="numberPress(6)">6</button>
        <button class="Button" @click="minus()">-</button>
      </div>
      <div class="FlexRow">
        <button class="Button" @click="numberPress(1)">1</button>
        <button class="Button" @click="numberPress(2)">2</button>
        <button class="Button" @click="numberPress(3)">3</button>
        <button class="Button" @click="equal()">=</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      current2: 0,
      total: 0,
      current: 0,
      status: true,
      operator: ''
    }
  },
  methods: {
    numberPress (temp) {
      this.number = temp
      if (this.status) {
        this.current = temp
        this.status = false
      } else {
        this.current2 = temp
        this.status = true
      }
    },
    add () {
      if (this.status) {
        this.current = this.total
        this.status = !this.status
      }
      this.operator = '+'
    },
    minus () {
      if (this.status) {
        this.current = this.total
        this.status = !this.status
      }
      this.operator = '-'
    },
    equal () {
      if (this.operator === '+') {
        this.total = this.current + this.current2
      } else {
        this.total = this.current - this.current2
      }
    }
  }
}
</script>

<style>
  .Display{
    font-family: Arial;
  }

  .Button{
    border: solid black 1px;
    padding: 10px;
    background: white;
    margin: 2px;
    font-family: Arial;
    font-size: 20px;
  }

  :hover.Button{
    background: black;
    color: white;
  }

  .FlexRow{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }

  .FlexCol{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
</style>
