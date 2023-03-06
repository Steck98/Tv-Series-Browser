<template>
  <div class="featured">
    <div class="row featured__container">
      <div class="columns small-12 medium-6 featured__content">
        <div class="h3 featured__title">Over 100+ Series to browse</div>
        <div class="featured__description">
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ea cum
          inventore suscipit labore, obcaecati iusto incidunt amet itaque
          numquam exercitationem natus error odit nostrum adipisci quod enim
          iure laborum. Natus! Lorem ipsum dolor sit amet consectetur
          adipisicing elit. Dolor, fugiat officiis! Nisi voluptate tenetur,
          perspiciatis necessitatibus minus earum quod tempore numquam aut vitae
          nam ipsam, totam fugit quasi, in natus. Lorem, ipsum dolor sit amet
          consectetur adipisicing elit. Iusto, quidem consequuntur distinctio
          qui illum facilis suscipit odio hic ut culpa, iure maxime. Nemo in cum
          laboriosam dignissimos, assumenda ipsam commodi!
        </div>
      </div>
      <div class="columns small-12 medium-6 featured__image-wrapper">
        <img src="" alt="" width="350" height="250" />
      </div>
    </div>
    <div class="row featured__container featured__container--right">
      <div
        class="columns small-12 medium-6 featured__content featured__content--right"
      >
        <div class="h3 featured__title">
          Search by Cathegory, platform, number of episodes and even more !
        </div>
        <div class="featured__description">
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ea cum
          inventore suscipit labore, obcaecati iusto incidunt amet itaque
          numquam exercitationem natus error odit nostrum adipisci quod enim
          iure laborum. Natus! Lorem ipsum dolor sit amet consectetur
          adipisicing elit. Dolor, fugiat officiis! Nisi voluptate tenetur,
          perspiciatis necessitatibus minus earum quod tempore numquam aut vitae
          nam ipsam, totam fugit quasi, in natus. Lorem, ipsum dolor sit amet
          consectetur adipisicing elit. Iusto, quidem consequuntur distinctio
          qui illum facilis suscipit odio hic ut culpa, iure maxime. Nemo in cum
          laboriosam dignissimos, assumenda ipsam commodi!
        </div>
      </div>
      <div
        class="columns small-12 medium-6 featured__image-wrapper featured__image-wrapper--right"
      >
        <img src="" alt="" width="350" height="250" />
      </div>
    </div>
    
  </div>
</template>
<script></script>
<style lang="scss" scoped>
.featured {
  background-color: $font;
  -webkit-box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
  -moz-box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
  box-shadow: 0 0 28px 0 rgba(2, 214, 53, 1);
  text-align: center;
  @include tablet {
    text-align: left;
  }
  &__container {
    display: flex;
    flex-direction: column;
    
    @include tablet {
      flex-direction: row;
    }
    &--right {
      flex-direction: row-reverse;
    }
  }
  &__content {
    padding: rem(32px) rem(16px);
    &--right {
      border-right: none;
      border-left: 1px dotted $lightGreen;
    }
  }
  &__image-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    border-left: 1px dotted $lightGreen;
    img {
      margin: rem(46px) 0;
      background-color: $darkGreen;
    }
    &--right {
      border-left: none;
    }
  }
  &__description {
    margin-top: rem(36px);
    color: #fff;
  }
}
</style>
