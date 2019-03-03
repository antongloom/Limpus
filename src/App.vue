<template>
  <div id="mainapp">
    <div class="main">
        <Slider />
        <Slider />
    </div>
   </div>
</template>

<script>
import Slider from "./components/Slider.vue";
export default {
  data () {
	    return {
	      
	   	}	
  	},
  components :{
    Slider
  },
}
</script>

<style lang="less">
@import url('./assets/stylus/main.less');
@import url('./assets/stylus/animation.less');

.main{
  position: relative;
}

</style>

