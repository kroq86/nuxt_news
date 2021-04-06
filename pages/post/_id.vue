<template>
  <section>
    <div class="hidden">
      <h2>{{ $route.params.id }}</h2>
    </div>
    <h3>{{ post.title }}</h3>
    <a> {{ post.body }}</a>
  </section>
</template>

<script>
export default {
  layout: "default",
  data() {
    return {
      count: this.$route.params.id,
      post: [],
    };
  },
  async fetch() {
    this.post = await fetch(
      `https://jsonplaceholder.typicode.com/posts/${this.count}`
    ).then((res) => res.json());
  },
};
</script>

<style scoped>
.hidden {
  visibility: hidden;
}
</style>