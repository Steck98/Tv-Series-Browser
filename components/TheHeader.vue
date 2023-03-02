<template>
  <div class="header">
    <div class="header__content">
        <div class="header__title">
          <h1 class="h1 column">Hundreds of TV Series to browse</h1>
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
    &__title{
      height: 50vh;
      background: rgba($font,0.8);
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
    color: $lightGreen;
    z-index: 1;
  }
}
.sticky {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
}
</style>
