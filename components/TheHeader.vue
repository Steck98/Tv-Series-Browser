<template>
  <div class="header">
    <div class="header__content">
        <div class="header__title">
          <h1 class="h1">Boxing Hall Of Fame</h1>
        </div>
        <div class="header__image">
          <img
            src="../assets/images/boxHeader.jpeg"
            alt=""
            width="1980"
            height="1420"
            :style="`transform: translateY(${parallax}px)`"
          />
        </div>
    </div>
    <Navigation ref="nav" :class="{ sticky: isSticky }"/>
  </div>
</template>
<script>
export default {
  data() {
    return {
      parallax: 0,
      isSticky: false,
      navPosition:{
        type: Number,
        default: 0
      }
    };
  },
  mounted() {
    this.navPosition = this.$refs.nav.$el.offsetTop
    console.log(this.navPosition)
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.parallax = -(window.pageYOffset * 1.7);
      if (window.pageYOffset > this.navPosition) {
        console.log( this.navPosition)
        this.isSticky = true;
      }
      if (window.pageYOffset < this.navPosition) {
        console.log( this.navPosition)
        this.isSticky = false;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.header {

    &__content{
        position: relative;
    }

  .h1 {
    text-align: center;
    display: flex;
    width: 100%;
    margin: 0 auto;
    position: absolute;
    height: 100%;
    justify-content: center;
    align-items: center;
    color: $darkRed;
    z-index: 1;
  }

  &__image {
    height: 60vh;
    background-color: rgba(0, 0, 0, 0.9);
    img {
      object-position: bottom;
      position: fixed;
      width: 100%;
      object-fit: cover;
      height: 100vh;
      z-index: -999;
    }
  }
}
.sticky {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
}
</style>
