<template>
<section class="container mx-auto">
  <div
    v-editable="blok"
    class="m-5 flex justify-center">
    
    <p class="p-2 text-sm text-gray-700">
      <iframe width="640" height="385" :src="blok.iframe_html" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </p>

    
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
