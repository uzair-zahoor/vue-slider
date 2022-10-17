<template>
  <!-- <h2>Hello from slides</h2> -->
  <div class="slide">
    <transition name="slide">
      <slot></slot>
    </transition>
  </div>
</template>
<script>
export default {
  name: "SlidesR",
};
</script>
<style scoped>
.slide-enter-active,
.slide-leave-active {
  transition: all 0.6s ease;
}
.slide-enter-from,
.slide-leave-to {
  opacity: 0.4;
}
.slide-enter-to,
.slide-leave-from {
  opacity: 1;
}
</style>
