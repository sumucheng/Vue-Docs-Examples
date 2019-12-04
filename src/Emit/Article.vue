<template>
  <div class="component">
    <h3>{{ post.title }}</h3>
    <div class="buttons">
      <button v-on:click="$emit('addFontSize',0.05)">+</button>
      <button v-on:click="$emit('minusFontSize',0.05)">-</button>
    </div>
    <div>{{post.content}}</div>
  </div>
</template>
<script>
export default {
  props: ["post"],
  data: () => {
    return {
      count: 0
    };
  },
  methods: {}
};
</script>
<style >
.component {
  border: 1px solid #ccc;
  position: relative;
  padding: 5px;
}
.component .buttons {
  position: absolute;
  right: 0;
  bottom: 0;
}
.component .buttons button {
  width: 1.5em;
  height: 1.5em;
}
</style>