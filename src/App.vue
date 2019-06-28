<template>
  <div id="app">
    <div v-if="bonJoviDay">
      <h1>HELL YES IT IS!</h1>
      <img alt="Vue logo" src="./assets/jbj.jpg">
    </div>
    <div v-if="!bonJoviDay">
      <h1>{{ daysToFriday }} day{{ daysToFriday > 1 ? 's' : '' }} until next Bon Jovi Day.</h1>
      <img alt="Vue logo" src="./assets/sad.jpg">
    </div>
  </div>
</template>

<script>

export default {
  name: 'app',
  data () {
    return {
      bonJoviDay: false,
      daysToFriday: -1
    }
  },
  mounted () {
    this.daysToFriday = 5 - new Date().getDay()
    this.daysToFriday = this.daysToFriday < 0 ? 6 : this.daysToFriday
    this.bonJoviDay = this.daysToFriday === 0

    console.log(`Days to friday: ${this.daysToFriday}`)
    console.log(`Is it Bon Jovi day?: ${this.bonJoviDay}`)
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
