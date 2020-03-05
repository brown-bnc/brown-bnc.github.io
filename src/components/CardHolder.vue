<template>
  <div class="cardholder">
    <h1>{{title}}</h1>
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
    resources: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cardholder {
  margin-top: 30px;
}
h1 {
  width: 50%;
  margin: auto;
  text-align: left;
  color: #A95659; /*#713E58;*/
}
</style>
