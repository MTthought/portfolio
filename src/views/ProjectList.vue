<template>
  <div class="projects">
    <ProjectCard v-for="project in projects" :key="project.id" :project="project" />
  </div>
</template>

<script>
// @ is an alias to /src
import ProjectCard from "@/components/ProjectCard.vue";
import ProjectService from "@/Services/ProjectService.js"

export default {
  name: "ProjectList",
  components: {
    ProjectCard
  },
  data(){
    return {
      projects: null
    }
  },
  created(){
    ProjectService.getProjects()
    .then(response => this.projects = response.data)
    .catch(error => console.log(error))
  }
};
</script>

<style scoped>
.projects {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>