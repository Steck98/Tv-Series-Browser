<template>
  <div class="movies">
    <!-- TYTUŁ -->
    <div class="row movies__title">
      <h3 class="column">Find the Movie your Looking for</h3>
    </div>
    <div class="movies__content">
      <!-- FILTROWANIE -->
      <div
        class="columns movies__filtration small-10 medium-8"
        :class="{ active: toggleFiltration }"
      >
        <div class="movies__search">
          <div>Categories:</div>
          <div>
            <label for="search">Search:</label>
            <input type="text" class="search" id="search" />
          </div>
        </div>
        <!-- LISTA KATEGORII -->
        <div class="movies__categories">
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Horror</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Sci-fi</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Discovery</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Comedy</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Romantic</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>History</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Anime</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Action</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Thriller</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Musical</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Hentai</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Drammatic</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Drama</div>
            <input type="checkbox" />
          </div>
          <div class="movies__categorie small-4 medium-4 large-3">
            <div>Something</div>
            <input type="checkbox" />
          </div>
        </div>
      </div>
      <!-- STRZAŁKA DO OTWARCIA -->
      <div
        class="arrow"
        @click="toggleFiltration = !toggleFiltration"
        :class="{ activeArrow: toggleFiltration }"
      >
      ↓
      </div>
      <!-- COMPONENT Z CATEGORIAMI  -->
      <FilmCategoryList :category="`Horror`"/>
      <FilmCategoryList :category="`Discovery`"/>
      <FilmCategoryList :category="`Action`"/>
      <FilmCategoryList :category="`Comedy`"/>
    </div>
  </div>
</template>

<script>
import FilmCategoryList from '../../components/allSeries/FilmCategoryList.vue';

export default {
    data() {
        return {
            toggleFiltration: false,
        };
    },
    components: { FilmCategoryList }
};
</script>

<style lang="scss" scoped>
.movies {
  display: flex;
  flex-direction: column;
  justify-content: center;
  
  &__title {
    text-align: center;
    padding: rem(36px) 0;
  }
  &__content {
    display: flex;
    align-items: center;
    flex-direction: column;
    background-color: $font;
    width: 100%;
    -webkit-box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
  -moz-box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
  box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
  }
  &__filtration {
    display: none;
    justify-content: space-between;
    align-items: center;
    border: 2px solid $lightGreen;
    border-top: 0;
    border-bottom-left-radius: 15px;
    border-bottom-right-radius: 15px;
    padding: rem(12px);
    transition: 1s;
    height: 0%;
    overflow: hidden;
    width: 0%;
  }
  .active {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
    transition: 2s;
    
  }
  &__categories {
    padding: 0 rem(16px);
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    margin-top: rem(16px);
  }
  &__categorie{
    display: flex;
    align-items: center;
    margin-right: rem(36px);
    justify-content: space-between;
    @include tablet{
    margin-right: rem(64px);

    }
    input{
        margin-left: rem(6px);
        outline: none;
        background-color: $font;
        color: $lightGreen;
        border-color: $lightGreen;
    }

  }
  &__search {
    display: flex;
    flex-direction: column-reverse;
    justify-content: space-between;
    width: 100%;
    padding: 0 rem(16px);
    @include tablet{
        flex-direction: row;
    }
  }
  .search {
    background-color: $font;
    border: none;
    border-bottom: 1px solid $lightGreen;
    color: $lightGreen;
    outline: none;
  }
  label {
    margin-right: rem(8px);
  }
  .arrow {
    display: flex;
    justify-content: center;
    margin-top: 0;
    border-bottom-left-radius: 50px;
    border-bottom-right-radius: 50px;
    border: 2px solid $lightGreen;
    border-top: none;
    width: 11%;
    cursor: pointer;
    @include desktop{
        width: 4%;
    }
    
  }
  .activeArrow {
    transform: rotate(180deg);
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
    border-bottom: none;
    border-top: 2px solid $lightGreen;
    border-top-right-radius: 50px;
    border-top-left-radius: 50px;
  }
}

</style>
