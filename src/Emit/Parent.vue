<template>
  <div :style="{fontSize:fontSize+'em'}">
    <Article
      v-for="post in posts"
      :key="post.id"
      :post="post"
      v-on:addFontSize="addFontSize($event)"
      v-on:minusFontSize="minusFontSize($event)"
    />
  </div>
</template>
<script>
// import Custom from "./Custom";
import Article from "./Article";
export default {
  components: {
    Article
  },
  data: () => {
    return {
      posts: [
        {
          id: 1,
          title: "My journey with Vue",
          content: "Welecome to Vue world!"
        },
        {
          id: 2,
          title: "Blogging with Vue",
          content: "Welecome to Vue world!"
        },
        {
          id: 3,
          title: "Why Vue is so fun",
          content: "Welecome to Vue world! Come on!"
        }
      ],
      fontSize: 1
    };
  },
  methods: {
    addFontSize: function(e) {
      this.fontSize += e;
    },
    minusFontSize: function(e) {
      this.fontSize -= e;
    }
  }
};
</script>
<style >
</style>