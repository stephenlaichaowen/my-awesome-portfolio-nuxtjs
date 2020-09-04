<template>
  <div>
    <Navbar @sidenavToggle="displaySidenav = !displaySidenav" />
    <Sidebar :open="displaySidenav" @close="displaySidenav = false" />
    <nuxt />
    <Footer />
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Portfolio | Stephen Lai'
    }
  },
  data() {
    return {
      displaySidenav: false
    }
  }
}
</script>

<style>
.fade-enter-active, .fade-leave-active {
  transition: opacity .3s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}

li a:hover,
li a:active,
li a.nuxt-link-exact-active {
  color: var(--clr-primary-5);
}

.fa-language {
  cursor: pointer;
}
</style>
