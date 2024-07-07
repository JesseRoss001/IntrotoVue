<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <v-text-field
          v-model="newTodo"
          label="New To-Do"
          @keyup.enter="addTodo"
        ></v-text-field>
        <v-btn @click="addTodo">Add</v-btn>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <v-list>
          <v-list-item
            v-for="(todo, index) in todos"
            :key="index"
          >
            <v-list-item-content>{{ todo }}</v-list-item-content>
            <v-list-item-action>
              <v-btn icon @click="removeTodo(index)">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-list-item-action>
          </v-list-item>
        </v-list>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      newTodo: '',
      todos: []
    }
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() !== '') {
        this.todos.push(this.newTodo.trim())
        this.newTodo = ''
      }
    },
    removeTodo(index) {
      this.todos.splice(index, 1)
    }
  }
}
</script>
