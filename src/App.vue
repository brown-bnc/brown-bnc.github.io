<template>
  <div id="app">
    <Header title="Behavioral Neuroimaging Core:" section="Resources"/>
    <p :v-bind="resources"></p>
    <CardHolder v-for="(item, key) in separateCategories(resourcesRaw)" :key="key" :resources="item" :title="key" />
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
      resourcesRaw: []
    }
  },
  created() {
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
                this.resourcesRaw.push(yamlContent);
              })
          }
        }
      })
  },
  methods: {
    separateCategories() {
      // separate resources into categories
      let resources = {};
      for (let i = 0; i < this.resourcesRaw.length; i++) {
        let currentResource = this.resourcesRaw[i];
        if (!(currentResource.category in resources)) {
          resources[currentResource.category] = [];
        }
        resources[currentResource.category].push(currentResource);
      }
      return resources;
    }
  }
}

</script>

<style>
* {
  margin: 0;
}

body {
  padding-bottom: 100px;
  background-color: #F8F8FF;
  border-bottom: 30px solid #3E5871;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
