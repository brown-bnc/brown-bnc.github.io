<template>
  <div class="cardholder">
    <h1>{{ data }}</h1>
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
    resources: Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
