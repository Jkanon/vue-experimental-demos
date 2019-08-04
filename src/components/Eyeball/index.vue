<template>
  <div class="eye_container" :style="eyeContainerStyle">
    <div class="eye">
      <EyeIris />
    </div>
    <div class="shade"></div>
  </div>
</template>

<script>
import EyeIris from './EyeIris'

export default {
  name: 'Eyeball',
  components: {
    EyeIris
  },
  props: {
    size: {
      type: Number,
      default: 200
    }
  },
  computed: {
    eyeContainerStyle() {
      return {
        width: this.size + 'px',
        height: this.size + 'px'
      }
    }
  }
}
</script>

<style>
  .eye {
    position: relative;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background-image: radial-gradient(circle at 45% 45%, #fff 41%, #ccc 83%);
  }

  .eye:before, .eye:after {
    content: "";
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border-radius: 50%;
  }
  .eye:before {
    opacity: .75;
    mix-blend-mode: color-burn;
    background-image: radial-gradient(circle at 45% 45%, #ffe 30%, #222 67%, #558 80%);
    z-index: 10;
  }

  .eye:after {
    mix-blend-mode: overlay;
    background-image: radial-gradient(circle at 65% 65%, #000 20%, rgba(0,0,0,0) 40%);
    z-index: 4;
    opacity: 0.5;
    -webkit-animation: eye_shade ease-in-out 1.5s infinite;
    animation: eye_shade ease-in-out 1.5s infinite;
  }

  .eye {
    -webkit-animation: float ease-in-out 1.5s infinite;
    animation: float ease-in-out 1.5s infinite;
  }

  .shade {
    -webkit-animation: shade ease-in-out 1.5s infinite;
    animation: shade ease-in-out 1.5s infinite;
    position: relative;
    width: 130%;
    height: 10%;
    margin: 0 2em;
    border-radius: 80% 60%;
    background-image: radial-gradient(ellipse at center, #000 0%, rgba(0,0,0, 0.6) 30%, rgba(0,0,0, 0) 70%);
    z-index: 1;
  }

  @-webkit-keyframes float {
    0% {
      -webkit-transform: translateY(0);
      transform: translateY(0);
    }
    50% {
      -webkit-transform: translateY(1em);
      transform: translateY(1em);
    }
    100% {
      -webkit-transform: translateY(0);
      transform: translateY(0);
    }
  }

  @keyframes float {
    0% {
      -webkit-transform: translateY(0);
      transform: translateY(0);
    }
    50% {
      -webkit-transform: translateY(1em);
      transform: translateY(1em);
    }
    100% {
      -webkit-transform: translateY(0);
      transform: translateY(0);
    }
  }

  @-webkit-keyframes shade {
    0% {
      -webkit-transform: translateY(0) translateX(1em);
      transform: translateY(0) translateX(1em);
      opacity: .5;
    }
    50% {
      -webkit-transform: translateY(1em) translateX(-1em) scale(.9);
      transform: translateY(1em) translateX(-1em) scale(.9);
      opacity: 1;
    }
    100% {
      -webkit-transform: translateY(0) translateX(1em);
      transform: translateY(0) translateX(1em);
      opacity: .5;
    }
  }

  @keyframes shade {
    0% {
      -webkit-transform: translateY(0) translateX(1em);
      transform: translateY(0) translateX(1em);
      opacity: .5;
    }
    50% {
      -webkit-transform: translateY(1em) translateX(-1em) scale(.9);
      transform: translateY(1em) translateX(-1em) scale(.9);
      opacity: 1;
    }
    100% {
      -webkit-transform: translateY(0) translateX(1em);
      transform: translateY(0) translateX(1em);
      opacity: .5;
    }
  }

  @-webkit-keyframes eye_shade {
    0% {
      opacity: .2;
    }
    50% {
      opacity: .5;
    }
    100% {
      opacity: .2;
    }
  }

  @keyframes eye_shade {
    0% {
      opacity: .2;
    }
    50% {
      opacity: .5;
    }
    100% {
      opacity: .2;
    }
  }
</style>
