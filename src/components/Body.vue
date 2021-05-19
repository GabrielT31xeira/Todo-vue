<template>
  <form class="mt-5 grid justify-items-center" @submit.prevent="addTodo(todo)">
    <div class="">
      <input
        type="text"
        class="w-60 border-2 border-green-500 rounded-md"
        v-model="todo.description"
        placeholder="Novo Todo"
      />
      <button
        class="ml-3 bg-green-500 hover:bg-green-900 duration-150 delay-75 rounded-md p-0.5 px-2 appearance-none"
      >
        Adcionar
      </button>
    </div>
  </form>
  <Todo
    class="mt-10 grid justify-items-center"
    v-for="t in todos"
    :key="t.id"
    @toggle="toggleTodo"
    @remove="removeTodo"
    :todo="t"
  />
</template>

<script>
import Todo from "./List";

export default {
  name: "body",
  components: {
    Todo,
  },
  data() {
    return { todos: [], todo: { checked: false } };
  },
  methods: {
    addTodo(todo) {
      todo.id = Date.now();
      this.todos.push(todo);
      this.todo = { checked: false };
    },
    toggleTodo(todo) {
      const index = this.todos.findIndex(item => item.id === todo.id);
      if (index > -1) {
        const checked = !this.todos[index].checked;
        this.todos[index].checked = checked;
      }
    },

    removeTodo: function(todo) {
      this.todos.splice(todo, 1)
    },
  },
};
</script>


