<template>
  <v-app>
    <Header />
    <Hero v-if="isHome" />
    <v-container fill-height class="d-md-flex global-bg">
      <slot />
    </v-container>
    <Footer />
  </v-app>
</template>

<script>
import Header from "../components/Header"
import Hero from "../components/Hero"
import Footer from "../components/Footer"

export default {
  components: {
    Header,
    Hero,
    Footer,
  },
  computed: {
    isHome() {
      return this.$route.path === "/"
    },
  },
}
</script>

<style>
  .global-bg {
    background: radial-gradient(papayawhip, snow, white);
  }
</style>
