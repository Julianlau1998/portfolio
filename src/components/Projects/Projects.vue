<template>
  <div class="section is-flex is-flex-direction-column secondary">
    <h1 class="header is-size-1 mb-5 mt-negative-5 mb-6">
      Projects
    </h1>
    <swiper
        class="swiper mb-6"
        :options="swiperOptions"
    >
      <swiper-slide
          v-for="(project, i) in projects"
          :key="i"
          :watchSlidesProgress="true"
      >
        <Card :project="project" />
      </swiper-slide>
    </swiper>

    <div class="swiper-button-prev is-top-auto" slot="button-prev"></div>
    <div class="swiper-button-next is-top-auto" slot="button-next"></div>
  </div>
</template>

<script>
import Card from "@/components/base/Card"
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'
import { projects } from '@/data/projects'

export default {
  name: "projects_component",
  components: { Card, Swiper, SwiperSlide },
  data () {
    return {
      projects: projects,
      swiperOptions: {
        slidesPerView: 1.2,
        spaceBetween: 20,
        navigation: {
          nextEl: "",
          prevEl: ""
        },
        breakpoints: {
          '1100': {
            slidesPerView: 3,
            slidesPerGroup: 3,
            spaceBetween: 20,
            navigation: {
              nextEl: ".swiper-button-next",
              prevEl: ".swiper-button-prev"
            }
          },
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
  }
}
</script>
