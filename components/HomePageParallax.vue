<template>
  <div class="parallax-container">
    <div class="parallax-background">
     
    </div>
  </div>
</template>

<script>
export default {
    data() {
  return {
    scrollPosition: 0
  };
},
  computed: {
    backgroundPosition() {
      return {
        transform: `translateY(${this.scrollPosition * -0.5}px)`,
      };
    },
  },
  watch: {
    scrollPosition() {
      this.updateBackgroundPosition();
    },
  },
  mounted() {
    this.updateBackgroundPosition();
    window.addEventListener("scroll", this.updateBackgroundPosition);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.updateBackgroundPosition);
  },
  methods: {
    updateBackgroundPosition() {
      this.scrollPosition = window.pageYOffset;
    },
  },
};
</script>

<style lang="scss" scoped>
.parallax-container {
  height: 500px;
  position: relative;
}

.parallax-background {
  background: url("../assets/images/parallax.jpg");
  position: fixed;
  width: 100%;
  height: 100vh;
  z-index: -99999;
  bottom: 0;
}

.parallax-background img {
  width: 100%;
}
</style>
