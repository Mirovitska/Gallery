<template>
    <div >
        <TopNav/>
        <div class="about">
        <!-- <h1 class="onas">O nas</h1>
        <h2 class="onas"> strona </h2> -->
        <button class="onas" @click="showInfo">Kliknij mnie</button>
      </div>
    </div>
</template>

<script>
import TopNav from '../components/nav/TopNav.vue'
export default {
  name: 'OnasPage',
  components: { TopNav },

  methods: {
    showInfo: () => {
        console.log('Witaj w konsoli')
        alert('Witaj')
    }
  }
}
</script>
<style scoped>
.onas{
  margin-top: 50px;
}
.about{
  display: flex;
  align-items: center;
  flex-direction: row;
  justify-content: center;
}
</style>