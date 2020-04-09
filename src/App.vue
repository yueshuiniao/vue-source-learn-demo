<template>
  <div id="app">
    <LearnNextTick msg="Welcome to Your Vue.js App" />
    <LearnWatcher />
  </div>
</template>

<script>
import LearnNextTick from './components/LearnNextTick'
import LearnWatcher from './components/LearnWatcher'

export default {
  name: 'App',
  components: {
    LearnNextTick,
    LearnWatcher,
  },
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
