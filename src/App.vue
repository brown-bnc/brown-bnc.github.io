<template>
  <div id="app">
    <Header title="Brown Neuroimaging Core: Resources"/>
    <CardHolder :resources="resources"></CardHolder>
    <p>{{resources}}</p>
  </div>
</template>

<script>
import axios from 'axios'
import yaml from 'js-yaml'
import Header from './components/Header.vue'
import CardHolder from './components/CardHolder.vue'

export default {
  name: 'App',
  components: {
    Header,
    CardHolder
  },
  data() {
    return {
      resources: []
    }
  },
  mounted() {
    // grab contents from each of the yaml files in bnc-resource-registry
    axios
      .get('https://api.github.com/repos/brown-bnc/bnc-resource-registry/contents')
      .then(response => {
        let allFiles = response.data;
        for (let i = 0; i < allFiles.length; i++) {
          let currentFilePath = allFiles[i].path;
          let splitPath = currentFilePath.split('.');
          let extension = splitPath[splitPath.length - 1];

          if (extension === "yaml") {
            axios
              .get('https://api.github.com/repos/brown-bnc/bnc-resource-registry/contents/' + currentFilePath)
              .then(detailedResponse => {
                let yamlContent = yaml.safeLoad(atob(detailedResponse.data.content));
                yamlContent["id"] = i;
                this.resources.push(yamlContent);
              })
          }
        }
      })
  }
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
