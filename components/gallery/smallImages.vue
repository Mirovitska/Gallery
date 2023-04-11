<template>
            <div class="mini-gallery">
                    <img  :src="image1" class="img" :key="index" />
                    <img  :src="image2" class="img" />
                    <img  :src="image3" class="img" /> 
                    <img  :src="image4" class="img" /> 
        </div>
</template>
<script>
export default {
  name: 'smallImages',
  props:{
    image1:{
        type:String,
        default: ()=> ''
    },
    image2:{
        type:String,
        default: ()=> ''
    },
    image3:{
        type:String,
        default: ()=> ''
    },
    image4:{
        type:String,
        default: ()=> ''
    }

  },
  created(){
    console.log(this.image1)
  }
}
</script>
<style>
.mini-gallery{
    margin: 10px auto 0;
    display: flex;
	position: relative;
	width: 610px;
	height: 100px;
	font-size: 0;
    justify-content: space-around;
}
.img{
    margin: 0px auto 0;
    display: flex;
	position: relative;
	width: auto;
	height: 100px;
	background-color: #062c23;
	border-radius: 8px;
	font-size: 0;
}
</style>