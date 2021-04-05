<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <img src="favicon.ico"/>
    <nuxt-link active-class="active" class="nav-link" to="/">
    <a class="navbar-brand">News</a>
    </nuxt-link>

    <div class="collapse navbar-collapse">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item">
          <nuxt-link active-class="active" class="nav-link" to="/">
            Posts
          </nuxt-link>
        </li>       
       
        <b-nav-form>
      <b-form-input class="mr-sm-2" placeholder="Search"></b-form-input>
      <b-button variant="outline-success" class="my-2 my-sm-0" type="submit">Search</b-button>
    </b-nav-form>
      </ul>
    </div>
  </nav>
</template>

<style>

</style>

