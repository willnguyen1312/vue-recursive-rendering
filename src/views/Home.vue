<template>
  <main>
    <Menu ref="menu" />
  </main>
</template>

<script>
import { ref, onMounted } from "vue";
import Menu from "../components/Menu.vue";

export default {
  name: "Home",
  components: {
    Menu,
  },
};
</script>
