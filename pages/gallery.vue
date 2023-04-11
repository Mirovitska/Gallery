
<template>
  <div class="galleryDiv">
    <TopNav />
    <BigImage :image="img" @rm="runModal($event)"/>
    <Thumb :images="items" @selectedImg="showImg($event)" clas="selected"/>
    <Modal v-show="showModal" :image="img" @closeModal="runModal($event)"/>
  </div>
</template>
      
<script>
import TopNav from '../components/nav/TopNav.vue'
import BigImage from '../components/gallery/bigImage.vue';
import Thumb from '../components/gallery/Thumb.vue';
import Modal from '../components/modals/modal.vue';
import Sidebar from "../components/gallery/sidebar.vue"


export default {
  name: 'GalleryPage',
  components: { TopNav, BigImage, Thumb, Modal, Sidebar },
  data() {
    return {
      items: [
        'https://img.freepik.com/free-photo/tasty-homemade-traditional-pizza-italian-recipe_24972-2141.jpg?w=1480&t=st=1679851312~exp=1679851912~hmac=d958c3eb786494d484c51a0859720eaa74a1be0db82bb95ec783c572a86da3d0',
        'https://img.freepik.com/free-photo/close-up-italian-pizza-about-cheese-it-stick-selective-focus-generative-ai_1258-153067.jpg?w=1480&t=st=1679860273~exp=1679860873~hmac=3c3dab383876aa2cd2fc7bdf9bb8e85610c58aa6fe177f626c0ba6c4b78060ac',
        'https://img.freepik.com/free-photo/top-view-mixed-pizza-with-tomato-black-olive-melted-cheese_140725-10787.jpg?w=996&t=st=1679860291~exp=1679860891~hmac=bbfdb27e42dd7748b10c85fb5eefab7450b9bf6a1ca6470118284898f091b367',
        

      ],
      img: 'https://img.freepik.com/free-photo/pizza_144627-39499.jpg?w=1480&t=st=1679860446~exp=1679861046~hmac=855e2b8b45b674b8dbf5ac42008330567006fa7d829f135c000312df88b0e021',
      showModal :false
    }
  },
  methods: {
    showImg(url){
      this.img = url
    },
    runModal(e){
      this.showModal = e
    }
  }
}

</script>
      
<style scoped>
image{
  border:20px orange;
}
.galleryPage {
  display: flex;
  align-items: center;
  width: 300px;
  height: 100px;
  font-size: large;
  font-style: italic;
  color: white;
  text-align: center;

}

.galleryDiv {

  justify-content: center;
  text-align: center;
  flex-wrap: wrap;
  align-items: center;

}
.selected{
  border: 5px orange;
}
</style>