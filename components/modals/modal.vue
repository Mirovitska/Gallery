<template>
    <div class="modal"  >
       
      <div class="modal-content">

        <!-- <BigImage :image="img"/> -->
        <img :src="image" :image="img" style=" width:410px">
        
        <!-- <Sidebar :imagesSidebar="items" @selectedImg="showImg($event)"/> -->
        <div>
            <p class='close' @click="closeModal" style="background-color: orange;">X </p>
        <Thumb :images="items" class='sidebar' @selectedImg="showImg($event)">
            </Thumb>
</div>
        
      </div>
    </div>
  </template>
  
  <script>
//   import Sidebar from "../gallery/sidebar.vue"
import Thumb from "../gallery/Thumb.vue"
  import BigImage from "../gallery/bigImage.vue"
  export default {
    name: 'Modal',
    components: { BigImage, Thumb},
    props:{
    image:{
        type:String,
        default: ()=> ''
    }
  },
   
    data() {
    return {
        
      items: [
        'https://img.freepik.com/free-photo/tasty-homemade-traditional-pizza-italian-recipe_24972-2141.jpg?w=1480&t=st=1679851312~exp=1679851912~hmac=d958c3eb786494d484c51a0859720eaa74a1be0db82bb95ec783c572a86da3d0',
        'https://img.freepik.com/free-photo/close-up-italian-pizza-about-cheese-it-stick-selective-focus-generative-ai_1258-153067.jpg?w=1480&t=st=1679860273~exp=1679860873~hmac=3c3dab383876aa2cd2fc7bdf9bb8e85610c58aa6fe177f626c0ba6c4b78060ac',
        'https://img.freepik.com/free-photo/top-view-mixed-pizza-with-tomato-black-olive-melted-cheese_140725-10787.jpg?w=996&t=st=1679860291~exp=1679860891~hmac=bbfdb27e42dd7748b10c85fb5eefab7450b9bf6a1ca6470118284898f091b367',
    ],
        image: 'https://img.freepik.com/free-photo/pizza_144627-39499.jpg?w=1480&t=st=1679860446~exp=1679861046~hmac=855e2b8b45b674b8dbf5ac42008330567006fa7d829f135c000312df88b0e021',
  }
},
    
  
    methods: {
     
      showImg(url){
        this.image =url;
        
      },
      closeModal() {
        this.$emit('closeModal', false)
      },
    }
  }
  </script>
  <style scoped>
  .modal {
    position: absolute;
    left: 0;
    top: 0;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0,0,0, 0.7);
  }
  
  .modal-content {
    display: flex;
    background-color: rgb(2, 3, 2);
    width: auto;
    height: auto;
    justify-content: center;
    align-items: center;
    margin-top: 0px;
    position: absolute;
    left: calc(50vw - 300px);
    top: calc(50vh - 300px);
    margin-top: 100px;
    margin-right: 500px;
    
  }
  .sidebar img{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    height: 50px;
    width: 50px;
    align-content: center;
    flex-direction: row;
  }
  .sidebar{
    display: flex;
    flex-wrap: wrap;
    margin-left: 20px;

  }
  .close{
  display: flex;
  justify-content: center;
  width:20px;
  height: 20px;
  float:right;
  border-radius: 15%;
  cursor: pointer;
  }
  p{
    display:flex;
    justify-content: center;
    
  }
  </style>