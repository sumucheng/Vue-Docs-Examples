<template>
  <div class="todo">
    <h1>Todos</h1>
    <form @submit.prevent="addTodo">
      <input class="addtodo" type="text" v-model="newTodo" placeholder="What needs to be done?" />
    </form>
    <TodoEvent :list="list">
      <template #todoEvent="{ item }">
        <span v-if="item.completed">✓</span>
        <input v-else class="toggle" type="checkbox" v-model="item.completed" />
        {{ item.text }}
      </template>
    </TodoEvent>
  </div>
</template>
<script>
import TodoEvent from "./TodoEvent";
export default {
  components: {
    TodoEvent
  },
  data: () => {
    return {
      list: [],
      newTodo: ""
    };
  },
  methods: {
    addTodo: function() {
      this.list.push({ text: this.newTodo, completed: false });
      this.newTodo = "";
    }
  }
};
</script>
<style >
.todo {
  padding: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.todo h1 {
  color: rgba(175, 47, 47, 0.15);
  font-size: 50px;
  font-weight: 100;
  text-align: center;
}
.todo form {
  width: 80%;
}
.todo .addtodo {
  width: 100%;
  padding-left: 15px;
  height: 2.5em;
}
.todo span {
  display: inline-block;
  width: 12.8px;
}
</style>