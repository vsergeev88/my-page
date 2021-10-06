<script setup lang="ts">
type Props = {
  tags: string[]
  i: string
}
const props = defineProps<Props>()
</script>

<template>
  <h2 :style="{ '--i': props.i } as Record<string, string>">
    <span v-for="(tag, index) in props.tags" :key="index">
      {{ tag }}
    </span>
  </h2>
</template>
