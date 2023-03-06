<template>
    <div class="numbers">
        <div class="row numbers__wrapper">
            <div class="numbers__number h4">1.000.000 <br /> Users</div>
            <div class="numbers__number h4">100+ <br /> Series</div>
            <div class="numbers__number h4">4.5/5 <br /> Rating</div>
        </div>
        <div class="row numbers__button-wrapper">
            <nuxt-link to="allSeries/" class="numbers__button button">See More -></nuxt-link>
        </div>
    </div>
</template>

<script>

</script>

<style lang="scss" scoped>
.numbers{
    padding: rem(86px);
    -webkit-box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
  -moz-box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
  box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
        background-color: $font;
    &__wrapper{
        display: flex;
        justify-content: space-evenly;
    }
    &__number{
        margin-bottom: rem(15px);
        text-align: center;
        width: rem(250px);
        height: rem(250px);
        border-radius: 100%;
        border: 2px solid $lightGreen;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    &__button-wrapper{
        justify-content: center;
        margin-top: rem(36px);
    }
}

</style>