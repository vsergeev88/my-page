<script setup lang="ts">
// https://github.com/vueuse/head
// you can use this to manipulate the document head in any components,
// they will be rendered correctly in the html results with vite-ssg
useHead({
  title: 'Val Sergeev | personal page',
  meta: [
    { name: 'Val Sergeev', content: 'Personal page by Val' },
  ],
})
</script>

<template lang="pug">
router-view
</template>
