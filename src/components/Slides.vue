<template>

<transition-group name="fade"  class="slides"  tag="div" id="slides">
   
     <div class="slides__image" :style="setBackgroundImage" :key="image.id">
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
                <div class="item__block">
                  <div class="block__number">80</div>
                  <div class="block__text">{{image.textSecond}}</div>
                </div>
                <div class="item__block">
                  <div class="block__number">1951</div>
                  <div class="block__text">Год основания компании</div>
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
    width: 290px;
    padding-top: 30px;
    .block__text{
      font-size: 16px;
      color: #fff;
      font-family: "Roboto-regular";
      line-height: 1.4;
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
}

.btn__more{
    display: inline-block;
    height: 30px;
    width: 140px;
    border-radius: 6px;
    background: #fff;
    font-family: "Roboto-regular";
    font-size: 12px;
    line-height: 30px;
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