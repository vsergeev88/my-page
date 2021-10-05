<script setup lang="ts">
type Props = {
  tags: string[]
  i: string
}
const props = defineProps<Props>()

const shuffle = (array: string[]) => {
  let currentIndex = array.length
  let randomIndex

  // While there remain elements to shuffle...
  while (currentIndex !== 0) {
    // Pick a remaining element...
    randomIndex = Math.floor(Math.random() * currentIndex)
    currentIndex--;

    // And swap it with the current element.
    [array[currentIndex], array[randomIndex]] = [
      array[randomIndex], array[currentIndex]]
  }

  return array
}
</script>

<template>
  <h2 :style="{ '--i': props.i } as Record<string, string>">
    <span v-for="(tag, index) in shuffle(props.tags)" :key="index">
      {{ tag }}
    </span>
  </h2>
</template>
