<template>
  <div class="header">
    <h1><div id="title-left">{{ title }} </div>
        <div id="title-right">{{ section }}</div></h1>
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
  /*font-family: Georgia, serif;*/
  font-size: 42px;
  padding: 80px 0px 30px 0px;
  color: #4E3629;
  text-shadow: 0 0 5px white;
}

#title-left {
  display: inline;
}

#title-right {
  display: inline;
  border-bottom: 10px solid #FFC72C;
}
</style>
