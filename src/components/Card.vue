<template>
  <div class="card">
    <font-awesome-icon v-if="resource.category == 'Web Portal'"
                       :icon="['fas', 'chalkboard-teacher']" size="3x" class="card-icon"/>
    <font-awesome-icon v-else-if="resource.category == 'Documentation'"
                       :icon="['fas', 'book']" size="3x" class="card-icon"/>
    <font-awesome-icon v-else :icon="['fas', 'tools']" size="3x" class="card-icon"/>
    <div class="card-info">
      <h1 v-if="resource.url"><a :href="resource.url">{{ resource.name }}</a></h1>
      <h1 v-else-if="resource.repo"><a :href="resource.repo">{{ resource.name }}</a></h1>
      <p>{{ resource.description }}</p>
    </div>
    <a :href="resource.url" v-if="resource.url" class="resource-go">
      <font-awesome-icon :icon="['fas', 'arrow-right']" size="lg"/>
    </a>
    <a :href="resource.repo" v-else-if="resource.repo" class="resource-go">
      <font-awesome-icon :icon="['fas', 'arrow-right']" size="lg"/>
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
.card {
  display: inline-block;
  position: relative;
  width: 50%;
  min-width: 200px;
  margin: 8px;
  padding: 30px 20px 5px 40px;
  vertical-align: top;
  background-color: rgba(78, 54, 41, 0.9);/*#4E3629;*/
  color: white;
  min-height: 100px;
  text-align: left;

  -moz-box-shadow: 0px 0px 2px 0px  #98A4AE;
   -webkit-box-shadow: 0px 0px 2px 0px  #98A4AE;
    box-shadow: 0px 0px 2px 0px  #98A4AE;
}

a {
  color: white;
  text-decoration: none;
}

p {
  padding-top: 5px;
}

.card-icon {
  width: 50px;
  display: inline-block;
  padding: 0px 30px 8px 0px;
  color: white;
}
.card-info {
  display: inline-block;
  margin-bottom: 40px;
}

.resource-go {
  position: absolute;
  right: 30px;
  bottom: 20px;
  font-weight: bold;
}
.resource-go:hover {
  color: #FFC72C;
}
</style>
