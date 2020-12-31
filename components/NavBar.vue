<template>
  <nav
    class="flex items-center justify-between flex-wrap bg-blue-900 p-6 fixed w-full z-10 pin-t"
  >
    <div class="flex items-center flex-no-shrink text-white mr-6">
      <i class="far fa-clipboard fa-2x text-orange-400"></i>
      <span class="ml-1 text-lg text-blue-200 font-semibold ml-4">StoryBlok</span>
    </div>
    <div class="block lg:hidden" v-show="this.$route.name == 'index'">
      <i class="fas fa-bars fa-2x text-orange-400" @click="toggleMenu"></i>
    </div>

    <div
      id="nav-content"
      class="w-full flex-grow lg:flex lg:items-center lg:w-auto hidden lg:block pt-6 lg:pt-0"
      v-show="this.$route.name == 'index'"
    >
      <ul
        class="list-reset lg:flex justify-end flex-1 items-center font-semibold"
      >
        <li>
          <a @click="navigateToAnchor('home', 'teaser')" :class="(activeNavSelection == 'home') ? activeLinkListItem :  inActiveLinkListItem">Home</a>
        </li>
        <li>
          <a @click="navigateToAnchor('feature-grid','feature-grid')" :class="(activeNavSelection == 'feature-grid') ? activeLinkListItem :  inActiveLinkListItem">Features</a>
        </li>
        <li>
          <a @click="navigateToAnchor('featured-articles','featured-articles')" :class="(activeNavSelection == 'featured-articles') ? activeLinkListItem :  inActiveLinkListItem">Articles</a>
        </li>
        <li>
          <a @click="navigateToAnchor('featured-videos','featured-videos')" :class="(activeNavSelection == 'featured-videos') ? activeLinkListItem :  inActiveLinkListItem">Videos</a>
        </li>
      </ul>
    </div>
    <div id="articleSummaryNav" v-show="this.$route.name != 'index'">
      <ul class="list-reset lg:flex justify-end flex-1 items-center font-semibold">
        <li><nuxt-link to="/" :class="inActiveLinkListItem">Home</nuxt-link></li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      activeNavSelection: "home",
      activeLinkListItem: "text-blue-600 pr-4",
      inActiveLinkListItem: "text-blue-200 pr-4",
    }
  },
  methods: {
    toggleMenu() {
      document.getElementById("nav-content").classList.toggle("hidden")
    },
    navigateToAnchor(link, anchorName) {
      console.log(`navigateToAnchor: link value = ${link}`)
      this.activeNavSelection = link;
      document.getElementById(anchorName).scrollIntoView(); 
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
