<template>
  <div>
    <header class="projects-hero">
      <div class="section-title" v-for="item in projects" :key="item.id">
        <h1 v-if="!isChinese">{{ item.engTitle }}</h1>
        <h1 v-else>{{ item.chnTitle }}</h1>
        <div class="underline"></div>
      </div>
    </header>
    <section class="section">
      <div class="section-center projects-page-center">
        <article class="single-project">
          <div class="project-container">
            <img src="/images/project-1.jpeg" alt="single project" />
            <a href="https://www.johnsmilga.com" class="project-icon">
              <i class="fas fa-home"></i>
            </a>
          </div>
          <div class="project-details">
            <h4>project name</h4>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum
              eveniet amet odit aperiam, provident cum possimus sapiente minus
              quos! Ipsum?
            </p>
            <div class="project-footer">
              <span>
                <i class="fab fa-github"></i>
              </span>
              <a href="https://www.github.com">source code</a>
            </div>
          </div>
        </article>
      </div>
    </section>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  data() {
    return {
      projects: []
    }
  },
  computed: {
    ...mapGetters(['isChinese', 'data'])
  },
  mounted() {
    this.projects = this.data.projects.main
  }
}
</script>

<style scoped>
</style>