<script setup lang="ts">
const titlePercentage = ref<number>(0)
const loader = ref<boolean>(true)
const delayedLoader = ref<boolean>(true)

const injectedLoader = inject<Ref<boolean>>('loader')

const animateTitle = () => {
  if (titlePercentage.value >= 99) {
    setTimeout(() => {
      titlePercentage.value = 100
      console.log(injectedLoader!.value)
      loader.value = false
      injectedLoader!.value = loader.value
      setTimeout(() => {
        delayedLoader.value = false
      },1500)
    }, 200)
    return
  }

  titlePercentage.value++

  const delay = 5 + (titlePercentage.value * 0.6)
  setTimeout(animateTitle, delay)
}

watch(delayedLoader, (val) => {
  if (val) {
    disableScroll()
  } else {
    enableScroll()
  }
})

onMounted(() => {
  animateTitle()
  if (delayedLoader.value) {
    disableScroll()
  }
})

function disableScroll() {
  document.body.style.overflow = 'hidden'
  document.body.classList.add("remove-scrolling")
}

function enableScroll() {
  document.body.style.overflow = ''
  document.body.classList.remove("remove-scrolling")
}
</script>

<template>
  <div v-if="delayedLoader" id="loader">
    <div class="svg-container">
      <SvgFullName/>
    </div>
    <div class="title-container">
      <p class="display-96">portfolio</p>
      <span class="display-32">{{ titlePercentage }}</span>
    </div>
  </div>
</template>

<style scoped lang="scss">
#loader {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  width: 100dvw;
  height: 100vh;
  height: 100dvh;
  padding: var(--spacing-m);
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  background: var(--radial-gradient);
  z-index: -1;

  .title-container {
    display: flex;
    gap: var(--spacing-xxs);
    animation: fade-up .5s ease-in-out forwards;

    span {
      padding-top: 1.5rem;
    }
  }

  .svg-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    padding: var(--spacing-m);
    z-index: -1;

    svg {
      width: 100%;
      height: 100%;
    }
  }
}

@keyframes fade-up {
  from {
    opacity: 0;
    transform: translateY(5vh);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>