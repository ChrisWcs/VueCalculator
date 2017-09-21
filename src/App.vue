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
        <button class="Button" >-</button>
      </div>
      <div class="FlexRow">
        <button class="Button" @click="numberPress(1)">1</button>
        <button class="Button" @click="numberPress(2)">2</button>
        <button class="Button" @click="numberPress(3)">3</button>
        <button class="Button">_</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      number: 0,
      total: 0
    }
  },
  methods: {
    numberPress (temp) {
      this.number = temp
    },
    add () {
      this.total += this.number
      this.number = 0
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
