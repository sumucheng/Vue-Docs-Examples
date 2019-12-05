<template>
  <div class="switch">
    <button
      v-for="tab in tabs"
      :key="tab"
      @click="currentTab=tab"
      :class="['tabButton', { active: currentTab === tab }]"
    >{{tab}}</button>

    <transition name="component-fade" mode="out-in">
      <keep-alive>
        <component :is="currentTab" class="tab"></component>
      </keep-alive>
    </transition>
  </div>
</template>

<script>
import Page1 from "./Page1";
import Page2 from "./Page2";
import Page3 from "./Page3";
export default {
  components: {
    Page1,
    Page2,
    Page3
  },
  data: () => {
    return {
      currentTab: "Page1",
      tabs: ["Page1", "Page2", "Page3"]
    };
  }
};
</script>
<style>
.component-fade-enter-active,
.component-fade-leave-active {
  transition: opacity 0.2s ease;
}
.component-fade-enter, .component-fade-leave-to
/* .component-fade-leave-active for below version 2.1.8 */ {
  opacity: 0;
}
.switch {
  padding: 3px;
}
.switch > * {
  margin: 10px;
  margin-bottom: 0;
}
.switch .tabButton {
  background: white;
  border: 0;
  cursor: pointer;
  padding-bottom: 4px;
}
.switch .tabButton:focus {
  outline: none;
}
.switch .tabButton.active {
  border-bottom: 3px solid pink;
}
</style>