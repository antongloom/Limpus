<template>
  <div id="mainapp">
    <div class="main">
       <!-- <Slider />
        <Slider /> -->
        

        <component :is="componentVue"></component>
        <div @click="sliderTop" class="b">1111111111</div>
    </div>
   </div>
</template>

<script>
import Slider from "./components/Slider.vue";
export default {
  data () {
	    return {
	      componentVue: 'Slider'
	   	}	
  	},
  components :{
    Slider
  },
  methods:{
    sliderTop(){
      console.log(this.componentVue)
    }
  }
}
</script>

<style lang="less">
@import url('./assets/stylus/main.less');
@import url('./assets/stylus/animation.less');

.main{
  position: relative;
}
.b{
  position: absolute;
}
</style>

