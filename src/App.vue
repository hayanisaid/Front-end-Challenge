<template>
  <div id="app">
    <!-- Header -->
   <div class="header">
   <div class="overlay"></div>
   <div class="row">
     <div class="col-lg-2 col-md-3 col-sm-12 first">
      <div class="logo">
        <h3>idea<span>date</span></h3>
      </div>
      <div class="mt-3">
        <img src="./assets/images/image1.png" class="img-fluid">
      </div>
     </div>
     <div class="col-lg-7 col-md-6 col-sm-12">
       <div class="browse ">
              <a @click="BrowseMenu" class="dropdown m-2" data-toggle="dropdown" href="#">Browse  <i class="material-icons" aria-hidden="true">expand_more</i></a>
              <transition name="broswM">
                 <ul v-show="BrowseMenuState" class="list-unstyled dropdown-menu">
                <li><a href="">Popular</a></li>
                <li><a href="">Tips</a></li>
                <li><a href="">Community</a></li>
                <li><a href="">Fanacy</a></li>
              </ul>
              </transition>
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
     <div class="col-lg-3 col-md-3 col-sm-12">
      <div class="row">
      <div class="col-lg-12 col-md-12">
        <div class="header_top_right float-right">
          <i class="material-icons">notifications</i>
          <i class="material-icons">favorite</i>
          <img src="./assets/images/image2.png" class="img-fluid">
          <a @click="openUserMenu" class="dropdown" data-toggle="dropdown" href="#">
          <i class="material-icons" aria-hidden="true">expand_more</i></a>
          <transition name="userM">
             <ul v-show="UserMenuState" class="list-unstyled dropdown-menu">
          <li><a href="">Profile <i class="material-icons">person</i></a></li>
          <li><a href="">Orders <span class="pill">12</span></a></li>
          <li><a href="">My favorits <i class="material-icons">favorite</i></a></li>
          <li><a href="">Sign out <i class="material-icons">arrow_forward</i></a></li>
          </ul>
          </transition>
        </div>
        <div class="menu_lancher">
          <span  @click="MobileMenuState= !MobileMenuState" :aria-pressed="MobileMenuState?'true':'false'" class="open"><i class="material-icons">menu</i></span>
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
       <a href="#" class="nav-link popular">popular <i class="material-icons">expand_more</i></a>
     </div>
     <div class="col-lg-6 col-md-6 navs">
       <ul class="list-inline">
         <li class="list-inline-item"><a class="nav-link" href="#">affordable</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">fanacy</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">tips</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">community</a></li>
       </ul>
     </div>
     <transition name="fade">
      <div v-show="MobileMenuState" v-bind:class="{MenuOpened:MobileMenuState}" class="header-mobile">
     <div class=" col-sm-12 col-md-12 ">
       <div class="header_mobile_top_right">
       <span @click="MobileMenuState = !MobileMenuState" :aria-pressed="MobileMenuState?'true':'false'"  class="close"><i class="material-icons">close</i></span>
       <div class="avatar">
         <img src="./assets/images/image2.png" class="img-fluid">
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
          <li><a href="">Sign out <i class="material-icons"></i></a></li>
          </ul>
     <div class=" navs">
       <ul class="list-inline">
         <li><a href="#" class="nav-link">popular </a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">affordable</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">fanacy</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">tips</a></li>
         <li class="list-inline-item"><a class="nav-link" href="#">community</a></li>
       </ul>
     </div>
        </div>
     </div>
   </div>
     </transition>
   </div>
   </div><!-- end header -->
   <div class="main_page">
     <div class="row">
       <div class="col-lg-8 col-md-8 col-sm-12">
        <div class="container">
              <router-view/>
        </div>
       </div>
       <div class="col-lg-4 col-md-4 col-sm-12 map">
       <div class="form-search">
         <div class="btn-group">
           <button class="btn btn-default btn-sm"><i class="material-icons">add</i></button>
           <button class="btn btn-default btn-sm"><i class="material-icons">remove</i></button>
         </div>
         <input type="text" class="form-control" name="search" placeholder="Search for an address">
       </div>
       <div class="markers">
         <span><img src="./assets/images/marker.png" class="img-fluid"></span>
         <span><img src="./assets/images/marker.png" class="img-fluid"></span>
         <span><img src="./assets/images/marker.png" class="img-fluid"></span>
         <span><img src="./assets/images/marker.png" class="img-fluid"></span>
       </div>
       <img src="./assets/images/map.png" class="img-fluid">
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
  /* eslint-disable */
   name: 'App',
   
   data (){
   return{
    MenuOpened     :false,
    MobileMenuState:false,
    BrowseMenuState:false,
    UserMenuState  :false  
   }
  
   },
    methods:{
    closeMenu(){
     this.MobileMenuState=(this.MobileMenuState===false)?true:false
    },
    openMenu(){
      this.MobileMenuState=(this.MobileMenuState===false)?true:false
      console.log('opened')
    },
    BrowseMenu:function(){
      this.BrowseMenuState=(this.BrowseMenuState===false)?true:false
    },
    openUserMenu:function(){
      this.UserMenuState=(this.UserMenuState===false)?true:false
    }
   }
}
</script>

<style scoped>
/*.menuState-enter-active{
  animation:all moveInLeft .6s  infinite;
  animation-timing-function: cubic-bezier(0.1,0.2,0.3,0.5);
}*/
#app{
  overflow: hidden;
}
.fade-enter-active {
 animation :moveInLeft .3s linear ;
 animation-timing-function: cubic-bezier(0.111,0.312 ,0.548 ,0.765 );
}
 .fade-leave-active/* .fade-enter, .fade-leave-to .fade-leave-active below version 2.1.8 */ {
  animation:moveFromRight .3s linear;
  animation-timing-function: cubic-bezier(0.111,0.3122 ,0.548 ,0.765 );
}
@keyframes moveInLeft{
  0%{
    transform: translateX(300px);
  }
  100%{
   transform: translateX(0px); 
  }
  .MenuOpened{
    background: red !important;
  }
}
@keyframes moveFromRight{
  0%{
    transform: translateX(0px);
  }
  100%{
   transform: translateX(300px); 
  }
  .MenuOpened{
    background: red !important;
  }
}
.broswM-enter-active{
  animation:bouncem .3ms linear;
}

@keyframes bouncem{
 
  0%{
    height: 0%;
   
  }
  50%{
     height: 50%; 
  }
  100%{
     height: 100%;
  }
}
.userM-enter-active
{
  animation:fadeInRight .3s linear;
}
@keyframes fadeInRight{
  0%{
    transform: translateX(300px);
  }
  50%{
    transform: translateX(50px);
  }
  100%{
    transform: translateX(0px);
  }
}


</style>
