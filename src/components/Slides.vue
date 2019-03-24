<template>

<transition-group name="fade"  class="slides"  tag="div" id="slides">
     <div class="slides__image" :style="setBackgroundImage" :key="image.id">
          <div class="application-left" v-if="applicationShow"></div>
          <div class="image__header">
            <div class="header__logo">Limpus</div>
            <div class="header__btn">
              <div class="btn__phone"></div>
              <div class="btn__menu" @click="application"><span></span></div>
            </div>
          </div>
          <div class="image__content">
              <div class="content__title">Мы знаем, как</div>
              <div class="content__subtitle">{{image.title}}</div>
              <div class="content__item item">
                <div class="item__block">
                  <div class="block__text">{{image.textFirst}}</div>
                  <div class="block__btn">
                    <div class="btn__more">узнать больше</div>
                  </div>
                </div>
                <div class="item__block item__block--left">
                  <div class="block__number">{{image.numberFirst}}</div>
                  <div class="block__text block__text--width">{{image.textSecond}}</div>
                </div>
                <div class="item__block item__block--left">
                  <div class="block__number">{{image.numberSecond}}</div>
                  <div class="block__text block__text--width">{{image.textThree}}</div>
                </div>
              </div>
          </div>
     </div>

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
          applicationShow: false
        }
   },
   methods :{
      application(){
        this.applicationShow = !this.applicationShow
      }
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

.image__header{
  max-width: 992px;
  margin: 0 auto;
  padding-top: 40px;
  display: flex;
  justify-content: space-between;
  .header__logo{
    font-family: "Roboto-regular";
    font-size: 32px;
    color: #fff;
  }
  .header__btn{
    .btn__phone{
      display: inline-block;
      height: 19px;
      width: 19px;
      background: url(../assets/images/arrow-right.svg) no-repeat;
      background-position: 79.6923076923077% 23.875432525951556%;
      cursor: pointer;
      margin-right: 72px;
      position: relative;
      top: -4px;
    }
    .btn__menu{
      position: relative;
      display: inline-block;
      width: 48px;
      height: 24px;
      cursor: pointer;
      &:before{
        content: '';
        width: 48px;
        height: 2px;
        display: block;
        background: #fff;
        border-radius: 2px;
        position: absolute;
        top: 0px;
        -webkit-transition: all 0.3s ease;
        -moz-transition: all 0.3s ease;
        transition: all 0.3s ease;
      }
      &:after{
        content: '';
        width: 48px;
        height: 2px;
        display: block;
        background: #fff;
        border-radius: 2px;
        position: absolute;
        bottom: 0px;
        -webkit-transition: all 0.3s ease;
        -moz-transition: all 0.3s ease;
        transition: all 0.3s ease;
      }
      span{
        width: 48px;
        height: 2px;
        display: block;
        background: #fff;
        border-radius: 2px;
        position: absolute;
        top: 0;
        bottom: 0;
        right: 0;
        margin: auto;
      }
    }
  }
}

.image__header .header__btn .btn__menu:hover:before{
  top: 2px;
}

.image__header .header__btn .btn__menu:hover:after{
  bottom: 2px;
}

.image__content{
  height: auto;
  width: 900px;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
  -moz-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  -o-transform: translate(-50%, -50%);
  .content__title{
    font-size: 72px;
    color: #fff;
    font-family: "Roboto-regular";
  }
  .content__subtitle{
    font-size: 72px;
    color: #fff;
    font-family: "Roboto-regular";
  }
  .content__item{
    display: flex;
    justify-content: space-between;
  }
}

.item{
  .item__block{
    width: 295px;
    padding-top: 30px;
    .block__text{
      font-size: 16px;
      color: #fff;
      font-family: "Roboto-regular";
      line-height: 1.4;
    }
    .block__text--width{
      width: 200px;
    }
    .block__btn{
      padding-top: 20px;
    }
    .block__number{
      font-size: 64px;
      color: #fff;
      font-family: "Roboto-regular";
      padding-bottom: 15px;
    }
  }
  .item__block--left{
    position: relative;
    left: 30px;
  }
}

.btn__more{
    display: inline-block;
    height: 30px;
    width: 140px;
    border-radius: 6px;
    background: #fff;
    font-family: "Roboto-regular";
    font-size: 12px;
    line-height: 34px;
    text-transform: uppercase;
    text-align: center;
    color: #000;
    border: 2px solid #fff;
    outline: 0;
    cursor: pointer;
    -webkit-transition: all 0.5s ease;
    -moz-transition: all 0.5s ease;
    transition: all 0.5s ease;
    &:hover{
      background: inherit;
      color: #fff;
    }
}


.application-left{
  position: absolute;
  height: 100%;
  width: 50%;
  z-index: 2000;
  background: #fff;
}

/*
.slide-enter-active, .slide-leave-active {
  transition: opacity .5s;
}

.fade-enter, .fade-leave-to  {
  opacity: 0;
} */

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








</style>