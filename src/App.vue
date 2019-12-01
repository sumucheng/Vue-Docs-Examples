<template>
  <div id="app">
    <div>
      <p>{{msg}}</p>
      <button v-on:click="reverse">反转</button>
    </div>
    <div>
      <span v-bind:title="title">鼠标悬停几秒钟查看此处动态绑定的提示信息！</span>
    </div>
    <div>
      <p v-if="seen">now you can see me</p>
    </div>
    <div>
      <ol>
        <li v-for="(todo,index) in todos" :key="index">{{ todo.text }}</li>
      </ol>
    </div>
    <div>
      <p>{{input}}</p>
      <input v-model="input" />
    </div>
    <div>
      <ol></ol>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      msg: "Welcome to Vue World",
      title: "ok",
      seen: true,
      input: "1",
      todos: [{ text: "1" }, { text: "2" }, { text: "3" }]
    };
  },
  methods: {
    reverse() {
      this.msg = this.msg
        .split("")
        .reverse()
        .join("");
    }
  }
};
</script>

<style>
#app {
}
</style>
