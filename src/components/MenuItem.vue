<template>
  <div v-show="open" ref="menuEle" class="v-menu border-2 border-red-500">
    <!-- <div v-for="item in node" :key="item.label"> -->
    <h1>{{ node.label }}</h1>
    <!-- </div> -->
  </div>
</template>

<script>
import { ref, watchEffect } from "vue";

const toPixel = (number) => `${number}px`;

export default {
  name: "MenuItem",
  props: {
    node: Object,
    anchorEle: Object,
    open: Boolean,
  },
  setup(props, ctx) {
    const menuEle = ref(null);

    watchEffect(() => {
      if (menuEle.value && props.anchorEle) {
        const {
          top: anchorTop,
          left: anchorLeft,
          width: anchorWidth,
        } = anchorEle.getBoundingClientRect();

        const menu = menuEle.value;
        menu.style.left = toPixel(anchorLeft + anchorWidth);
        menu.style.top = toPixel(anchorTop);
      }
    });

    return { menuEle, node: props.node, open: props.open };
  },
};
</script>

<style>
.v-menu {
  position: fixed;
}
</style>
