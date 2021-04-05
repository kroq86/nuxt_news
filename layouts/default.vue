<template>
  <div>
   <navBar/>

  <main>
    <div class="container">
      <Nuxt />
    
    </div>
    </main>
    
  </div>
</template>

<script>
import navBar from '@/components/navBar'
import Card from '@/components/Card'

export default {
  components: {
    navBar,
    Card,
  }
}
</script>

<style>
.container {
  max-width: 700px;
}
</style>
