<template>
  <teleport to="body">
    <!-- <div ref="menuEle" v-show="menuOpen" class="menu border-2 border-red-500">
      <div v-for="item in menuData" :key="item.label">
        <h1>{{ item.label }}</h1>
      </div>
    </div> -->
    <MenuItem
      v-for="item in menuData"
      :key="item.label"
      :node="item"
      :anchorEle="anchorEle"
      :open="menuOpen"
    />
  </teleport>
</template>

<script>
import { ref, watchEffect } from "vue";

import MenuItem from "./MenuItem.vue";

const data = [
  {
    label: "Haha",
  },
  {
    label: "Haha",
  },
  {
    label: "Haha",
  },
];

export default {
  components: {
    MenuItem,
  },
  name: "Menu",
  props: {
    anchorEle: {
      type: HTMLButtonElement,
      required: true,
    },
  },
  setup(props, ctx) {
    const menuData = ref(data);
    const menuOpen = ref(false);

    watchEffect(() => {
      if (props.anchorEle) {
        props.anchorEle.addEventListener("click", () => {
          menuOpen.value = !menuOpen.value;
        });
      }
    });

    return { menuOpen, menuData, anchorEle: props.anchorEle };
  },
};
</script>
