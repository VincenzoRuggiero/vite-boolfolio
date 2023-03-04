<script>
export default {
  name: "ProjectCard",
  props: {
    img: String,
    title: String,
    description: String,
    id: Number,
    project: Object,
  },
};
</script>

<template>
  <div class="card">
    <div class="card-body">
      <h3 class="card-title">{{ title }}</h3>

      <p class="card-text">
        {{ description }}
      </p>

      <router-link
        :to="{ name: 'project', params: { id: `${id}` } }"
        class="btn btn-secondary"
        >Open</router-link
      >
    </div>
  </div>
</template>

<style lang="scss"></style>
