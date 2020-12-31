<template>
  <section>  
  <div v-editable="blok" class="container mx-auto px-6 py-20">
    <a name="featured-articles" id="featured-articles">
      <p class="text-xl font-bold text-center text-blue-100 mb-8">
        {{blok.title}}
      </p>
    </a>
    <div class="flex flex-wrap">
      <ul class="flex justify-center flex-wrap">
        <li
          :key="key=article._uid"
          v-for="article in sortedArticles"
          class="flex-auto px-6">
          <article-teaser
              v-if="article.content"
              :article-link="article.full_slug"
              :article-content="article.content"/>
            <p v-else class="px-4 py-2 text-white bg-red-700 text-center rounded">This content loads on save. <strong>Save the entry &amp; reload.</strong></p>
        </li>
      </ul>
      <div class="max-w-5xl mx-auto text-center">
      <nuxt-link
        class="text-gray-500 font-bold hover:text-gray-800 hover:underline"
        to="/articles">
        All Articles
      </nuxt-link>
    </div>
    </div>
  </div>
</section>
</template>

<script>
export default {
  props: {
    blok: {
      type: Object,
      required: true
    }
  },
  computed: {
    sortedArticles() {
      // Load reference data/content from store
      const featuredArticles = this.$store.state.articles.articles.filter((article) => {
        return this.blok.articles.includes(article.uuid)
      })

      // Enable the ordering of the article previews
      featuredArticles.sort((a, b) => {
        return this.blok.articles.indexOf(a.uuid) - this.blok.articles.indexOf(b.uuid);
      })

      return featuredArticles
    }
  }
}
</script>
