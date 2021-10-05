<script setup lang="ts">
type Props = { url: string }
const props = defineProps<Props>()
const router = useRouter()
const go = () => {
  router.push(`/${encodeURIComponent(props.url)}`)
}
</script>

<template>
  <button class="text-3xl text-purple-600 font-semibold" @click="go">
    <slot></slot>
  </button>
</template>
