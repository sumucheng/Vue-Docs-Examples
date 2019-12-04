<template>
  <div class="container" :class="color">
    <header>
      <slot name="header"></slot>
    </header>
    <main>
      <slot :defaultMain="defaultMain">hello</slot>
    </main>
    <footer>
      <slot name="footer"></slot>
    </footer>
  </div>
</template>
<script>
export default {
  props: ["color"],
  data: () => {
    return {
      defaultMain: "A paragraph for the main content."
    };
  }
};
</script>
<style >
.container {
  position: relative;
}
.container header {
  text-align: center;
  font-size: 30px;
  padding-top: 10px;
}
.container main {
  margin: 15px;
  color: black;
}
.container footer {
  position: absolute;
  bottom: 0;
  text-align: center;
  width: 100%;
}
.pink {
  color: pink;
}
</style>