<template>
  <section class="section single-page">
    <div v-for="item in contact" :key="item.id">
      <div class="section-title">
        <h1 v-if="!isChinese">{{ item.engTitle }}</h1>
        <h1 v-else>{{ item.chnTitle }}</h1>
        <div class="underline"></div>
      </div>
      <div class="section-center page-info">
        <p>
          <span v-if="!isChinese">{{ item.engContent }}</span>
          <span v-else>{{ item.chnContent }}</span>          
          <a href="mailto:email@email.com">@your_email</a>
        </p>
      </div>
    </div>
  </section>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  data() {
    return {
      contact: []
    }
  },
  computed: {
    ...mapGetters(['isChinese', 'data'])
  },
  mounted() {
    this.contact = this.data.contact.main
  },
}
</script>

<style scoped>
</style>