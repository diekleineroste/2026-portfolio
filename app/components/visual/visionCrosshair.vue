<script setup lang="ts">

</script>

<template>
  <div id="vision-crosshair">
    <div class="crosshair">
      <div class="crosshair-line"/>
      <p class="display-32 uppercase crosshair-label">Vision</p>
      <div class="crosshair-line"/>
    </div>
    <img src="~/assets/images/DSC00860.jpg" alt="picture of me (laurens rousseau) typing on a computer as a kid">
  </div>
</template>

<style scoped lang="scss">
#vision-crosshair {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: crosshair;

  .crosshair {
    display: flex;
    align-items: center;
    gap: var(--spacing-s);
    width: calc(100% - 40px);
    height: calc(100% - 40px);
    margin: var(--spacing-s);
    overflow: hidden;

    .crosshair-line {
      flex: 1;
      height: 5px;
      background: var(--secondary);
    }

    .crosshair-label {
      position: relative;
      flex-shrink: 0;
      white-space: nowrap;
      color: var(--secondary);
    }

    .crosshair-label::before,
    .crosshair-label::after {
      content: '';
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      width: 5px;
      background: var(--secondary);
      height: 10vh;
    }

    .crosshair-label::before {
      bottom: 100%;
      margin-bottom: 1rem;
    }

    .crosshair-label::after {
      top: 100%;
      margin-top: 1rem;
    }
  }

  img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    filter: grayscale(1);
    opacity: .6;
    z-index: -1;
  }
}
</style>