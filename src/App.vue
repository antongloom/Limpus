<template>
  <div id="mainapp" class="mainapp">
       <!-- <Slider /> -->
        <Slider :block="block[chosenBlock]" /> 
        <div @click="arrowBottom" class="b">1111111111</div>
  </div>
</template>

<script>
import Slider from "./components/Slider.vue";
export default {
  data () {
	    return {
	      componentVue: 'Slider',

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
        chosenBlock: 0
      }	
  	},
  components :{
    Slider
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
}
</style>

