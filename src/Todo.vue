<template>
  <div class="todo">
    <h1>Todos</h1>
    <form @submit.prevent="addTodo">
      <input class="addtodo" type="text" v-model="newTodo" placeholder="What needs to be done?" />
    </form>
    <ul>
      <li v-for="(item,index) in list" :key="index" :class="{completed: item.completed}">
        <input class="toggle" type="checkbox" v-model="item.completed" @click="complete" />
        <p>{{item.text}}</p>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
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
    },
    complete: function() {
      console.log(this.list);
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
.todo ul {
  margin: 10px;
  margin-top: 0px;
  width: 80%;
}
.todo li {
  line-height: 2.5em;
  border-top: 1px solid #eee;
}
.todo .completed {
  color: #ccc;
}
.todo p {
  display: inline;
  margin-left: 5px;
}
.todo li:last-child {
  border-bottom: 1px solid #eee;
}
.todo .toggle {
  position: relative;
  top: 2px;
}

.todo form {
  width: 80%;
}
.todo .addtodo {
  width: 100%;
  padding-left: 15px;
  height: 2.5em;
}
</style>