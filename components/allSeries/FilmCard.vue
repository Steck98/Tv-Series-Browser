<template>
  <nuxt-link class="film" to="/" target="_blank">
    <div class="row film__tile-content">
      <div class="film__image">
        <img
          src="../../assets/images/parallax.jpg"
          alt="Title"
          width="350"
          height="450"
        />
      </div>
      <h5 class="film__title">Tytuł Filmu</h5>
      <div class="film__description" :class="{ active: toggleReadMore }">
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Beatae amet
        ipsam quos nemo deleniti vero quasi delectus, voluptatibus quo
        exercitationem rerum maxime maiores adipisci eum nostrum aspernatur.
        Iure, quasi quibusdam.
      </div>
      <button class="film__read-more" @click="toggleReadMore = !toggleReadMore">
        Czytaj Więcej
      </button>
      <button v-if="favorite" class="film__add-favorite">❤</button>
    </div>
</nuxt-link>
</template>

<script>
import FilmCard from "./FilmCard.vue";
export default {
  data() {
    return {
      toggleReadMore: false,
    };
  },
  props: {
    favorite: {
      type: Boolean,
      default: true,
      required: false,
    },
  },
  components: { FilmCard },
};
</script>

<style lang="scss">
.film {
  &__tile-content {
    background-color: #000;
    display: flex;
    flex-direction: column;
    padding: rem(24px);
    overflow: hidden;
    flex-wrap: nowrap;
    border-radius: 15px;
    transition: 0.5s;
    -webkit-box-shadow: 0 0 16px 0 rgb(1, 124, 29);
    -moz-box-shadow: 0 0 16px 0 rgb(1, 124, 29);
    box-shadow: 0 0 16px 0 rgb(1, 124, 29);
    &:hover {
      background-color: $font;
      transform: scale(1.1);
      transition: 0.5s;
      border: 1px solid;
      -webkit-box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
      -moz-box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
      box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
    }
  }

  &__image {
    aspect-ratio: 1/1;

    img {
      object-fit: cover;
      height: 100%;
    }
  }
  &__description {
    font-size: rem(14px);
    max-height: rem(128px);
    overflow: hidden;
  }

  &__title {
    margin: 0;
  }
  &__read-more {
    z-index: 99;
    font-size: rem(12px);
    text-decoration: underline;
    margin-top: rem(8px);
    text-align: left;
  }
  &__add-favorite {
    position: absolute;
    color: #ff1e43;
  }
  .active {
    max-height: 100%;
  }
}
.glide__slides,
.glide__track {
  overflow: visible;
}
</style>
