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
        {title: 'Todo A', desc: 'I need to do this.', isDone: false},
        {title: 'Todo B', desc: 'I need to do this after A.', isDone: false},
        {title: 'Todo C', desc: 'I need to do this later.', isDone: false}
      ],
    };
  },
};
</script>
