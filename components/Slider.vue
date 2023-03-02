<template>
    <div>
      <glide :per-view="1" :options="glideOptions">
        <slide v-for="(slide, index) in slides" :key="index">
          <img :src="slide.image" alt="Slide Image">
          <h2>{{ slide.title }}</h2>
          <p>{{ slide.text }}</p>
        </slide>
      </glide>
    </div>
  </template>
  
  <script>
  import Glide from 'vue-glide-js'
  import 'vue-glide-js/dist/vue-glide.css'
  
  export default {
    components: {
      Glide,
      Slide: Glide.slide
    },
    data() {
      return {
        glideOptions: {
          type: 'slider',
          startAt: 0,
          autoplay: 2500,
          hoverpause: true,
          perView: 1
        },
        slides: [
          {
            image: 'https://via.placeholder.com/600x400',
            title: 'Slide 1',
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam viverra euismod odio, gravida pellentesque urna varius vitae.'
          },
          {
            image: 'https://via.placeholder.com/600x400',
            title: 'Slide 2',
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam viverra euismod odio, gravida pellentesque urna varius vitae.'
          },
          {
            image: 'https://via.placeholder.com/600x400',
            title: 'Slide 3',
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam viverra euismod odio, gravida pellentesque urna varius vitae.'
          }
        ]
      }
    }
  }
  </script>
  <style lang="scss" scoped></style>
  