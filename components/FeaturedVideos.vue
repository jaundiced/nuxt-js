<template>
<div class="container mx-auto">
<a name="featured-videos" id="featured-videos">&nbsp;</a>
  <ul
    v-editable="blok">
    <li
      :key="blok._uid"
      v-for="blok in blok.video_item">
      <component :blok="blok" :is="blok.component" />
    </li>
  </ul>
</div>
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
