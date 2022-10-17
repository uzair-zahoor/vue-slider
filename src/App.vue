<template>
  <div>
    <SlideR class="slider" v-slot="{ currentslide }">
      <Slides v-for="(image, index) in images" :key="index">
        <div class="images" v-show="currentslide === index + 1">
          <img :src="require(`./assets/${image}.jpg`)" alt="" />
        </div>
      </Slides>
    </SlideR>
  </div>
</template>

<script>
import SlideR from "./components/Slider.vue";
import Slides from "./components/Slides.vue";
// import "./assets/pic1.jpg";
export default {
  name: "App",
  components: { SlideR, Slides },
  data() {
    return {
      // img: "pic1.jpg",
      images: ["pic1", "pic2", "pic3", "pic4"],
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
.slider {
  position: relative;
  width: 100%;
  max-height: 100vh;
  height: 100vh;
  /* transition: all 0.4s ease; */
}
.images {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  max-height: 100vh;
  height: 100vh;
}
img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
