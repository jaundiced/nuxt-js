<template>
<div class="container mx-auto">
<a name="feature-grid" id="feature-grid">&nbsp;</a>
  <ul
    v-editable="blok"
    class="flex justify-center flex-wrap">
    <li
      :key="blok._uid"
      v-for="blok in blok.columns"
      class="flex-auto px-6">
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
