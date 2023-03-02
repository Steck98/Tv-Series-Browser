<template>
  <div class="contact">
    <div class="row contact__content-wrapper">
      <div class="contact__content columns small-10">
        <h2>Welcome in contact section, I'm glad u made it here</h2>
        <h5>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quasi fuga
          deserunt obcaecati cumque? Quibusdam repellat voluptatem cumque.
          Placeat voluptatum culpa, voluptas saepe, natus maiores ullam error
          perferendis, recusandae itaque voluptatibus?
        </h5>
        <div>
          <button class="button" @click="sendEmail" :key="emailLinkKey">
            I invite you to contact me
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  layout: "noHeader",

  data() {
    return {
      emailLink: "",
      emailLinkCounter: 0,
    };
  },
  computed: {
    emailLinkKey() {
      return `emailLink_${this.emailLinkCounter}`;
    },
  },
  methods: {
    sendEmail() {
      const emailAddress = "steczkiewicz1998@Gmail.com";
      const subject = "Contact";
      const body = "Hi there! I would like to contact you...";

      const mailToUrl = `mailto:${emailAddress}?subject=${encodeURIComponent(
        subject
      )}&body=${encodeURIComponent(body)}`;

      window.location.href = mailToUrl;

      this.emailLinkCounter++;
    },
  },
};
</script>
<style lang="scss" scoped>
.contact {
  height: 80vh;
  display: flex;
  &__content-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  &__content {
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: rem(65px) rem(15px);
    -webkit-box-shadow: 0 0 28px 0px rgba(2, 214, 53, 1);
  -moz-box-shadow: 0 0 28px 0px rgba(2, 214, 53, 1);
  box-shadow: 0 0 28px 0px rgba(2, 214, 53, 1);
        background-color: $font;
       
  }
}
</style>
