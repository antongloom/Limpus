<template>
  <div id="mainapp" class="mainapp">
       <!-- <Slider /> -->
        <Slider v-if="check" :block="block[0]"/> 
        <div v-else>
            <Slider :block="block[1]" /> 
        </div>
      
        <div  class="b">1111111111</div>
        <button class="b" @click="check = !check">2222</button>
  </div>
</template>

<script>
import Slider from "./components/Slider.vue";
export default {
  components :{
    Slider
  },
  data () {
	    return {
        check: true,
        block:[
           [
               {
                    id: 0,
                    text: '111',
                    title: '1111',
                    urlRight: require('./assets/images/bg1.jpg')
                },
                {
                    id: 1,
                    text: '222',
                    title: '222',
                    urlRight: require('./assets/images/bg2.jpg')
                },
                {
                    id: 2,
                    text: '333',
                    title: '3333',
                    urlRight: require('./assets/images/bg3.jpg')
                }
             ],
             [
               {
                    id: 0,
                    text: '111',
                    title: '1111',
                    urlRight: require('./assets/images/bg4.jpg')
                },
                {
                    id: 1,
                    text: '222',
                    title: '222',
                    urlRight: require('./assets/images/bg5.jpg')
                }
            ]
        ],
        chosenBlock: 0,
      }	
  	},
  methods:{
   arrowBottom(){
     this.move(); 
    },
    move(){
       var flag = this.chosenBlock;
        flag++;
        if(flag>=this.block.length){
            flag = 0;
        }
        this.chosenBlock = flag;
        console.log(this.chosenBlock)
    }
  }
}
</script>

<style lang="less">
@import url('./assets/stylus/main.less');
@import url('./assets/stylus/animation.less');

.mainapp{
  position: relative;
}
.b{
  position: absolute;
  z-index: 2000;
}
</style>

