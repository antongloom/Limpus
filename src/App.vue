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
                    textThree: 'Год основания компании',
                    numberFirst: '80',
                    numberSecond: '1951',
                    urlRight: require('./assets/images/bg1.jpg')
                },
                {
                    id: 1,
                    title: 'сохранить ваше тепло',
                    textFirst: 'Наша главная ценность — качество наших решений. Мы заботимся о повышении энергоэффективности и сохранении уюта и точно знаем, как сберечь красоту и тепло вашего дома.',
                    textSecond: 'Сотрудников трудятся в нашей компании',
                    textThree: 'Из них работает в Германии',
                    numberFirst: '4700',
                    numberSecond: '3300',
                    urlRight: require('./assets/images/bg2.jpg')
                },
                {
                    id: 2,
                    title: 'обезопасить вас',
                    textFirst: 'Постоянно обмениваясь опытом с нашими партнерами, мы предлагаем «умные» оконные и дверные системы, отвечающие всем современным стандартам комфорта, безопасности и энергоэффективности.',
                    textSecond: 'Миллиарда евро оборот компании за 2016 год',
                    textThree: 'Компаний-партнеров, по всему миру',
                    numberFirst: '1,5',
                    numberSecond: '1200',
                    urlRight: require('./assets/images/bg3.jpg')
                }
             ],
             [
               {
                    id: 3,
                    title: 'обезопасить вас',
                    textFirst: 'Постоянно обмениваясь опытом с нашими партнерами, мы предлагаем «умные» оконные и дверные системы, отвечающие всем современным стандартам комфорта, безопасности и энергоэффективности.',
                    textSecond: 'Миллиарда евро оборот компании за 2016 год',
                    textThree: 'Компаний-партнеров, по всему миру',
                    numberFirst: '1,5',
                    numberSecond: '1200',
                    urlRight: require('./assets/images/bg4.jpg')
                },
                {
                    id: 4,
                    title: 'обезопасить вас',
                    textFirst: 'Постоянно обмениваясь опытом с нашими партнерами, мы предлагаем «умные» оконные и дверные системы, отвечающие всем современным стандартам комфорта, безопасности и энергоэффективности.',
                    textSecond: 'Миллиарда евро оборот компании за 2016 год',
                    textThree: 'Компаний-партнеров, по всему миру',
                    numberFirst: '1,5',
                    numberSecond: '1200',
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
    width: 48px;
    height: 32px;
    border: 2px solid rgba(255, 255, 255, 0.6);
    border-radius: 4.5px;
    position: absolute;
    bottom: 48px;
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

