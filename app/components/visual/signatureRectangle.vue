<script setup lang="ts">
const hovered = ref(false)
</script>

<template>
  <div id="signature-rectangle" @mouseenter="hovered = true">
    <div v-if="!hovered" class="helper">
      <p>{{ "< click me >" }}</p>
    </div>
    <SvgPortfolio :hovered :stroke-width="7"/>
  </div>
</template>

<style scoped lang="scss">
#signature-rectangle {
  position: relative;
  background: rgba(255, 255, 255, 0.12);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: scale .3s cubic-bezier(.25, 2, .35, .5);

  svg {
    pointer-events: none;
    width: 100%;
    height: 100%;
    scale: 1.2;
    transition: scale .3s cubic-bezier(.25, 2, .35, .5);
  }

  .helper {
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    width: 100%;
    height: 100%;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    font-size: .7rem;
    color: rgba(255, 255, 255, 0.4);

    @media screen and (min-width: 40em) {
      display: none;
    }
  }

  &:hover {
    scale: .95;
    transition: scale .3s ease-in-out;
    svg {
      scale: 1.25;
      transition: scale .3s ease-in-out;
    }
  }
}
</style>