<template>
  <div class="navigation">
    <!-- Mobile -->
    <div
      class="navigation__hamburger"
      @click="toggleNavigation"
    >
      <div
        class="navigation__hamburger-bar"
        :class="navigationOpen ? 'navigation__hamburger-bar--open' : ''"
      ></div>
      <div
        class="navigation__hamburger-bar"
        :class="navigationOpen ? 'navigation__hamburger-bar--open' : ''"
      ></div>
      <div
        class="navigation__hamburger-bar"
        :class="navigationOpen ? 'navigation__hamburger-bar--open' : ''"
      ></div>
    </div>
    <div class="navigation__mobile " :class="navigationOpen ? 'navigation__mobile--open' : ''">
      <nuxt-link
          v-for="(item, index) in navigation.navigationItems"
          :key="index"
          class="navigation__mobile-list-item h3"
          :to="`/${item.url}/`"
        >
          {{ item.navItem }}
        </nuxt-link>
    </div>
    <!-- Desktop -->
    <div class="row navigation__desktop">
      <div class="navigation__list columns medium-8 medium-offset-2">
        <nuxt-link
          v-for="(item, index) in navigation.navigationItems"
          :key="index"
          class="navigation__list-item h5"
          :to="`/${item.url}/`"
        >
          {{ item.navItem }}
        </nuxt-link>
      </div>
    </div>
  </div>
</template>
<script>
import data from "../static/header.json";
export default {
  data() {
    return {
      navigation: data,
      navigationOpen: false,
    };
  },
  methods: {
    toggleNavigation() {
      console.log(this.navigationOpen);
      this.navigationOpen = !this.navigationOpen;
    },
  },
};
</script>

<style lang="scss" scoped>
.navigation {
  z-index: 900;
  background: linear-gradient(
    12deg,
    $darkRed,
    rgba(135, 7, 25, 1) 31%,
    rgba(27, 27, 27, 1) 64%
  );
  &__list {
    @include tablet {
      display: flex;
      justify-content: space-around;
      text-transform: uppercase;
      color: #fff;
      padding: rem(20px) 0;
      &-item {
        margin: 0 rem(10px);
        &:hover {
          color: $lightRed;
          transform-origin: 1.5;
        }
      }
    }
  }
  &__desktop{
    display: none;
    @include tablet {
      display: block;
      
    }
  }
  &__mobile{
    position: fixed;
    top: 0;
    display: flex;
    width: 100%;
    align-items: center;
    flex-direction: column;
    background-color: $darkRed;
    padding: 10vh 0 9vh 0;
    top: -60%;
    transition: 0.5s;
    z-index: 99998;
    a{
      margin: rem(15px) 0;
    }
    &--open{
      top: 0;
      transition: 0.5s;
    }
  }
  &__hamburger {
    position: fixed;
    top: rem(15px);
    right: rem(15px);
    z-index: 99999;
    &-bar {
      width: rem(50px);
      margin: rem(8px) 0;
      border-left: 25%;
      height: rem(7px);
      background-color: $darkRed;
      transform:translateX(0);
      transition: 1s;

      &--open {
        transform: translate(0,10px) rotate(45deg);
        background-color: $font;
        transition: 0.5s;
      }
      &--open:nth-child(2) {
        transform: translate(0,-5px) rotate(315deg);
      }
      &--open:nth-child(3) {
        transform: translateX(130%);
      }
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
