<template>
  <main>
    <div class="mt-6">
      <button
        class="w-40 outline-none"
        @click="menuOpen = !menuOpen"
        ref="anchorEle"
      >
        {{ `${menuOpen ? "Close" : "Open"} menu` }}
        <Menu :anchorEle="anchorEle" />
      </button>
    </div>
  </main>
</template>

<script>
import { ref } from "vue";

import Menu from "../components/Menu.vue";

export default {
  name: "Home",
  components: {
    Menu,
  },
  setup() {
    const menuOpen = ref(false);
    const anchorEle = ref(null);

    return { menuOpen, anchorEle };
  },
};
</script>
