<template>
  <ul class="todoEvent">
    <li v-for="(item,index) in list" :key="index" :class="{completed: item.completed}">
      <slot name="todoEvent" :item="item"></slot>
    </li>
  </ul>
</template>
<script>
export default {
  props: ["list"]
};
</script>
<style >
.todoEvent {
  margin: 10px;
  margin-top: 0px;
  width: 80%;
}
.todoEvent li {
  line-height: 2.5em;
  border-top: 1px solid #eee;
}
.todoEvent li:last-child {
  border-bottom: 1px solid #eee;
}
.todoEvent .completed {
  color: #ccc;
}
</style>