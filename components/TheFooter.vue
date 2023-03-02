<template>
  <div class="footer">
    <div class="row footer__contact">
      <div
        class="columns small-10 small-offset-1 medium-5 medium-offset-1 footer__contact-info h5"
      >
        <div>{{ contact.name }} {{ contact.surname }}</div>
        <div>{{ contact.phone }}</div>
        <div>{{ contact.email }}</div>
        <div>{{ contact.location }}</div>
      </div>
      <div
        class="columns small-10 small-offset-1 medium-5 medium-offset-0 footer__social-media"
      >
        <a
          class="footer__icons-wrapper"
          :href="media.url"
          target="_blank"
          v-for="(media, index) in contact.socialMedia"
          :key="`${media.name}+_${index}`"
        >
          <div>
            <img
              class="icon"
              :src="require(`@/assets/svg/${media.src}`)"
              :alt="media.name"
              width="60px"
              height="60px"
            />
          </div>
        </a>
      </div>
    </div>
    <div class="row footer__copyright credits">
      <div>Designed and developed By Rafał Steczkiewicz</div>
    </div>
  </div>
</template>

<script>
import data from "../static/contact.json";

export default {
  data() {
    return {
      contact: data.contactData,
    };
  },
};
</script>

<style lang="scss" scoped>
.footer {
  background: linear-gradient(
    12deg,
    $darkGreen,
    rgba(27, 27, 27, 1) 64%
  );
  &__contact {
    border-bottom: 0.5px solid $font;
  }
  color: #fff;
  &__contact-info {
    margin-top: rem(24px);
    padding-left: rem(36px);
  }
  &__social-media {
    display: flex;
    justify-content: center;
    align-items: flex-end;
    @include tablet {
      justify-content: flex-end;
    }
  }
  &__icons-wrapper {
    margin: rem(5px) rem(15px);
  }
  .icon {
    width: 60px;
    height: 60px;
  }

  &__copyright {
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
