<template>
  <div>
    <input :value="value" @input="$emit('input', $event.target.value)" />
    <div>{{value}}</div>
  </div>
</template>
<script>
export default {
  props: ["value"],
  data: () => {
    return {
      count: 0
    };
  },
  methods: {}
};
</script>
<style >
</style>