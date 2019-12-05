<template>
  <div class="posts-tab">
    <ul class="posts-sidebar">
      <li
        v-for="post in posts"
        :key="post.id"
        :class="{ selected: post === selectedPost }"
        @click="selectedPost = post"
      >{{ post.title }}</li>
    </ul>
    <div class="selected-post-container">
      <div v-if="selectedPost" class="selected-post">
        <h3>{{ selectedPost.title }}</h3>
        <div v-html="selectedPost.content"></div>
      </div>
      <strong v-else>Click on a blog title to the left to view it.</strong>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      selectedPost: null,
      posts: [
        {
          id: 1,
          title: "动态组件",
          content:
            "<p>我们之前曾经在一个多标签的界面中使用 is 特性来切换不同的组件。当在这些组件之间切换的时候，你有时会想保持这些组件的状态，以避免反复重渲染导致的性能问题。</p>"
        },
        {
          id: 2,
          title: "异步组件",
          content:
            "<p>在大型应用中，我们可能需要将应用分割成小一些的代码块，并且只在需要的时候才从服务器加载一个模块。为了简化，Vue 允许你以一个工厂函数的方式定义你的组件，这个工厂函数会异步解析你的组件定义。Vue 只有在这个组件需要被渲染的时候才会触发该工厂函数，且会把结果缓存起来供未来重渲染。</p>"
        }
      ]
    };
  }
};
</script>
<style>
.posts-tab {
  display: flex;
}
.posts-sidebar {
  padding-right: 10px;
  border-right: 1px solid #ccc;
}
.posts-sidebar li {
  white-space: nowrap;
  cursor: pointer;
  border-bottom: 3px solid transparent;
  margin-bottom: 5px;
}
.posts-sidebar li:hover {
  border-color: pink;
}
.posts-sidebar li.selected {
  color: pink;
  font-weight: bolder;
}
.selected-post-container {
  padding-left: 10px;
}
</style>