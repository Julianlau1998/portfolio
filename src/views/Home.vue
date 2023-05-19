<template>
  <div class="home">
    <Welcome />
    <Projects />
    <Contact />
    <div class="section is-small" />
  </div>
</template>

<script>
import Welcome from "@/components/welcome/Welcome"
import Projects from "@/components/Projects/Projects"
import Contact from "@/components/contact/Contact"
export default {
  name: 'HomeView',
  components: { Welcome, Projects, Contact }
}
</script>
