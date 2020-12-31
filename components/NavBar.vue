<template>
  <nav
    class="flex items-center justify-between flex-wrap bg-blue-900 p-6 fixed w-full z-10 pin-t"
  >
    <div class="flex items-center flex-no-shrink text-white mr-6">
      <i class="far fa-clipboard fa-2x text-orange-400"></i>
      <span class="ml-1 text-lg text-blue-200 font-semibold ml-4">StoryBlok</span>
    </div>
    <div class="block lg:hidden">
      <i class="fas fa-bars fa-2x text-orange-400" @click="toggleMenu"></i>
    </div>

    <div
      id="nav-content"
      class="w-full flex-grow lg:flex lg:items-center lg:w-auto hidden lg:block pt-6 lg:pt-0"
    >
      <ul
        class="list-reset lg:flex justify-end flex-1 items-center font-semibold"
      >
        <li
          :class="
            this.$route.name == 'index'
              ? activeLinkListItem
              : inActiveLinkListItem
          "
        >
          <nuxt-link class="text-blue-200" to="/">Home</nuxt-link>
        </li>
        <li
          :class="
            this.$route.name == 'services'
              ? activeLinkListItem
              : inActiveLinkListItem
          "
        >
          <nuxt-link class="text-blue-200" to="/services">Services</nuxt-link>
        </li>
        <li
          :class="
            this.$route.name == 'projects'
              ? activeLinkListItem
              : inActiveLinkListItem
          "
        >
          <nuxt-link class="text-blue-200" to="/projects">Projects</nuxt-link>
        </li>
        <li
          :class="
            this.$route.name == 'team'
              ? activeLinkListItem
              : inActiveLinkListItem
          "
        >
          <nuxt-link class="text-blue-200" to="/team">Team</nuxt-link>
        </li>
        <li
          :class="
            this.$route.name == 'about'
              ? activeLinkListItem
              : inActiveLinkListItem
          "
        >
          <nuxt-link class="text-blue-200" to="/about">About</nuxt-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      activeLinkListItem: "mr-6 p-1 border-b-2 border-amber-500",
      inActiveLinkListItem: "mr-6 p-1",
      showMenu: false,
    }
  },
  methods: {
    toggleMenu() {
      document.getElementById("nav-content").classList.toggle("hidden")
    },
  },
}
</script>
<style scoped>
.nuxt-link-exact-active {
  cursor: default;
  @apply text-blue-400;
}
</style>
