<template>
  <div class="section">
    <h1 class="header is-size-2">
      {{ project.title }}
    </h1>
    <p>
      {{ project.description }}
    </p>

    <a :href="`${project.link}`" class="button is-primary mt-5">
      Open app
      <i class="fas fa-arrow-right ml-3 mr-1 mt-1"></i>
    </a>

    <swiper
        class="swiper"
        :options="swiperOptions"
    >
      <swiper-slide
          v-for="(image, i) in project.images"
          :key="i"
          :watchSlidesProgress="true"
      >
        <img
            class="image is-medium is-border-radius-10 has-border-white is-margin-auto mt-6"
            :src="image" :alt="`Example Screen shot of the App ${project.title}`"
        >
      </swiper-slide>
    </swiper>
    <div class="swiper-button-prev" slot="button-prev"></div>
    <div class="swiper-button-next" slot="button-next"></div>

    <div v-if="project.playLink.length" class="mt-5">
      <a :href="`${project.playLink}`">
        <img class="is-badge google" alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png'/>
      </a>
      <a :href='`${project.appleLink}`'>
        <img class="is-badge apple" alt='Get it on the App Store' src='/img/appStoreBadge.svg'/>
      </a>
    </div>
  </div>
</template>

<script>
import { projects } from '@/data/projects'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

export default {
  name: "ProjectView",
  components: {
    Swiper,
    SwiperSlide
  },
  data () {
    return {
      projects: projects,
      project: {},
      swiperOptions: {
        slidesPerView: 1.2,
        spaceBetween: 20,
        navigation: {
          nextEl: "",
          prevEl: ""
        },
        breakpoints: {
          '700': {
            slidesPerView: 2,
            slidesPerGroup: 2,
            spaceBetween: 20,
            navigation: {
              nextEl: ".swiper-button-next",
              prevEl: ".swiper-button-prev"
            }
          }
        }
      }
    }
  },
  created() {
    this.project = this.projects.filter(project => project.slug === this.$route.params.slug)[0]
  }
}
</script>
