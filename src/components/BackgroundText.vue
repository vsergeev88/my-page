<script setup lang="ts">
const props = defineProps({
  pos: { type: String },
})
const tags = [
  'Vue',
  'Node.js',
  'Nuxt',
  'MongoDB',
  'Nest',
  'SASS',
  'Docker',
  'React',
  'Webpack',
  'PostCSS',
  'Kubernetes',
  'RxJS',
  'Lerna',
  'Storybook',
  'Vite',
  'Figma',
]

// const shuffle = (array: string[]) => {
//   let currentIndex = array.length
//   let randomIndex

//   // While there remain elements to shuffle...
//   while (currentIndex !== 0) {
//     // Pick a remaining element...
//     randomIndex = Math.floor(Math.random() * currentIndex)
//     currentIndex--;

//     // And swap it with the current element.
//     [array[currentIndex], array[randomIndex]] = [
//       array[randomIndex], array[currentIndex]]
//   }

//   return array
// }
</script>

<template>
  <section
    v-if="props.pos"
    ref="el"
    class="bg-gray-500 dark:bg-dark-600"
    :style="{'--x': props.pos} as any"
  >
    <div class="text">
      <BGTextItem :tags="tags" i="0.5" />
      <BGTextItem :tags="tags" i="1.5" />
      <BGTextItem :tags="tags" i="2.5" />
      <BGTextItem :tags="tags" i="2.25" />
      <BGTextItem :tags="tags" i="1.25" />
      <BGTextItem :tags="tags" i="0.75" />
      <BGTextItem :tags="tags" i="1.25" />
      <BGTextItem :tags="tags" i="0.75" />
      <BGTextItem :tags="tags" i="3" />
      <BGTextItem :tags="tags" i="2.35" />
    </div>
  </section>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

section {
  transform: translateZ(0);
  will-change: transform;
  position: absolute;
  z-index: -1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100vh;
  overflow: hidden;
}

.text {
  position: relative;
  transform: skewY(345deg) translateY(-200px);
  animation: animateColor 5s linear infinite;
}

@keyframes animateColor {
  0% {
    filter: hue-rotate(0deg);
  }
  100% {
    filter: hue-rotate(360deg);
  }
}

.text h2 {
  position: relative;
  width: 100%;
  font-size: 13vh;
  color: #fff;
  font-weight: bold;
  pointer-events: none;
  line-height: 1em;
  white-space: nowrap;
  text-shadow: calc(var(--x)) 100px 0 rgba(255, 255, 255, 0.1);
  transform: translateX(calc(0% - var(--x) * var(--i)))
}

.text h2 span {
  color: #0f0;
  margin: 0 10px;
}

.text h2 span:nth-child(even) {
  color: transparent;
  -webkit-text-stroke: 2px #fff;
}
</style>
