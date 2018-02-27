<template>
<div class="home">
   <div class="products"><!-- main page -->
         <div class="row">
           <div  class="col-lg-4 col-md-4 col-sm-12 product" v-for="(data,index) in products" :key="index">
             <div class="item">
               <div class="overlay"></div>
                 <i v-on:click="like(index)" v-bind:class={liked:data.isLiked} class="material-icons large">favorite_border</i>
                 <img :src="data.image" class="img-fluid">
                 <div class="controls">
                   <a class="right" ><i class="material-icons large">chevron_right</i></a>
                   <a class="left" ><i class="material-icons">chevron_left</i></a>
                 </div>
             </div>
            <div class="reviews">
            <h4 v-on:click="toDetail(index)">{{data.name}} <i class="material-icons">star_border</i> <span>5.2</span></h4>
             <span v-bind:class="{bounce:data.bounceAnimation}" class="review">{{data.like}}k like</span>
             </div>
           </div>
         </div>
     </div>
   </div>
</template>

<script>

export default {
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
        isLiked:false,
        bounceAnimation:false
       },
        {
        name:"Blue Hill",
        image:require("../assets/images/product2.png"),
        rate: 5.1,
        like:4000,
        isLiked:false,
        bounceAnimation:false
       },
        {
        name:"Jeab-Geaorges",
        image:require("../assets/images/product3.png"),
        rate: 5.3,
        like:4006,
        isLiked:false,
        bounceAnimation:false
       },
        {
        name:"Petrossian",
        image:require("../assets/images/product4.png"),
        rate: 5.0,
        like:670,
        isLiked:false,
        bounceAnimation:false
       },
        {
        name:"ABC kitchen",
        image:require("../assets/images/product5.png"),
        rate: 5.5,
        like:362,
        isLiked:false,
        bounceAnimation:false
       },
       {
        name:"OC",
        image:require("../assets/images/product6.png"),
        rate: 5.4,
        like:3620,
        isLiked:false,
        bounceAnimation:false
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
          this.products[index].bounceAnimation=true;
        }

      }
    },
    toDetail(index){
      const userId=index;
      this.$router.push({name:'details' ,params:{id:userId}})
      //console.log(index)
    }
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
.liked{
  color: #e33943 !important;
}
.bounce{
  animation:bounceIn .3s ease-in infinite;
  animation-timing-function: cubic-bezier(0.1,0.2,0
    3,0.4);
}
.isMenuClosed{
  display: none;
}
.isMenuOpened{
 display: block;
 background: #fff !important;
}
@keyframes bounceIn{
  0%{
    transform: scale(0)
  }
   50%{
    transform: scale(0.5)
  }
   100%{
    transform: scale(1)
  }
}
</style>
