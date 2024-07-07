<template>
  <v-app>
    <v-main>
      <todo-list />
    </v-main>
  </v-app>
</template>

<script>
import TodoList from './components/TodoList.vue';

export default {
  components: {
    TodoList
  }
}
</script>
