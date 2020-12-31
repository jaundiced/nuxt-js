<template>
  <section class="container mx-auto">
    <!-- <h2 class="py-10 text-center font-bold text-2xl pt-30">Articles</h2> -->
    <p class="text-xl font-bold text-center text-white mb-8 pt-20">
      Articles
    </p>
    
    <ul class="flex justify-center flex-wrap">
      <li
        v-for="article in stories" :key="article._uid"
          class="flex-auto min-width:80% w-full">
        <article-teaser
          v-if="article.content"
          :article-link="article.full_slug"
          :article-content="article.content"/>
        <p v-else class="px-4 py-2 text-white bg-red-700 text-center rounded">This content loads on save. <strong>Save the entry &amp; reload.</strong></p>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data () {
    return {
      stories: []
    }
  },
  asyncData (context) {
    return context.app.$storyapi.get('cdn/stories', {
      starts_with: 'articles/',
      sort_by: "sort_by_date:desc",
      version: 'draft'
    }).then((res) => {
      return res.data
    }).catch((res) => {
      if (!res.response) {
        console.error(res)
        context.error({ statusCode: 404, message: 'Failed to receive content form api' })
      } else {
        console.error(res.response.data)
        context.error({ statusCode: res.response.status, message: res.response.data })
      }
    })
  }
}
</script>
