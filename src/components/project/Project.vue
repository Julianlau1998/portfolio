<template>
  <div class="section">
    <h1 class="header is-size-2">
      {{ project.title }}
    </h1>
    <p>
      {{ project.description }}
    </p>
    <Chips :items="project.technologies" />

    <a :href="`${project.link}`" class="button is-primary mt-1" target="_blank">
      Open app
      <i class="fas fa-arrow-right ml-3 mr-1 mt-1"></i>
    </a>

    <Swiper
        :swiper-options="swiperOptions"
        :project="project"
    />
    <Links
        :play-link="project.playLink"
        :apple-link="project.appleLink"
        :github-link="project.githubLink"
    />
  </div>
</template>

<script>
import Chips from "@/components/base/Chips"
import Swiper from "@/components/base/Swiper"
import Links from "@/components/base/Links"

export default {
  name: "ProjectComponent",
  components: {
    Chips,
    Swiper,
    Links
  },
  props: {
    project: {
      type: Object,
      required: true
    }
  },
  data () {
    return {
      swiperOptions: {
        slidesPerView: 1.3,
        spaceBetween: 10,
        navigation: {
          nextEl: "",
          prevEl: ""
        },
        breakpoints: {
          '450': {
            slidesPerView: 1.5,
            slidesPerGroup: 2,
            spaceBetween: 45,
            navigation: {
              nextEl: ".swiper-button-next",
              prevEl: ".swiper-button-prev"
            }
          },
          '775': {
            slidesPerView: 2,
            slidesPerGroup: 2,
            spaceBetween: 45,
            navigation: {
              nextEl: ".swiper-button-next",
              prevEl: ".swiper-button-prev"
            }
          },
          '1100': {
            slidesPerView: 2,
            slidesPerGroup: 2,
            spaceBetween: 60,
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
