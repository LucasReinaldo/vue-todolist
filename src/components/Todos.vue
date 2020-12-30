<template>
  <div class="todos">
    <h1 class="title">Todos!?</h1>
    <ul>
      <li
        v-for="todo in todos"
        v-bind:key="todo.id"
      >
        <TodoItem v-bind:todo="todo" />
      </li>
    </ul>
  </div>
</template>

<script lang="ts">

import { Component, Prop, Vue } from 'vue-property-decorator';
import TodoItem from './TodoItem.vue';

interface ITodos {
  id: number;
  title: string;
  completed: boolean;
}

@Component({
  name: 'Todos',
  components: {
    TodoItem,
  }
})
export default class Todos extends Vue {
  @Prop() private todos!: ITodos[];
}
</script>

<style scoped>
  div.todos {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  div h1.title {
    text-align: center;
  }

  ul li {
    list-style: none;
  }
</style>
