<template>
  <div class="card">
    <a :href="resource.url" v-if="resource.url">
      <h1>{{ resource.name }}</h1>
    </a>
    <a :href="resource.repo" v-else-if="resource.repo">
      <h1>{{ resource.name }}</h1>
    </a>
    <p>{{ resource.description }}</p>
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
.card {
  display: inline-block;
  max-width: 20%;
  min-width: 200px;
  padding: 20px;
  vertical-align: top;
}

a {
  text-decoration: none;
}

h1 {
  border-bottom: 1px solid black;
}

p {
  padding-top: 10px;
}
</style>
