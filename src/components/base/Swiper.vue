<template>
  <span>
    <swiper
        class="swiper mt-negative-4"
        :options="swiperOptions"
    >
      <swiper-slide
          v-for="(image, i) in project.images"
          :key="i"
          :watchSlidesProgress="true"
      >
        <img
            class="image is-medium is-border-radius-10 has-border-white is-margin-auto mt-6 has-ipad-frame"
            :src="image" :alt="`Example Screen shot of the App ${project.title}`"
        >
      </swiper-slide>
    </swiper>
    <div class="swiper-button-prev is-top" slot="button-prev" />
    <div class="swiper-button-next is-top" slot="button-next" />
  </span>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

export default {
  name: "SwiperComponent",
  components: {
    Swiper,
    SwiperSlide,
  },
  props: {
    swiperOptions: {
      type: Object,
      required: true
    },
    project: {
      type: Object,
      required: true
    }
  }
}
</script>
