<template>
  <div id="app">
    
    <div class="card">
        <div class="card-content">
    <div class="media">
      <div class="media-left">
        <figure class="image is-64x64">
          <img class="is-rounded" src="https://bulma.io/images/placeholders/96x96.png" alt="Placeholder image">
        </figure>
      </div>
      <div class="media-content">
        <p class="title is-4">{{name}}</p>
        <p class="subtitle is-6">{{idade}}{{city}}</p>
        
      </div>
    </div>

    <div class="content">
        {{description}}
    </div>
    <div class="data">
        <span class="tag is-dark">HTML</span>
    </div>
  </div>
    </div>
  </div>
</template>

<script>
import { serverRealTimeValues } from "./utils/register.js";

export default {
  name: "App",
  data() {
    return {
      server: null,
      name: "Felipe Spigoti",
      idade: "26 anos, ",
      city: "Balneário Camboriú, SC",
      description: "Estudante de Ciência da Computação na UNIVALI",
    
    };
  },
  created() {
    serverRealTimeValues(value => {
      this.server = value;
    });
  }
};
</script>

<style>
html,
body,
iframe,
#app {
  height: 100%;
  overflow: hidden;
}

</style>
