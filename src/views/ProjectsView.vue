<template>
 <div class="projects pt-2">
  <div class="container">
      <div class="row mt-5 text-center">
        <div class="col-lg-4 mb-3" v-for="project in projects" :key="project.id">
          <div class="card text-bg-dark" style="width: 100%">
            <img
              :src="project.imageUrl"
              class="card-img-top"
              :alt="project.name"
            />
            <div class="card-body">
              <h5 class="card-title">{{ project.name }}</h5>
              <p class="card-text">
                {{ project.despcription }}
              </p>
              <a
                :href="project.github"
                target="_blank"
                class="btn btn-outline-light mx-3 animate__animated animate__zoomIn animate__delay-1s"
                >GitHub</a
              >
              <a
                :href="project.netlify"
                target="_blank"
                class="btn btn-outline-light mx-3 animate__animated animate__zoomIn animate__delay-2s"
                >Website</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
 </div>
</template>

<script>
export default {
  computed: {
    projects() {
      return this.$store.state.projects;
    },
  },
  mounted() {
    this.$store.dispatch("fetchProjects");
  },
};
</script>

<style scoped>

</style>