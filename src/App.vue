<template>
  <div id="app">
    <TodoApp v-bind:todos="todos" />
  </div>
</template>

<script>
import TodoApp from './components/TodoApp'

export default {
  name: 'App',
  components: {
    TodoApp
  },
  data() {
    return {
      todos: [
        {title: 'Todo A', desc: 'I need to do this.', done: true},
        {title: 'Todo B', desc: 'I need to do this after A.', done: true},
        {title: 'Todo C', desc: 'I need to do this later.', done: false}
      ],
    };
  },
};
</script>
