<template>
  <div class="films">
    <div class="row films__category-title">
      <!-- GLOWNA KATEGORIA -->
      <h3>{{ category }}</h3>
    </div>
    <!-- LISTA FILMÓW -->
    <div class="films__list">
      <vue-glide :perView="5" :gap="30" :rewind="true">
        <vue-glide-slide v-for="i in 24" :key="i">
          <FilmCard />
        </vue-glide-slide>
        <template slot="control">
          <button data-glide-dir="<">Prev</button>
          <button data-glide-dir=">">Next</button>
        </template>
      </vue-glide>
    </div>
  </div>
</template>

<script>
import { Glide, GlideSlide } from "vue-glide-js";
import FilmCard from "./FilmCard.vue";
export default {
  data() {
    return {
      
    };
  },
  props: {
        category: {
          type: String,
          default:"",
          required: true,
        },
      },

  components: {
    [Glide.name]: Glide,
    [GlideSlide.name]: GlideSlide,
    FilmCard,
  },
};
</script>

<style lang="scss" scoped>
.films {
  width: 100%;
  height: 100%;
    margin-top: rem(64px);

  &__category-title {
    justify-content: center;
  }

  &__list {
    margin: 0 rem(26px);
  }
  div[data-glide-el="controls"]{
    font-size: 50px;
  }
}
</style>
