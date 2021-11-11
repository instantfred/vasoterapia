<template>
  <div v-bind:class="flipped ? 'flip-container flipped': 'flip-container'">
    <div class="flipper">
      <div class="front">
        <slot name="front"></slot>
        <div class="frontFlipBtn"
          v-on:click="flipped=true">
          <img class="icon" alt="Voltear carta" src="./../assets/rotate-right.png">
        </div>
      </div>
      <div class="back">
        <slot name="back"></slot>
        <div class="backFlipBtn"
          v-on:click="flipped=false">
          <img class="icon" alt="Voltear carta" src="./../assets/rotate-left.png">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FlipCard',
  data: function() {
    return {
      flipped: false
    };
  }
};
</script>

<style type='text/css' scoped>
  div.frontFlipBtn,
  div.backFlipBtn {
      position:absolute;
      right: 15px;
      top: 15px;
      color:#FFFFFF;
  }
  @media screen and (max-width: 710px) {
    h2 {
      margin-top: 5px;
      margin-bottom: 5px;
    }
    div.frontFlipBtn,
    div.backFlipBtn {
      right: 5px;
      top: 31px;
    }
  }
  i.backFlipBtn {
      -webkit-transform: rotateY(-180deg);
      -moz-transform: rotateY(-180deg);
      -o-transform: rotateY(-180deg);
      -ms-transform: rotateY(-180deg);
      transform: rotateY(-180deg);
  }
  img.icon {
    height: 20px;
    width: 20px;
  }
  .flip-container {
    -webkit-perspective: 1000;
    -moz-perspective: 1000;
    -o-perspective: 1000;
    perspective: 1000;
  }
  .flip-container {
    min-height: 120px;
  }
  .flipper {
    -moz-transform: perspective(1000px);
    -moz-transform-style: preserve-3d;
    position: relative;
  }
  .front,
  .back {
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    -o-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-transition: 0.6s;
    -webkit-transform-style: preserve-3d;
    -moz-transition: 0.6s;
    -moz-transform-style: preserve-3d;
    -o-transition: 0.6s;
    -o-transform-style: preserve-3d;
    -ms-transition: 0.6s;
    -ms-transform-style: preserve-3d;
    transition: 0.6s;
    transform-style: preserve-3d;
    top: 0;
    left: 0;
    width: 100%;
  }
  .back {
    -webkit-transform: rotateY(-180deg);
    -moz-transform: rotateY(-180deg);
    -o-transform: rotateY(-180deg);
    -ms-transform: rotateY(-180deg);
    transform: rotateY(-180deg);
    position: absolute;
  }
  .flip-container.flipped .back {
    -webkit-transform: rotateY(0deg);
    -moz-transform: rotateY(0deg);
    -o-transform: rotateY(0deg);
    -ms-transform: rotateY(0deg);
    transform: rotateY(0deg);
  }
  .flip-container.flipped .front {
    -webkit-transform: rotateY(180deg);
    -moz-transform: rotateY(180deg);
    -o-transform: rotateY(180deg);
    -ms-transform: rotateY(180deg);
    transform: rotateY(180deg);
  }
  .front {
    z-index: 2;
  }
</style>