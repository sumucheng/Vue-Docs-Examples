<template>
  <div class="lifecycle">
    <div :class="{active}">{{msg}}</div>
    <div>
      <button v-on:click="reverseMessage">逆序</button>
      <button v-on:click="changeColor">改变颜色</button>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      msg: "123456789",
      active: false
    };
  },
  methods: {
    reverseMessage: function() {
      this.msg = this.msg
        .split("")
        .reverse()
        .join("");
    },
    changeColor: function() {
      this.active = !this.active;
    }
  }
  // beforeCreate: function() {
  //   console.log("beforeCreate");
  // },
  // created: function() {
  //   console.log("created");
  // },
  // beforeMount: function() {
  //   console.log("beforeMount");
  // },
  // mounted: function() {
  //   console.log("mounted");
  // },
  // beforeUpdate: function() {
  //   console.log("beforeUpdate");
  // },
  // updated: function() {
  //   console.log("updated");
  // },
  // beforeDestroy: function() {
  //   console.log("beforeDestroy");
  // },
  // destroyed: function() {
  //   console.log("destroyed");
  // }
};
</script>
<style>
.lifecycle {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.lifecycle .active {
  color: red;
}
.lifecycle button {
  margin: 10px;
}
</style>