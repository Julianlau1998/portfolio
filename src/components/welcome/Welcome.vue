<template>
  <div class="section primary is-flex is-flex-direction-column is-justify-content-center is-align-items-center">
    <social />
    <h1 class="header is-size-1">
      Julian Lau
    </h1>
    <h4 class="header is-size-5 mt-3">
      Web Developer
    </h4>
    <i class="fas fa-arrow-down is-down-arrow" />
  </div>
</template>

<script>
import social from "@/components/base/Social"
export default {
  name: "welcome_component",
  components: { social }
}
</script>
