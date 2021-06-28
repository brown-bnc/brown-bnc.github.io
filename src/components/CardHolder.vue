<template>
  <div class="cardholder">
    <h1 v-if="title">{{title}}</h1>
    <Card v-for="item in resources" :key="item.id" :resource="item"></Card>
  </div>
</template>

<script>
import Card from '../components/Card.vue'

export default {
  name: 'CardHolder',
  components: {
    Card
  },
  props: {
    title: String,
    resources: Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cardholder {
  margin-top: 20px;
}
h1 {
  width: 54%;
  margin: auto;
  text-align: left;
  color: #4E3629;
}
</style>
