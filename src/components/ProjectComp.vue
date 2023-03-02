<script>
export default {
  name: "ProjectComp",
  props: {
    img: String,
    title: String,
    description: String,
  },
};
</script>

<template>
  <div class="card">
    <div class="bg-image">
      <img :src="img" />
    </div>

    <div class="card-body">
      <h3 class="card-title">{{ title }}</h3>

      <p class="card-text">
        {{ description }}
      </p>
      <a href="" class="btn btn-secondary">Open</a>
    </div>
  </div>
</template>

<style lang=""></style>
