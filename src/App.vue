<template>
  <div id="app">
    <Todos v-bind:todos="todos" />
  </div>
</template>

<script lang="ts">

import { Component, Vue } from 'vue-property-decorator';
import Todos from './components/Todos.vue';

@Component({
  name: 'app',
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'The default behavior of v-for will try to patch the elements in-place without moving them',
          completed: false,
        },
        {
          id: 2,
          title: 'The detailed usage for v-for is explained in the guide section linked below.',
          completed: true,
        },
        {
          id: 3,
          title: '<div v-for="item in items" :key="item.id">',
          completed: false,
        }
      ]
    }
  }
})
export default class App extends Vue {}
</script>

<style>
* {
  padding: 0;
  margin: 0;
  outline: 0;
  box-sizing: border-box;
}

body {
  background: #287150;
  height: 100%;
  width: 100%;
  max-height: 100vh;
  max-width: 100vw;
  color: #eef9f4;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
}
</style>
