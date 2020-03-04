<template>
  <div id="app">
    <Header title="Brown Neuroimaging Core: Resources"/>
    <CardHolder :resources="resources"></CardHolder>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import CardHolder from './components/CardHolder.vue'

export var resourceData = [{id: 1, name: "card1", url: "#"}, {id: 2, name: "card2", url: "#"}]

export default {
  name: 'App',
  components: {
    Header,
    CardHolder
  },
  data() {
    return {
      resources: resourceData
    }
  },
}

</script>

<style>
* {
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
