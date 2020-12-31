<template>
  <section>
    <div class="container mx-auto">
    <a name="featured-videos" id="featured-videos">
      <p class="text-xl font-bold text-center text-blue-100">Featured Videos</p></a>
      <ul
        v-editable="blok">
        <li
          :key="blok._uid"
          v-for="blok in blok.video_item">
          <component :blok="blok" :is="blok.component" />
        </li>
      </ul>
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
