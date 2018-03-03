 <!-- eslint-disable -->
<template>
<div class="home">
   <div class="products"><!-- main page -->
         <div class="row">
           <div  class="col-lg-4 col-md-4 col-sm-12 product" v-for="(data,index) in products" :key="index">
             <div class="item">
               <div class="overlay"></div>
                 <i v-on:click="like(index)" v-bind:class={liked:data.isLiked} class="material-icons large">favorite_border</i>
                 <transition name="fade">
                   <img :src="data.image[data.currentImage % data.image.length]" class="img-fluid productImg">
                 </transition>
                 <div class="controls">
                   <a class="right" @click="next(index)"><i class="material-icons large">chevron_right</i></a>
                   <a class="left" @click="prev(index)"><i class="medium material-icons">chevron_left</i></a>
                 </div>
             </div>
            <div class="reviews">
            <h4 @click="toDetail(index)">{{data.name}} <i class="material-icons">star_border</i> <span>5.2</span></h4>
             <span v-bind:class="{bounce:data.bounceAnimation}" class="review">{{data.like}}k like</span>
             
             </div>
           </div>
         </div>
     </div>
   </div>
</template>

<script>
/* eslint-disable */
const vm=this;
export default {
  name: 'home',

  data () {
    return {
      
      products:[
       {
        name:"Asiate",
        image:
        [
        require("../assets/images/product1.png"),
        require("../assets/images/product2.png"),
        require("../assets/images/product3.png"),
        require("../assets/images/product4.png"),
        require("../assets/images/product5.png"),
        require("../assets/images/product6.png")
        ],
        currentImage:0,
        rate: 5.2,
        like:4526,
        isLiked:false,
        bounceAnimation:false
       },
        {
        name:"Blue Hill",
        image:
        [
        require("../assets/images/product2.png"),
        require("../assets/images/product1.png"),
        require("../assets/images/product3.png"),
        require("../assets/images/product4.png"),
        require("../assets/images/product5.png"),
        require("../assets/images/product6.png")
        ],
        currentImage:0,
        rate: 5.1,
        like:4000,
        isLiked:false,
        bounceAnimation:false
       },
        {
        name:"Jeab-Geaorges",
        image:
        [
        require("../assets/images/product3.png"),
        require("../assets/images/product1.png"),
        require("../assets/images/product2.png"),
        require("../assets/images/product4.png"),
        require("../assets/images/product5.png"),
        require("../assets/images/product6.png")
        ],
        currentImage:0,
        rate: 5.3,
        like:4006,
        isLiked:false,
        bounceAnimation:false
       },
        {
        name:"Petrossian",
        image:
        [
        require("../assets/images/product4.png"),
        require("../assets/images/product1.png"),
        require("../assets/images/product3.png"),
        require("../assets/images/product2.png"),
        require("../assets/images/product5.png"),
        require("../assets/images/product6.png")
        ],
        currentImage:0,
        rate: 5.0,
        like:670,
        isLiked:false,
        bounceAnimation:false
       },
        {
        name:"ABC kitchen",
        image:
        [
        require("../assets/images/product5.png"),
        require("../assets/images/product1.png"),
        require("../assets/images/product3.png"),
        require("../assets/images/product4.png"),
        require("../assets/images/product2.png"),
        require("../assets/images/product6.png")
        ],
        currentImage:0,
        rate: 5.5,
        like:362,
        isLiked:false,
        bounceAnimation:false
       },
       {
        name:"OC",
        image:
        [
        require("../assets/images/product6.png"),
        require("../assets/images/product1.png"),
        require("../assets/images/product3.png"),
        require("../assets/images/product4.png"),
        require("../assets/images/product5.png"),
        require("../assets/images/product2.png")
        ],
        currentImage:0,
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
      this.$router.push({name:'details' ,params:{Productid:userId}})
      //console.log(index)
    },
    next:function(index){
      
     for(let i=0 ; i <=this.products.length; i++){
       if(index===i){
        this.products[index].currentImage+=1
       }
     }
    },
    prev:function(index){
      
      for(let i=0 ; i <=this.products.length; i++){
      if(index===i){
        this.products[index].currentImage-=1
        if(this.products[index].currentImage < 0){
          this.products[index].currentImage=this.products[index].image.length
        }
        
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
.fade-enter{
  animation:fadeImg .3s linear;
}
@keyframes fadeImg{
  0%{
    opacity: 0;
    transform: scale(1);
  }
    100%{
    opacity: 1;
    transform: scale(0);
  }
}
</style>
