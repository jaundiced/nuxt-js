<template>
<section class="container mx-auto">
  <a name="teaser" id="teaser">
  <div
    v-editable="blok"
    class="pb-4 mb-4 mx-auto">
    <div class="p-2 pt-32 text-md text-orange-400 font-bold text-center">{{ blok.headline }}</div>
  </div>
  </a>
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
