<template>
  <div>
    <Hero :hero="data.home.hero" />
    <About :about="data.home.about" />
    <Services :services="data.home.services" />
    <Projects :projects="data.home.projects" />
    <Connect :connect="data.home.connect" />
    <Skills :skills="data.home.skills" />
    <TimeLine :timeline="data.hometimeline" />
    <Blog :blog="data.home.blog" />
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters(['data'])
  }
}
</script>

<style scoped>
</style>