<template>
<div class="wraper">
  
    
    <div class="all" v-for="post of posts" :key="post.id"> 
      <h3 class="title" href="#" @click="openPost(post.id)">
        <b-avatar :src="'auth/'+`${post.userId}`+'.jpg'"></b-avatar> 
        {{ post.title }}  </h3>
        
      <p class="items-text"> {{ post.body }}</p>
      <b-img rounded="circle" :src="'img/'+`${post.id}`+'.png'" 
      width="400" height="300" class="img-thumbnail" alt="image"></b-img>
      
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
      openPost(id){
        this.$router.push('/post/'+ id)
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
.all {
  margin-top:20px;
  }

.items-text {
overflow: hidden;
text-overflow: ellipsis;
display: -webkit-box;
-webkit-line-clamp: 2;
-webkit-box-orient: vertical;
}

.title:hover {
  text-transform: uppercase;
}
</style>
