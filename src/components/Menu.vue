<template>
  <main>
    <div class="mt-6">
      Here goes your content. You can also go the About page.
    </div>
  </main>
</template>

<script>
export default {
  name: "Menu",
  setup() {
    const sayHi = () => console.log("Hi");

    return { sayHi };
  },
};
</script>
