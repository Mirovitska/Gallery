<template>
    <div class="sidebar">
          <img :src="item" v-for="(item, index) in imagesSidebar" :key="index" class="image" @click="sendImage(item)">
    </div>
  </template>
  
  <script>
  export default {
    name: 'Sidebar',
    props: {
      imagesSidebar: {
        type: Array,
        default: () => []
      }
    },
  
  
    methods: {
      sendImage(url) {
        this.$emit('selectedImg', url)
      }
    }

  }
  </script>
  <style scoped>
  .sidebar {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    height: 150px;
    width: 150px;
    align-content: center;
    flex-direction: row;
  }
  .sidebar img{
    width: 100px;
    height: 100px;
  padding-top: 5px;
  }
  </style>