<template>
   <nav class="navbar navbar-expand-lg navbar-light" style="background-color: #e3f2fd;">
       <a class="navbar-brand" href="#"> Markup Application </a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto" v-if="show">
      <li class="nav-item" >
        <router-link class="nav-link" to="/"> Home </router-link>
      </li>
      <li class="nav-item">
        <router-link class="nav-link" to="/markup"> Markup </router-link>
      </li>
      <li class="nav-item">
        <router-link class="nav-link" to="/user"> Info </router-link>
      </li>
    </ul>
  </div>
</nav> 
</template>

<script>
export default {
    props: ["show"],
}
</script>