<script setup lang="ts">
import { isDark, toggleDark } from '~/logic'

const { t, availableLocales, locale } = useI18n()

const toggleLocales = () => {
  // change to some real logic
  const locales = availableLocales
  locale.value = locales[(locales.indexOf(locale.value) + 1) % locales.length]
}
</script>

<template lang="pug">
nav(class="text-xl mt-6")
  button(class="icon-btn mx-2 !outline-none" :title="t('button.toggle_dark')" @click="toggleDark()")
    carbon-moon(v-if="isDark")
    carbon-sun(v-else)

  a(class="icon-btn mx-2" :title="t('button.toggle_langs')" @click="toggleLocales")
    carbon-language

</template>
