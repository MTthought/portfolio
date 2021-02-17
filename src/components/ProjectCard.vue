<template>
  <div class="project-card">
    <span>{{ project.category }}</span>
    <h4>{{ project.title }}</h4>
  </div>
</template>

<script>
export default {
  name: "ProjectCard",
  props: {
    project: Object
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.project-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}

.project-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>
