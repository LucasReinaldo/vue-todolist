<template>
  <div class="todo-item">
    <div>
      <input type="checkbox" v-on:change="handleComplete"/>
      <p v-bind:class="{'is-completed':todo.completed}">{{ todo.title }}</p>
    </div>
    <button class="del" type="submit">X</button>
  </div>
</template>

<script lang="ts">

import { Component, Vue } from 'vue-property-decorator';

@Component({
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    handleComplete: () => {
     return this.todo.completed = !this.todo.completed;
    }
  }
})

export default class Todos extends Vue {}

</script>

<style scoped>
  .todo-item {
    align-items: center;
    background: #338e64;
    border-radius: 4px;
    display: inline-flex;
    margin: 6px;
    max-width: 500px;
    padding: 12px;
    width: 100%;
    font-weight: bold;
    justify-content: space-between;
  }

  div.todo-item div {
    display: inline-flex;
    align-items: center;
  }

  div p {
    margin: 0 8px;
  }

  .is-completed {
    text-decoration: line-through;
  }

  .del {
    background: #b94842;
    border: none;
    padding: 6px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
    color: whitesmoke;
  }
</style>
