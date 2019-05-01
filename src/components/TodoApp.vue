<template>
  <div>
    <div v-for="todo in todos">
      {{ todo.title }}
    </div>
  </div>
</template>


<script>
  export default {
    props: ['todos'],
  };
</script>
