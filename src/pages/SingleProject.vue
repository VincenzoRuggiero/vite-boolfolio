<script>
import ProjectCard from "../components/ProjectCard.vue";
import axios from "axios";

export default {
  name: "SingleProject",
  data() {
    return {
      project: null,
      urlAddress: "http://127.0.0.1:8001",
    };
  },
  methods: {
    getProject() {
      axios
        .get(this.urlAddress + `/api/projects/${this.$route.params.id}`)
        .then((response) => {
          console.log(response.data.results);
          this.project = response.data.results;
        })
        .catch(function (error) {
          console.warn(error);
        });
    },
  },
  created() {
    this.getProject();
  },
};
</script>

<template>
  <div>
    <ProjectCard :project="project" />
  </div>
</template>

<style lang=""></style>
