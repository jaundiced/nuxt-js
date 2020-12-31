<template>
<section class="container mx-auto shadow-xl bg-gray-100 text-blue-500 border-blue-200 text-md w-3/4 p-10 pt-20">
  <div class="pt-10 mb-4 ">
    <nuxt-link class="italic text-l" to="/articles">...back to articles...</nuxt-link>
    </div>
  <div
    v-editable="blok"
    class="section"
    >
    <div class="font-semibold text-2xl">{{ blok.name }}</div>
    <div class="font-semibold text-l italic">{{ blok.intro }}</div>
    <rich-text-renderer
      :document="blok.body"
    />
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
  }
}
</script>
