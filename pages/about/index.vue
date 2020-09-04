<template>
  <section class="section single-page">
    <div v-for="item in about" :key="item.id">
      <div class="section-title">
        <h1 v-if="!isChinese">{{ item.engTitle }}</h1>
        <h1 v-else>{{ item.chnTitle }}</h1>
        <div class="underline"></div>
      </div>
      <div class="section-center page-info" v-for="item in about" :key="item.id">
        <p v-if="!isChinese">
          {{ item.engContent }}
          <a
            href="https://www.youtube.com/channel/UCMZFwxv5l-XtKi693qMJptA"
          >coding addict</a>
        </p>
        <p v-else>
          {{ item.chnContent }}
          <a
            href="https://www.youtube.com/channel/UCMZFwxv5l-XtKi693qMJptA"
          >coding addict</a>
        </p>
      </div>
    </div>
  </section>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  head() {
    return {
      title: 'About | Stephen Lai'
    }
  },
  data() {
    return {
      // about: []
    }
  },
  computed: {
    ...mapGetters(['isChinese'])
  },
  async asyncData({ $axios }) {
    const data = await $axios.$get('/data.json')
    // this.about = data.about.main
    return { about: data.about.main }
  }
}
</script>

<style scoped>
</style>