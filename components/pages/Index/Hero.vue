<template>
  <div class="p-hero">
    <!--<img src="/img/moc/1200x600.png" class="p-hero&#45;&#45;background">-->
    <div class="p-hero--slogan">
      <div class="p-hero--slogan_bg"></div>
      <div class="p-hero--slogan_text_wrapper">
        <div class="p-hero--slogan_text"><span>Webのこれからを語り合う</span></div>
        <div class="p-hero--slogan_text"><span></span><span>「作る」</span><span>「伝える」</span><span>「語り合う」</span></div>
      </div>
   </div>
  </div>
</template>

<style lang="scss" scoped>
  @import "~assets/scss/layout/_layout.scss";
  @import "~assets/scss/object/component/_container.scss";
  @import "~assets/scss/object/component/_title.scss";

  .p-hero{
    @include c-container;
    background: url("/images/brand_top.jpg");
    background-position: 100% 50%;
    background-size: cover;
    background-repeat: no-repeat;
    height: 30rem;
    padding-top: 8rem;
    padding-bottom: 10em;
    animation: hero_bg_img 1s cubic-bezier(.4, .2, 0, 1) 0s 1 alternate both running;
    @keyframes hero_bg_img {
      from {
        opacity: 0;
        background-position: 100% 100%;
      }
      to {
        opacity: 1;
        background-position: 100% 50%;
      }
    }

    @include desktop(){
      background-size: 90%;
      padding-top: 30rem;
      height: 70rem;
    }

    &--inner{
      @include c-containerInner
    }

    &--slogan{
      //display: absolute;
      position: relative;
      color: white;
      font-size: 1.5rem;
      width: 80%;
      margin-top:3rem;
      border-radius: 0 6px 6px 0;
      text-align: left;
      z-index: 1;
      &_bg {
        position: absolute;
        width: 100%;
        height: 100%;
        background-color: rgba(195,80,79,0.9);
        animation: slogan .8s cubic-bezier(.4, .2, 0, 1) .4s 1 alternate both running;
        z-index: -1;
      }
      @keyframes slogan {
        0% {
          width: 0%;
        }
        100% {
          width: 100%;
        }
      }

      &_text_wrapper {
        padding: 2rem 1rem;
      }
      &_text {
        font-weight: bold;
        font-family: YuGothic, serif;
        perspective: 250px;
        @include desktop() {
          line-height: 84px;
          font-family: YuGothic, serif;
          font-size: 30px;
          letter-spacing: 4px;
          color: #FFFFFF;
        }
        span {
          display: inline-block;
          transform-origin: 50% 50% -10px;
        }
        span:nth-child(1) {
          animation: slogan_text .6s cubic-bezier(.4, .2, 0, 1) .6s 1 alternate both running;
        }
        span:nth-child(2) {
          animation: slogan_text .6s cubic-bezier(.4, .2, 0, 1) 1.2s 1 alternate both running;
        }
        span:nth-child(3) {
          animation: slogan_text .6s cubic-bezier(.4, .2, 0, 1) 1.4s 1 alternate both running;
        }
        span:nth-child(4) {
          animation: slogan_text .6s cubic-bezier(.4, .2, 0, 1) 1.6s 1 alternate both running;
        }
        @keyframes slogan_text {
          0% {
            transform: rotateX(88deg);
          }
          100% {
            transform: rotateX(0deg);
          }
        }
      }
      @include desktop(){
        font-size: 3rem;
        line-height: 8rem;
      }
    }    
  }
</style>
