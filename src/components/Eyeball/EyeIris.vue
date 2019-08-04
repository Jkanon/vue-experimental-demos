<template>
  <div class="eye_iris">
    <ul class="eye_ciliary">
      <li v-for="index in 9" :key="index" class="eye_ciliary_item" :style="getEyeCiliaryItemStyle(index)"><span></span></li>
    </ul>
    <ul class="eye_ciliary eye_ciliary_sub">
      <li v-for="index in 9" :key="index" class="eye_ciliary_item" :style="getEyeCiliaryItemStyle(index)"><span></span></li>
    </ul>
    <div class="eye_reflect"></div>
    <div class="eye_reflect eye_reflect_sec"></div>
    <div class="eye_reflect eye_reflect_sub"></div>
  </div>
</template>

<script>
export default {
  name: 'EyeIris',
  methods: {
    getEyeCiliaryItemStyle(index) {
      return { transform: `rotateZ(${(index - 1) * 5}deg)` }
    }
  }
}
</script>

<style scoped>
ol, ul {
  list-style: none;
}

ul,li {
  margin: 0;
  padding: 0;

}

.eye_iris {
  position: absolute;
  top: 15%;
  left: 15%;
  width: 50%;
  height: 50%;
  border-radius: 50%;
  box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.5) inset;
  background-image: radial-gradient(circle at center, #b86e29 32%, #94c7d4 42%, #1c0a24 200%);
  -webkit-animation: eye_iris_shade ease-in-out 1.5s infinite;
  animation: eye_iris_shade ease-in-out 1.5s infinite;
}

.eye_ciliary {
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transform: rotateZ(1deg);
}

.eye_ciliary_item {
  display: block;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 50%;
  margin-top: -50%;
}

.eye_ciliary_item span {
  display: block;
  width: 100%;
  height: 100%;
  position: absolute;
}

.eye_ciliary_item:before, .eye_ciliary_item:after, .eye_ciliary_item span:before, .eye_ciliary_item span:after {
  content: "";
  display: block;
  width: 100%;
  height: 100%;
  position: absolute;
  background-color: #000;
  opacity: 0.1;
}

.eye_ciliary_item:before {
  transform: scale(0.025, 0.7) rotate(45deg);
}

.eye_ciliary_item:after {
  transform: scale(0.7, 0.025) rotate(45deg);
}

.eye_ciliary_item span:before {
  transform: rotate(45deg) scale(0.025, 0.7) rotate(45deg);
}

.eye_ciliary_item span:after {
  transform: rotate(-45deg) scale(0.025, 0.7) rotate(45deg);
}

.eye_ciliary_sub {
  width: 60%;
  height: 60%;
  top: 20%;
  left: 20%;
}

.eye_ciliary_sub .eye_ciliary_item:before, .eye_ciliary_sub .eye_ciliary_item:after, .eye_ciliary_sub .eye_ciliary_item span:before, .eye_ciliary_sub .eye_ciliary_item span:after {
  opacity: 1;
}

.eye_reflect {
  position: absolute;
  top: 30%;
  left: 30%;
  width: 20%;
  height: 15%;
  border-radius: 50%;
  transform: rotate(-35deg);
  background-image: radial-gradient(circle at center, #fff 0%, #fff 40%, rgba(255,255,255,0) 100%);
  z-index: 2;
  opacity: .9;
}

.eye_reflect_sec {
  top: 58%;
  left: 50%;
  width: 12%;
  height: 6%;
  background-image: radial-gradient(ellipse at center, #fff 0%, #fff 10%, rgba(255,255,255,0) 100%);
  transform: rotate(35deg);
}

.eye_reflect_sub {
  width: 80%;
  height: 80%;
  top: 0;
  left: 0;
  margin-left: -10%;
  margin-top: -10%;
  background-image: none;
  background-color: rgba(255,255,255, .1);
  z-index: 3;
}

@-webkit-keyframes eye_iris_shade {
  0% {
    -webkit-box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.2) inset;
    box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.2) inset;
  }
  50% {
    -webkit-box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.5) inset;
    box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.5) inset;
  }
  100% {
    -webkit-box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.2) inset;
    box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.2) inset;
  }
}

@keyframes eye_iris_shade {
  0% {
    -webkit-box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.2) inset;
    box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.2) inset;
  }
  50% {
    -webkit-box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.5) inset;
    box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.5) inset;
  }
  100% {
    -webkit-box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.2) inset;
    box-shadow: 0 0 3px 1px rgba(0,0,0,0.4), 5px 5px 5px 0 rgba(0,0,0,0.2) inset;
  }
}
</style>
