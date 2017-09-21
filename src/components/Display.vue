<template>
    <h1>{{count}}</h1>
</template>

<script>
export default {
  props: ['data'],
  data () {
    return {
      count: this.data
    }
  }
}
</script>

<style scoped>

</style>

