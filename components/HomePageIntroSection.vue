<template>
  <div class="intro">
    <div class="row intro__container">
      <div class="intro__content columns small-10 medium-8">
        <div class="intro__title h3">
          Find the TV Series your looking for and discover new ones
        </div>
        <div class="intro__description">
          Jump into the immersive world of TV series, find the one that interest
          you the most or maybe discover some new ones, app is designed to be
          simple and easy in use
        </div>
      </div>
    </div>
  </div>
</template>

<script></script>

<style lang="scss" scoped>
.intro {
  background-color: #000;
  &__container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding-top: rem(126px);
    padding-bottom: rem(126px);
  }
  &__content {
    padding: rem(30px) rem(30px);
    -webkit-box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
    -moz-box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
    box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
    background-color: $font;
    border: 0.5px solid $font;
    border-radius: 15px;
  }
  &__title {
    color: $lightGreen;
  }
  &__description {
    margin-top: rem(36px);
    color: #fff;
  }
}
</style>
