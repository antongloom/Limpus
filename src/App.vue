<template>
  <div id="mainapp" class="mainapp">
        <Slider v-if="flag" :block="block[0]"/>
        <div v-else>
          <Slider :block="block[1]"/>
        </div>
        <div class="mainapp__btn" @click="flag = !flag"></div>
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
        flag: true,
        block:[
           [
               {
                    id: 0,
                    title: 'сделать ваш дом ярче',
                    textFirst: 'Более 45 лет мы создаем решения для создания по настоящему комфортабельного и надежного дома, из года в год отличающиеся инновационными технологиями и уникальным дизайном.',
                    textSecond: 'Стран, в которых есть продукция Schüco',
                    textThree: '',
                    numberFirst: '',
                    numberSecond: '',
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
                    text: '444',
                    title: '444',
                    urlRight: require('./assets/images/bg4.jpg')
                },
                {
                    id: 1,
                    text: '555',
                    title: '555',
                    urlRight: require('./assets/images/bg5.jpg')
                }
            ]
        ]
      }	
  	}
}
</script>

<style lang="less">
@import url('./assets/stylus/main.less');
@import url('./assets/stylus/animation.less');

.mainapp{
  position: relative;
  .mainapp__btn{
    width: 32px;
    height: 48px;
    border: 2px solid rgba(255, 255, 255, 0.6);
    border-radius: 4.5px;
    position: absolute;
    top: 48px;
    left: 60px;
    z-index: 1000;
    cursor: pointer;
    -webkit-transition: all 0.5s ease;
    transition: all 0.5s ease;
    &:after{
      content: '';
      display: block;
      position: absolute;
      top: 10px;
      left: 0;
      right: 0;
      bottom: 0;
      margin: auto;
      background-image: url(./assets/images/arrow-right.svg);
      background-position: 79.93827160493827% 16.89189189189189%;
      width: 20px;
      height: 20px;
      -webkit-transition: .35s ease all;
      transition: .35s ease all;
    }
    &:hover{
      border: 2px solid #fff;
    }
  }
}

</style>

