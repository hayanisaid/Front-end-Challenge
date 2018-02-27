<template>
<transition name="fadePage">
		<div class="details">
	<div class="row">
		<div class="col-lg-12 col-md-4 col-sm-12 product">
		<div v-for="(data,index) in productDetails" :key="index">
			<div v-if="productId===index">
			<img :src="data.image" class="img-fluid">
			<div class="product-detail">
				<h4>{{data.name}}<i class="material-icons">star_border</i> <span>5.2</span></h4>
			    <p>id:{{productId}}</p>
			</div>
			</div>
		
		</div>
			
		</div>
		<div class="col-lg-7 col-md-8 col-sm-12 product">
		
		</div>
	</div>
</div>
</transition>
</template>
<style scoped>
.details{
}
/*conponent transition*/
.fadePage-enter-active{
  filter:blur(60px);
  transition: .5s;
  animation-timing-function: cubic-bezier(0.111,0.312 ,0.548 ,0.765 );
}
.fadePage-leave-active{
 filter:blur(0);
}
</style>
<script>
export default{
/* eslint-disable */
name:"details",
data(){
	return{
	 productId:this.$route.params.id,
	 productName:'',
	 productImage:'',
	 productRate:'',
     
	 productDetails:[
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
}
}
</script>