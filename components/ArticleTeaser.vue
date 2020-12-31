<template>
  <div class="px-2 mb-4">
    <div class="bg-white rounded py-2">
      <nuxt-link :to="articleLink" class="article-teaser  border rounded border-gray-500">
      <p class="text-gray-800 text-base px-6 mb-5">
         {{ articleContent.name }}
        </p>
      <p class="text-gray-500 text-xs md:text-sm px-6">{{ articleContent.intro }}</p>
       </nuxt-link>
    </div>
  </div>
  <!-- <nuxt-link>
    :to="articleLink"
    class="article-teaser block py-4 px-6 border rounded border-gray-500">
    <h2 class="pt-2 pb-4 text-2xl font-bold">
      {{ articleContent.name }}
    </h2>
    <p class="pb-6 leading-relaxed">
      {{ articleContent.intro }}
    </p>
  </nuxt-link> -->
</template>

<script>
export default {
  props: {
    articleContent: {
      type: Object,
      required: true
    },
    articleLink: {
      type: String,
      required: true
    }
  }
}
</script>

<style>
.article-teaser:hover {
  box-shadow: 0px 0px 15px 0px rgba(0,0,0,0.75);
}
</style>
