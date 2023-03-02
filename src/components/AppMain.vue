<template>
  <section>
    <div class="container">
      <div class="row">
        <div class="col-12">
          <h1>Projects:</h1>
        </div>

        <div class="col-4">
          <article class="card single-card" v-for="project in projects">
            {{ project.title }}
          </article>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";

export default {
  name: "AppMain",
  data() {
    return {
      projects: [],
      apiCall: "http://127.0.0.1:8000/api/projects/",
    };
  },

  methods: {
    getProjects() {
      axios
        .get(this.apiCall)
        .then((response) => {
          //   console.log(response.data.results);
          this.projects = response.data.results;
        })
        .catch(function (error) {
          // handle error
          console.warn(error);
        });
    },
  },

  created() {
    this.getProjects();
  },
};
</script>

<style lang="scss" scoped></style>
