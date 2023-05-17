<template>
  <div class="columns mt-1">
    <div class="column">
        <span
            v-for="(item, i) in items"
            :key="`chip-${i}`"
            class="tag is-rounded is-dark mx-2"
        >
          {{ item }}
        </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "chipsComponent",
  props: {
    items: {
      type: Array,
      required: true
    }
  }
}
</script>
