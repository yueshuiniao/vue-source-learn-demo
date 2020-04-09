<template>
  <div>
    <div>{{ age }}</div>
    <button @click="setAge">调用setAge</button>
    <button @click="setAge1">调用setAge1</button>
    <button @click="setAge2">调用setAge2</button>
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
    }
  },
  beforeUpdate() {
    console.log('beforeUpdate this.age=' + this.age)
  },
  updated() {
    console.log('updated this.age=' + this.age)
  },
  methods: {
    setAge() {
      this.age = 1
      this.age = 2
    },
    setAge1() {
      this.$nextTick(() => {
        this.age = 3
      })
      this.age = 2
      // this.age = 3
      this.$nextTick(() => {
        this.age = 4
      })
    },

    setAge2() {
      this.$nextTick(() => {
        this.age = 10
      })
      this.age = 20
      this.$nextTick(() => {
        this.age = 30
      })
      this.age = 40
      this.age = 50
      this.$nextTick(() => {
        this.age = 60
      })
      this.age = 70
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
