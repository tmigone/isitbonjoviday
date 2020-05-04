<template>
  <div id="app">
    <div v-if="mayTheFourth">
      <h1>May the Force be with you!</h1>
      <img alt="Vue logo" src="./assets/may.jpg" />
    </div>
    <div v-if="!mayTheFourth">
      <h1>Sadly no :(</h1>
      <img alt="Vue logo" src="./assets/sad.jpeg" />
    </div>
  </div>
</template>

<script>

export default {
  name: 'app',
  data () {
    return {
      mayTheFourth: false
    }
  },
  mounted () {
    this.mayTheFourth = new Date().getMonth() === 4 && new Date().getDate() === 4
    console.log(`Is it May the Fourth?: ${this.mayTheFourth}`)
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
