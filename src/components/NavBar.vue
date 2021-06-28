<template>
  <div class="navbar">
    <div class="nav-section" id="nav-left">
      <a href="www.brown.edu">
        <img v-bind:src="logo"/>
      </a>
      <h2>Behavioral Neuroimaging Core</h2>
    </div>
    <div class="nav-section" id="nav-right">
      <ul v-for="link in links" :key="link.url">
        <li><a :href="link.url">{{ link.name }}</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NavBar',
  props: {
    logo: Object,
    links: Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navbar {
  padding: 20px 50px;
  background-color: white;
  text-align: left;
  color: black;
}

.nav-section {
  display: inline-block;
  vertical-align: middle;
}

#nav-right {
  margin-left: 25%;
  padding-top: 4px;
  font-size: 18px;
}

img {
  height: 90px;
  width: auto;
  padding-left: 20px;
  padding-right: 40px;
  border-right: 1px solid grey;
  vertical-align: middle;
}

h2 {
  display: inline-block;
  padding-left: 40px;
  vertical-align: middle;
  color: rgb(34, 34, 34);
}

ul {
  display: inline-block;
}

li {
  list-style-type: none;
}

a {
  text-decoration: none;
  color: rgb(34, 34, 34);
}

#nav-right a:hover {
  color: #ED1C24;
}

</style>
