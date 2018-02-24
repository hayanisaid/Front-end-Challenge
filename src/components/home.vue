<template>
<div class="home">
  <!-- Header -->
   <div class="header">
   <div class="overlay"></div>
   <div class="row">
     <div class="col-lg-2 col-md-2 col-sm-12 first">
      <div class="logo">
        <h3>idea<span>date</span></h3>
      </div>
      <div class="mt-3">
        <img src="../assets/images/image1.png" class="img-fluid">
      </div>
     </div>
     <div class="col-lg-6 col-md-6 col-sm-12">
       <div class="browse">
              <a class="dropdown m-2" data-toggle="dropdown" href="#">Browse  <i class="material-icons" aria-hidden="true">expand_more</i></a>
              <ul class="list-unstyled dropdown-menu">
                <li><a href="">link</a></li>
                <li><a href="">link</a></li>
                <li><a href="">link</a></li>
                <li><a href="">link</a></li>
              </ul>
        </div>
        <div class="header_description">
          <div class="title">
                      <h3>Date Night Restaurants</h3>
                      <br>
                      <p> Best places for a date night in New York City</p>
                      <span>
                        6 M FOLLOWERS
                      </span>
                    </div>
        </div>
     </div>
     <div class="col-lg-4 col-md-4 col-sm-12">
      <div class="row">
      <div class="col-lg-12 col-md-12">
        <div class="header_top_right float-right">
          <i class="material-icons">notifications</i>
          <i class="material-icons">favorite</i>
          <img src="../assets/images/image2.png" class="img-fluid">
          <a class="dropdown" data-toggle="dropdown" href="#">
          <i class="material-icons" aria-hidden="true">expand_more</i></a>
          <ul class="list-unstyled dropdown-menu">
          <li><a href="">Profile <i class="material-icons">person</i></a></li>
          <li><a href="">My cart <i class="material-icons"></i></a></li>
          <li><a href="">Setting <i class="material-icons">settings</i></a></li>
          <li><a href="">Logout <i class="material-icons"></i></a></li>
          </ul>
        </div>
      </div>
      <div class="col-lg-12 col-md-12">
        <div class="btn_follow">
        <button class="btn btn-default btn-lg">Follow</button>
        <span>
          <i class="material-icons">settings</i>
        </span>
      </div>
      </div>
      </div>
     </div>
   </div>
   </div><!-- end header -->
</div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style>

</style>
