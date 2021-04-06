<template>
  <div>
    <navBar />

    <main>
      <div class="container">
        <Nuxt />
      </div>
    </main>
  </div>
</template>

<script>
import navBar from "@/components/navBar";

export default {
  components: {
    navBar,
  },
};
</script>

<style>
/* .container {
  max-width: 700px;
} */
</style>
