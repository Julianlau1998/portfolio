<template>
  <div class="section primary is-flex is-flex-direction-column is-justify-content-center is-align-items-center">
    <social />
    <h1 class="header is-size-1 mt-negative-6">
      Julian Lau
    </h1>
    <h4 class="header is-size-5 is-size-6-mobile mt-3 is-full-width">
      Web Developer
    </h4>
    <i class="fas fa-arrow-down is-down-arrow is-pointer is-bottom-center" @click="scrollDown" />
  </div>
</template>

<script>
import social from "@/components/base/Social"
export default {
  name: "welcome_component",
  components: { social },
  methods: {
    scrollDown () {
      window.scrollTo({ top: 1000, behavior: "smooth"})
    }
  }
}
</script>
