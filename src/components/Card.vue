<template>
  <div class="card">
    <a :href="resource.url">
      <h1>{{ resource.name }}</h1>
    </a>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    resource: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
