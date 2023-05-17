<template>
  <span>
    <div v-if="playLink.length && appleLink.length" class="mt-5">
      <a :href="`${playLink}`" target='_blank'>
        <img class="is-badge google" alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png'/>
      </a>
      <a :href='`${appleLink}`' target='_blank'>
        <img class="is-badge apple" alt='Get it on the App Store' src='/img/appStoreBadge.svg'/>
      </a>
    </div>
    <a class="mx-4" :href="githubLink" target='_blank'>
      <img
          src="/img/socials/github.svg"
          class="is-socials-icon is-big mt-4 ml-5"
          :class="{'mt-6 mr-5' : !playLink.length}"
      />
    </a>
  </span>
</template>

<script>
export default {
  name: "SocialLinks",
  props: {
    playLink: {
      type: String,
      required: true
    },
    appleLink: {
      type: String,
      required: true
    },
    githubLink: {
      type: String,
      required: true
    }
  }
}
</script>
