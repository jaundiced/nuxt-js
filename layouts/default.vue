<template>
  <div>
    <NavBar />
    <div class="container mx-auto">
      <Nuxt />
    </div>
    <Footer />
  </div>
</template>

<script>
import NavBar from '~/components/NavBar.vue'
import Footer from '~/components/Footer.vue'

export default {
  name: "AppLayout",
  components: {
    NavBar,
    Footer
  },
  head: {
    bodyAttrs: {
      class: "font-sans bg-blue-900",
    },
    link: [
      {
        rel: "stylesheet",
        href:
          "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.9.0/css/all.min.css",
      },
    ],
  },
}
</script>
