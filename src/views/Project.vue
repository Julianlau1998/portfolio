<template>
  <div class="section">
    <h1 class="header is-size-2">
      {{ project.title }}
    </h1>
    <p>
      {{ project.description }}
    </p>
    <Chips :items="project.technologies" />

    <a :href="`${project.link}`" class="button is-primary mt-1">
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
import { projects } from '@/data/projects'
import Chips from "@/components/base/Chips"
import Swiper from "@/components/base/Swiper"
import Links from "@/components/base/Links"

export default {
  name: "ProjectView",
  components: {
    Chips,
    Swiper,
    Links
  },
  data () {
    return {
      projects: projects,
      project: {},
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
  },
  created() {
    this.project = this.projects.filter(project => project.slug === this.$route.params.slug)[0]
  }
}
</script>
