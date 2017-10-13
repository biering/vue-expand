<template>
  <main class="app">

    <h1>
      Vue Expand
    </h1>

    <vue-expand
      v-model="text"
      :placeholder="placeholder"
      min-row="5"
      :handler="handler"/>

  </main>
</template>

<script>
  import Vue       from 'vue'
  import VueExpand from 'vue-expand'
  
  export default {
    name: 'app',

    components: {
      VueExpand
    },

    data () {
      return {
        text: '',
        handler: new Vue(),
        placeholder: 'Type here..'
      }
    }
  }
</script>

<style scoped>
body, html {
  top: 0;
  left: 0;
  margin: 0;
  padding: 0;
}

* {
  box-sizing: border-box;
  -webkit-font-smoothing: antialiased;
}

.app {
  color: #4c4c4f;
}

h1 {
  font-family: 'Open Sans', sans-serif;
  text-align: center;
  text-transform: uppercase;
  margin: 100px 0;
}
</style>

<style>
.vue-expand {
  width: 10%;
  margin: 50px auto;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 3px;
}

.vue-expand textarea {
  font-size: 16px;
  padding: 10px;
}
</style>
