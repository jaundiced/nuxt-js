<template>
  <nav
    class="flex items-center justify-between flex-wrap bg-blue-900 p-6 fixed w-full z-10 pin-t"
  >
    <div class="flex items-center flex-no-shrink text-white mr-6">
      <i class="far fa-clipboard fa-2x text-orange-400"></i>
      <span class="ml-1 text-lg text-blue-200 font-semibold ml-4">StoryBlok</span>
    </div>
    <div class="block md:hidden">
      <i class="fas fa-bars fa-2x text-orange-400" @click="toggleMenu" v-show="showMobileMenu"></i>
    </div>

    <div
      id="nav-content"
      class="w-full flex-grow md:flex md:items-center md:w-auto hidden md:block pt-6 md:pt-0"
      v-show="this.$route.name == 'index'"
    >
      <ul
        class="list-reset md:flex justify-end flex-1 items-center font-semibold"
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
      <ul class="list-reset md:flex justify-end flex-1 items-center font-semibold">
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
  computed: {
    showMobileMenu: function () {
      return this.$route.name === "index";
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
