<template>
  <header class="bg-white shadow" v-if="$route.meta.title">
    <div class="max-w-screen-xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
      <h1 class="text-3xl font-bold leading-tight text-gray-900">
        {{ $route.meta.title }}
      </h1>
    </div>
  </header>

  <div class="max-w-screen-xl mx-auto py-6 sm:px-6 lg:px-8">
    <router-view />
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  data: () => ({
    showMenu: false,
    showProfileMenu: false,
    links: [
      { text: "Home", to: "/" },
      { text: "About", to: "/about" },
    ],
  }),
});
</script>
