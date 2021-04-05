<template>
<div class="wraper">
  
    <h1>Posts</h1>
    <div v-for="post of posts" :key="post.id"> <h3 href="#" @click="openPost(title)">{{ post.title }}</h3>
      <a> {{ post.body }}</a>
      <hr>
    </div>
 
</div>
</template>

<script>
  export default {
    data() {
      return {
        posts: []
      }
    },
    async fetch() {
      this.posts = await fetch(
        'https://jsonplaceholder.typicode.com/posts'
      ).then(res => res.json())
    },
    methods: {
      openPost(body){
        this.$router.push('/post'+ body)
      }
    }
  }
</script>

<style>
.container {
  justify-content:space-between;
}
.wraper {
  max-width: 770px;
}

</style>
