<template>
  <div class="header">
    <h1><div id="title-left">{{ title }}</div> {{ section }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    title: String,
    section: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  margin: 10px;
}

h1 {
  font-size: 48px;
  padding: 80px 0px 20px 0px;
  color: #A95659; /*#2c3e50;*/
}

#title-left {
  color: #3E5871;
  display: inline;
}
</style>
