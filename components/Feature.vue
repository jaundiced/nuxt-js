<template>
  <div
    v-editable="blok"
    class="relative w-48 h-64 m-5 bg-white shadow-lg">
    <div class="flex items-center w-48 h-20 bg-blue-100">
       <img
        class="mx-auto"
        :src="blok.image"> 
    </div>
    <p
      class="mx-2 py-2 border-b-2 text-center text-gray-700 font-semibold uppercase"
    >
      {{blok.title}}
    </p>
    <p class="p-2 text-sm text-gray-700">
      {{blok.description}}
    </p>
    <div
      class="absolute right-0 bottom-0 w-8 h-8 bg-gray-300 hover:bg-orange-300 text-center cursor-pointer"
    >
      <i class="fas fa-chevron-right mt-2 text-orange-500"></i>
    </div>
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
