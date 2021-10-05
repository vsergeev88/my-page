<script setup lang="ts">
import { isClient } from '@vueuse/shared'
import { isDark, toggleDark } from '~/logic'

const { t, availableLocales, locale } = useI18n()

const toggleLocales = () => {
  // change to some real logic
  const locales = availableLocales
  locale.value = locales[(locales.indexOf(locale.value) + 1) % locales.length]
}

const options = ref({
  title: 'Val S',
  text: 'Personal page',
  url: isClient ? location.href : '',
})
const { share, isSupported } = useShare(options)
const startShare = () => share().catch(err => err)
</script>

<template lang="pug">
.flex.text-md.justify-end.text-xl.pr-1
  a(class="icon-btn" :title="t('button.toggle_langs')" @click="toggleLocales")
    carbon-language
  button(class="icon-btn ml-2 !outline-none" :title="t('button.toggle_dark')" @click="toggleDark()")
    carbon-moon(v-if="isDark")
    carbon-sun(v-else)
  .ml-2(v-if="isSupported")
    button(class="icon-btn !outline-none" title="Share" @click="startShare")
      mdi:share-variant-outline
</template>
