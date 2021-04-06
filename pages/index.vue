<template>
  <div id="app"
    class="max-w-md mx-auto bg-white rounded-xl shadow-md overflow-hidden md:max-w-2xl"
  >
    <div class="md:flex" v-for="post of posts" :key="post.id">
      <div class="md:flex-shrink-0">
        <img
          class="h-48 w-full object-cover md:w-48"
          :src="'img/' + `${post.id}` + '.png'"
          alt="Man looking at item at a store"
        />
      </div>
      <div class="p-8">
        <a
          href="#"
          @click="openPost(post.id)"
          class="block mt-1 text-lg leading-tight font-medium text-black hover:underline"
          >{{ post.title }}</a
        >
        <p id="text-item" class="mt-2 text-gray-500">
          {{ post.body }}
          <hr>
        </p>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      posts: [],
    };
  },
  async fetch() {
    this.posts = await fetch(
      "https://jsonplaceholder.typicode.com/posts?_page=1&_limit=5"
    ).then((res) => res.json());
  },
  methods: {
    openPost(id) {
      this.$router.push("/post/" + id);
    },
  },
};
</script>

<style>
.app {
  margin-top: 20rem;
}
#text-item {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
}
</style>
