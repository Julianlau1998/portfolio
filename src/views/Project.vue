<template>
  <Project :project="project" />
</template>

<script>
import Project from "@/components/project/Project"
import { projects } from "@/data/projects"

export default {
  name: "ProjectView",
  components: { Project },
  data () {
    return {
      project: {},
      projects: projects
    }
  },
  created() {
    this.project = this.projects.filter(project => project.slug === this.$route.params.slug)[0]
  }
}
</script>
