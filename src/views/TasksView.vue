<template>
  <div class="about">
    <v-container>
      <h1 class="title mb-5">Список задач</h1>
      <v-app>
        <v-flex xs12 sm6 offset-sm3>
          <v-card>
            <v-card-title primary-title class="title"> </v-card-title>
            <v-card-text>
              <TodoItem
                v-for="(todo, index) in todos"
                :key="index"
                :todo="todo"
              >
              </TodoItem>
              <InputField ref="inputFeild"></InputField>
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="success" @click="addTodo">Добавить в список</v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-app>
    </v-container>
  </div>
</template>


<script>
import TodoItem from "../components/TodoItem";
import InputField from "../components/InputField";

export default {
  name: "App",
  components: {
    TodoItem,
    InputField,
  },
  data() {
    return {};
  },
  computed: {
    todos() {
      return this.$store.state.todos;
    },
  },
  methods: {
    addTodo() {
      this.$refs.inputFeild.addTodo();
    },
  },
};
</script>

<style>
.title {
  display: flex;
  justify-content: center;
}
</style>
