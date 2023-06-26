<template>
  <div class="card">
    <div class="card-image">
      <figure class="image is-4by3 is-preview">
        <img :src="project.images[0]" alt="Placeholder image">
      </figure>
    </div>
    <div class="card-content">
      <div class="media">
        <div class="media-content">
          <p class="title is-4 is-white">
            {{ project.title }}
          </p>
          <p class="mt-negative-4 is-white">
            {{ project.description }}
          </p>
        </div>
      </div>
      <div class="content mt-negative-2">
        <ul>
          <li v-for="(item, index) in project.items" :key="index" class="pl-2">
            {{ item }}
          </li>
        </ul>
      </div>
      <router-link :to="`/project/${project.slug}`" class="mt-6">
        Read More
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "card_component",
  props: {
    project: {
      type: Object,
      required: true,
    }
  }
}
</script>

