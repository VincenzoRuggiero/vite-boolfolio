<template>
  <div class="container">
    <h2 class="text-center text-white text-uppercase py-5">All projects</h2>
    <div class="row d-flex justify-content-center g-3">
      <ProjectCard
        v-for="project in projects"
        :key="project.id"
        class="col-4 mx-2"
        :title="project.title"
        :description="project.description"
        :id="project.id" />
    </div>
  </div>
</template>

<script>
import ProjectCard from "../components/ProjectCard.vue";

import axios from "axios";

export default {
  name: "ProjectsList",
  components: {
    ProjectCard,
  },
  data() {
    return {
      projects: [],
      urlAddress: "http://127.0.0.1:8001",
    };
  },
  methods: {
    getProjects() {
      axios.get(this.urlAddress + "/api/projects/").then((response) => {
        console.log(response.data.results);
        this.projects = response.data.results;
      });
    },
  },
  created() {
    this.getProjects();
  },
};
</script>

<style lang=""></style>
