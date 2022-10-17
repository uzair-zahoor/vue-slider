<template>
  <!-- <h2>Hello from slider</h2> -->
  <div class="slider">
    <slot :currentslide="currentslide"></slot>
    <div class="navigation">
      <div class="left" @click="prev"><h2>Prev</h2></div>
      <div class="right" @click="nextslide"><h2>Next</h2></div>
    </div>
  </div>
</template>
<script>
export default {
  name: "SlideR",
  data() {
    return {
      currentslide: 1,
      getslidecount: null,
    };
  },
  methods: {
    nextslide() {
      if (this.currentslide === this.getslidecount) {
        this.currentslide = 1;
        return;
      }
      this.currentslide += 1;
    },
    prev() {
      if (this.currentslide === 1) {
        this.currentslide = this.getslidecount;
        return;
      }
      this.currentslide -= 1;
    },
    autoplay() {
      setInterval(() => {
        this.nextslide();
      }, 5000);
    },
  },
  //   created() {},
  mounted() {
    this.getslidecount = document.querySelectorAll(".slide").length;
    this.autoplay();
    console.log(this.getslidecount);
  },
};
</script>
<style scoped>
.navigation {
  position: absolute;
  color: white;
  top: 50%;
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 0px 20px;
}
.left,
.right {
  cursor: pointer;
}
</style>
