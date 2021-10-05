<script setup lang="ts">
import { isDark } from '~/logic'

// https://github.com/vueuse/head
// you can use this to manipulate the document head in any components,
// they will be rendered correctly in the html results with vite-ssg
useHead({
  title: 'Vitesse',
  meta: [
    { name: 'Val Sergeev', content: 'Personal page by Val' },
  ],
})

const x = ref('50px')
let wait = false
const moveHandler = (e: MouseEvent) => {
  if (!wait) {
    x.value = `${e.clientX}px`
    wait = true
    setTimeout(() => {
      wait = false
    }, 35)
  }
}
const leaveHandler = (e: MouseEvent) => {
  x.value = '200px'
}
</script>

<template lang="pug">
div(class="h-full w-full" @mousemove="moveHandler" @mouseleave="leaveHandler")
  //- BackgroundText(:pos="x")
  .flex(class="p-3 h-full w-full items-center justify-center")
    .my-card(
      :class="{'smooth-shadow': !isDark, 'smooth-glow': isDark}"
      class="w-full sm:w-1/2 lg:w-prose rounded-2xl pl-6 pb-6 pr-2 pt-2 text-center"
      style="--tw-bg-opacity: 0.9;"
    )
      router-view
</template>

<style>
.my-card {
  @apply text-gray-700 dark:text-gray-200 bg-gray-200 dark:bg-black;
  backdrop-filter: blur(10px);

}
.smooth-shadow {
  box-shadow: 0 2px 1px rgba(0,0,0,0.09),
              0 4px 2px rgba(0,0,0,0.09),
              0 8px 4px rgba(0,0,0,0.09),
              0 16px 8px rgba(0,0,0,0.09),
              0 32px 16px rgba(0,0,0,0.09);
}
.smooth-glow {
  box-shadow: 0 2px 1px rgba(124, 58, 237,0.09),
            0 4px 2px rgba(124, 58, 237,0.09),
            0 8px 4px rgba(124, 58, 237, 0.09),
            0 16px 8px rgba(124, 58, 237,0.09),
            0 32px 16px rgba(124, 58, 237,0.09);
}
</style>
