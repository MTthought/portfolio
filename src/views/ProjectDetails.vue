<template>
  <div v-if="project">
    <h1>{{ project.title }}</h1>
    <p>{{ project.time }} on {{ project.date }} @ {{ project.location }}</p>
    <p>{{ project.description }}</p>
  </div>
</template>

<script>
import ProjectService from '@/Services/ProjectService.js'

export default{
    props: ['id'],
    data(){
        return{
            project: null
        }
    },
    created(){
        ProjectService.getProject(this.id)
        .then(response => this.project = response.data)
        .catch(error => console.log(error))
    }
}
</script>