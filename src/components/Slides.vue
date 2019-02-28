<template>

<transition-group :name="image.animation"  class="slides"  tag="div" id="slides">
   
     <div class="slides__image" :style="setBackgroundImage" :key="image.id"></div>

</transition-group>



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
    position: relative;
    .slides__image{
      height: 100vh;
      width: 100%;
      background-repeat: no-repeat;
      background-position: center;
      background-size: cover;
    }
}



.fade-enter-active{
    animation-name: fadeEnter;
    animation-duration: 1.5s;
    animation-iteration-count: 1;
}

.fade-move{
    transition: all 1s;
}

.fade-leave-active{
    animation-name: fadeLeave;
    animation-duration: 1.5s;
    animation-iteration-count: 1;
    position: absolute;
}

@keyframes fadeEnter{
    from{
        right: 100%;
    }
    to{
        right: 0%; 
    }
}

@keyframes fadeLeave{
    from{
        right: 0%; 
    }
    to{
        right: 100%; 
    }
} 

/*
.fadeTop-enter-active{
    animation-name: fadeTopEnter;
    animation-duration: 1.5s;
    animation-iteration-count: 1;
}

.fadeTop-move{
    transition: all 1s;
}

.fadeTop-leave-active{
    animation-name: fadeTopLeave;
    animation-duration: 1.5s;
    animation-iteration-count: 1;
    position: absolute;
}

@keyframes fadeTopEnter{
    from{
        top: 100%;
    }
    to{
        top: 0%; 
    }
}

@keyframes fadeTopLeave{
    from{
        top: 0%; 
    }
    to{
        top: 100%; 
    }
} 
*/




</style>