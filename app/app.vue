<script setup lang="ts">
useSeoMeta({
  title: 'My portfolio by Laurens Rousseau',
  description: 'This is my portfolio where I question conventions before I apply them and where the idea always comes first.',
  ogTitle: 'My portfolio by Laurens Rousseau',
  ogDescription: 'This is my portfolio where I question conventions before I apply them and where the idea always comes first.',
  ogImage: 'https://laurensrousseau.com/data/images/cover.png',
  twitterCard: 'summary_large_image',
  themeColor: { content: '#FFB634', media: '(prefers-color-scheme?: dark)'}
})

const loader = ref(true)

provide('loader', loader)
</script>
<template>
  <VisualLoader/>
  <main :class="{ 'loader': loader }">
    <VisualBirthDate/>
    <SectionHero/>
    <SectionIntro/>
    <SectionWorks/>
  </main>
</template>

<style scoped lang="scss">
main {
  position: relative;
  transform: translateX(0);
  transition: transform 1.5s cubic-bezier(.16,.26,.59,1);
  background: var(--double-radial-gradient);

  &.loader {
    transform: translateX(100%);
  }
}

:global(html) {
  overflow-x: hidden;
}
</style>
