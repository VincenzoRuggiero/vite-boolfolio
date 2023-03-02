<script>
import axios from "axios";
import ProjectComp from "./ProjectComp.vue";

export default {
  name: "AppMain",
  components: {
    ProjectComp,
  },
  data() {
    return {
      projects: [],
      projectsApi: "http://127.0.0.1:8000/api/projects/",
    };
  },

  methods: {
    getProjects() {
      axios
        .get(this.projectsApi)
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

<template>
  <section>
    <div class="container">
      <div class="row">
        <h1>Projects</h1>
      </div>

      <div class="wrapper d-flex flex-wrap justify-content-center">
        <div class="col-3 m-3" v-for="project in projects">
          <div class="card">
            <div class="bg-image">
              <img :src="img" />
            </div>

            <div class="card-body">
              <h3 class="card-title">{{ project.title }}</h3>

              <p class="card-text">
                {{ project.description }}
              </p>
              <a href="" class="btn btn-secondary">Open</a>
            </div>
          </div>
          <!-- <ProjectComp
            :img="project.image"
            :title="project.title"
            :description="project.description" /> -->
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped></style>
