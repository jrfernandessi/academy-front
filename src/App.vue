<template>
  <div id="app">
    <h1>Nome: </h1>
    <input v-model="student.name" />
    <button @click="saveData()">Salvar</button>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      student:{
        name: null
      }
    }
  },
  methods: {
    saveData(){
      this.$http.post('students', this.student)
      console.log("salvar "+this.student.name)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
