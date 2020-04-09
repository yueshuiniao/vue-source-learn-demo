<template>
  <div>
    <div>Watcher</div>
    <div>{{ info }}</div>
    <button @click="setAge">调用setAge</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data() {
    return {
      age: 0,
      name: 'dexter',
    }
  },
  beforeUpdate() {
    console.log('beforeUpdate this.age=' + this.age)
  },
  updated() {
    console.log('updated this.age=' + this.age)
  },
  computed: {
    info() {
      return this.name + '-' + this.age
    },
  },
  methods: {
    setAge() {
      this.age++
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
button {
  margin-right: 10px;
}
</style>
