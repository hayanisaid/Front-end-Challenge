<template>
<div class="home">
  <!-- Header -->
   <div class="header">
   <div class="overlay"></div>
   <div class="row">
     <div class="col-lg-2 col-md-3 col-sm-12 first">
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
     <div class="col-lg-4 col-md-3 col-sm-12">
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
      <div class="col-lg-12 col-md-12 btn_follow">
        <button class="btn btn-default btn-lg">Follow</button>
        <span>
          <i class="material-icons">settings</i>
        </span>
      </div>
      </div>
     </div>
     <!-- navs -->
     <div class="col-lg-3 col-md-3 navs">
       <a href="#" class="nav-link">popular <i class="material-icons">expand_more</i></a>
     </div>
     <div class="col-lg-6 col-md-6 navs">
       <ul class="list-inline">
         <li class="list-inline-item"><a class="nav-link" href="#">affordable</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">fanacy</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">tips</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">community</a></li>
       </ul>
     </div>
     <div class="header-mobile " hidden>
     <div class=" col-sm-12 col-md-12 ">
       <div class="header_mobile_top_right">
       <div class="avatar">
         <img src="../assets/images/image2.png" class="img-fluid">
       </div>
       <div class="note">
          <i class="material-icons">notifications</i>
          <i class="material-icons">favorite</i>
          <a class="dropdown" data-toggle="dropdown" href="#">
          <i class="material-icons" aria-hidden="true">expand_more</i></a>
       </div>
          <ul class="list-unstyled dropdown-menu">
          <li><a href="">Profile <i class="material-icons">person</i></a></li>
          <li><a href="">My cart <i class="material-icons"></i></a></li>
          <li><a href="">Setting <i class="material-icons">settings</i></a></li>
          <li><a href="">Logout <i class="material-icons"></i></a></li>
          </ul>
     <div class=" navs">
       <ul class="list-inline">
         <li><a href="#" class="nav-link">popular <i class="material-icons">expand_more</i></a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">affordable</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">fanacy</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">tips</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">community</a></li>
       </ul>
     </div>
        </div>
     </div>
   </div>
   </div>
   </div><!-- end header -->
   <div class="products"><!-- main page -->
     <div class="row">
       <div class="col-lg-8 col-md-8 col-sm-12">
         <div class="row">
           <div class="col-lg-4 col-md-4 col-sm-12 product" v-for="(data,index) in products" :key="index">
             <div class="item">
               <div class="overlay"></div>
                 <i v-on:click="like(index)" v-bind:class={liked:data.isLiked} class="material-icons">favorite_border</i>
                 <img :src="data.image" class="img-fluid">
             </div>
            <div class="reviews">
            <h4>{{data.name}} <i class="material-icons">star_border</i> <span>5.2</span></h4>
            <span class="review">{{data.like}}k like</span>
            </div>
           </div>

         </div>
       </div>
       <div class="col-lg-4 col-md-4 col-sm-12">
         Here map
       </div>
     </div>
   </div>
     <!-- start footer -->
  <div class="footer">
     <div class="container">
       <div class="pull-left logo">
      <h3>idea<span>date</span></h3>
     </div>
     </div>
  </div>
  <!-- End footer -->
</div>
</template>

<script>
export default {
  // eslint-disable-next-line 
  /* eslint-disable */
  name: 'home',
  
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      products:[
       {
        name:"Asiate",
        image:require("../assets/images/product1.png"),
        rate: 5.2,
        like:4526,
        isLiked:false
       },
        {
        name:"Blue Hill",
        image:require("../assets/images/product2.png"),
        rate: 5.1,
        like:4000,
        isLiked:false
       },
        {
        name:"Jeab-Geaorges",
        image:require("../assets/images/product3.png"),
        rate: 5.3,
        like:4006,
        isLiked:false
       },
        {
        name:"Petrossian",
        image:require("../assets/images/product4.png"),
        rate: 5.0,
        like:670,
        isLiked:false
       },
        {
        name:"ABC kitchen",
        image:require("../assets/images/product5.png"),
        rate: 5.5,
        like:362,
        isLiked:false
       },
       {
        name:"OC",
        image:require("../assets/images/product6.png"),
        rate: 5.4,
        like:3620,
        isLiked:false
       }
      ]
    }
  },
  methods:{
    like(index){
      for(let i=0; i<=this.products.length; i++){
        if(index===i){
          this.products[index].like+=1;
          this.products[index].isLiked=true;
        }

      }
    }
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
.liked{
  color: #e33943 !important;
}
</style>
