<template>
  <div id="app">
    <Login />
    <LifeCycle />
    <Todo />
    <Parent />
    <SwitchComponent />
    <VSlot />
  </div>
</template>

<script>
import Login from "./Login";
import LifeCycle from "./Lifecycle";
import Todo from "./todo/Todo";
import Parent from "./Emit/Parent";
import SwitchComponent from "./switch/SwitchComponent";
import VSlot from "./slot/VSlot";

export default {
  components: {
    Login,
    LifeCycle,
    Todo,
    Parent,
    SwitchComponent,
    VSlot
  },
  data: () => {
    return {};
  },
  methods: {},
  computed: {}
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
li {
  list-style: none;
}
#app {
  display: flex;
  justify-content: space-evenly;
  margin: 10px;
  flex-wrap: wrap;
}
#app > * {
  border: 2px solid pink;
  width: 30%;
  min-height: 30vh;
  margin-bottom: 15px;
}
</style>
