<script setup lang="ts">
const works = ref()
const fetchData = async () => {
  fetch('/data/works.json')
  .then((res) => res.json())
  .then((data) => {
    works.value = data
  })
}

onMounted(() => {
  fetchData()
})

const clickedNumber = ref<number>(0)

const handleClick = (idx: number) => {
  if (clickedNumber.value === idx + 1) {
    clickedNumber.value = 0
  }
  else {
    clickedNumber.value = idx + 1
  }
}
</script>

<template>
  <section id="works">
    <ProjectCard class="card" v-for="(w, idx) in works" @click="handleClick(idx)" :number="'0' + (idx + 1).toString()" :clicked="clickedNumber === idx + 1" :key="idx" :data="w"/>
  </section>
</template>

<style scoped lang="scss">
#works {
  display: grid;
  gap: var(--spacing-s);
  grid-template-columns: 1fr;
  padding: var(--spacing-s);

  .card {
    width: 100%;
    aspect-ratio: .75;
  }
}

@media screen and (min-width: 40em) {
  #works {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (min-width: 80em) {
  #works {
    grid-template-columns: repeat(4, 1fr);
    width: 100vw;
    width: 100dvw;
    height: 100vh;
    height: 100dvh;

    .card {
      aspect-ratio: 0;
    }
  }
}
</style>