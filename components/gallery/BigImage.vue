<template>
    <div>
        <div class="container">
            <div>
                <img  :src="image" class="mainImg" @click="showModal" />
            </div>
        </div>
    </div>
</template>
<script>
export default {
  name: 'BigImage',
  props:{
    image:{
        type:String,
        default: ()=> ''
    }
  },
  methods:{
    showModal(){
        this.$emit('rm', true)
    }
  },
}
</script>
<style scoped>
.container{
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    align-items: center;
}
.mainImg{
    display: flex;
    height: 500px;
    width: 600px;
    align-items: center;
}

</style>