<script setup lang="ts">
const { t } = useI18n()
</script>

<template lang="pug">
div(class="md:flex items-center justify-center md:justify-items-start")
  .mb-3(class="w-full md:w-1/3 flex justify-center")
    img.userpic(class="w-1/3 md:w-full border-2 border-gray-200 rounded-full" src="/userpic.jpg")
  div(class="md:pl-6 md:text-left")
    h1(class="text-2xl md:text-3xl font-semibold") {{ t('greeting') }}
    em.mt-2 {{ t('info') }}
    Socials

    .mt-10.w-full(class="justify-center md:justify-items-end")
      //- NavBtn(url='projects')
      //-   .flex(class="flex items-center")
      //-     div Projects
      //-     mdi:arrow-right(class="ml-3 text-2xl")
</template>
