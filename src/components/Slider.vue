<template>
  <div id="slider" class="slider">
      <Slides :image="images[chosenImage]"/>
      <div class="slider__right" @click="arrowRight"></div>
  </div>
</template>

<script>
import Slides from "./Slides.vue";
export default {
   components: {
      Slides    
   },
   data(){
        return{
            images: [
               {
                    id: 0,
                    text: '111',
                    title: '1111',
                    urlRight: require('../assets/images/bg1.jpg'),
                },
                {
                    id: 1,
                    text: '222',
                    title: '222',
                    urlRight: require('../assets/images/bg2.jpg'),
                },
                {
                    id: 2,
                    text: '333',
                    title: '3333',
                    urlRight: require('../assets/images/bg3.jpg'),
                }
            ],
            chosenImage: 0
        }
   },
   methods :{
    arrowRight(){
       this.move(); 
    },
    move(){
        var flag = this.chosenImage;
        flag++;
        if(flag>=this.images.length){
            flag = 0;
        }
        this.chosenImage = flag;
      }
   },
   created(){
       
   }
}
</script>

<style lang="less">

.slider{
    position: relative;
    .slider__right{
        position: absolute;
        width: 48px;
        height: 32px;
        border: 2px solid rgba(255,255,255,.6);
        border-radius: 4.5px;
        position: absolute;
        bottom: 48px;
        right: 60px;
        z-index: 1000;
        cursor: pointer;
        -webkit-transition: all 0.5s ease;
        -moz-transition: all 0.5s ease;
        transition: all 0.5s ease;
        &:after{
          content: '';
          display: block;
          position: absolute;
          top: 0;
          left: 0;
          right: 0;
          bottom: 0;
          margin: auto;
          background-image: url(../assets/images/arrow-right.svg);
          background-position: 85.5421686746988% 30.555555555555557%;
          width: 12px;
          height: 20px;
          -webkit-transition: .35s ease all;
          transition: .35s ease all;
          &:hover{
          left: 12px;
          }
        }
        &:hover{
          border: 2px solid #fff;
        }
    }
}
</style>