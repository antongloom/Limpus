<template>
  <div id="slides" class="slides">
     <div class="slides__image" :style="setBackgroundImage">
    
     </div>
  </div>
</template>
<script>
export default {
   props: ["image"],
   components: {
    
   },
   computed:{
      setBackgroundImage(){
        return {backgroundImage : "url("+this.image.urlRight+")"}
      }
   },
   data(){
        return{
            
        }
   },
   methods :{
      
   },
   created(){
       
   }
}
</script>

<style lang="less">
.slides{
  .slides__image{
    height: 100vh;
    width: 100%;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    position: relative;
  }
}


</style>