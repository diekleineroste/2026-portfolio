<script setup lang="ts">
interface Props {
  number: string
  clicked: boolean
  data: {
    year: string,
    rolls: string[],
    brandName: string,
    imagePath: string,
    link: string
  }
}

defineProps<Props>()
</script>

<template>
<div class="work-card" :class="{'clicked': clicked}">
  <div class="top">
    <p class="year display-64">{{ data.year }}</p>
    <div class="rolls">
      <p v-for="r in data.rolls" class="body-16-600 uppercase">{{ r }}</p>
    </div>
  </div>
  <div class="svg-number-wrapper">
    <SvgNumber class="svg-number" :number="number" :color="'accent'"/>
  </div>
  <div class="brand-name">
    <h3 class="display-32">{{ data.brandName }}</h3>
  </div>
  <div class="image-wrapper">
    <img v-if="data.imagePath" :src="data.imagePath" :alt="'A picture of my work with ' + data.brandName" />
  </div>
</div>
</template>

<style scoped lang="scss">
@mixin card-hover {
  &::after {
    top: 100%;
    height: 0;
  }

  .image-wrapper img {
    filter: grayscale(.1) brightness(.9);
  }

  .top,
  .brand-name {
    color: white;
  }

  .svg-number-wrapper {
    opacity: 0;
  }
}

// ─── Base styles ──────────────────────────────────────────────────────────────

.work-card {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: var(--spacing-s);
  color: var(--text);
  overflow: hidden;

  .image-wrapper {
    position: absolute;
    inset: 0;
    background: var(--primary-20);
    z-index: -2;

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      filter: grayscale(1) brightness(.7);
      transition: filter 1s ease-in-out;
    }
  }

  &::after {
    position: absolute;
    content: '';
    top: 60%;
    left: -15em;
    transform: translate(-50%, -50%);
    height: 200%;
    aspect-ratio: 1;
    border-radius: 100%;
    background: var(--radial-gradient-2);
    z-index: -1;
    transition: top 1s ease-in-out, height 1s ease-in-out;
  }

  .svg-number-wrapper,
  .top,
  .brand-name {
    opacity: 1;
    transition: opacity .5s ease-in-out, color 1s ease-in-out;
  }

  .top {
    height: fit-content;

    .rolls {
      margin-top: var(--spacing-xs);

      p { margin: 0; }
    }
  }

  .svg-number-wrapper {
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;

    .svg-number { width: 60%; }
  }

  .brand-name {
    height: fit-content;
    display: flex;
    align-items: flex-end;
    justify-content: flex-end;

    h3 {
      margin: 0;
      text-align: right;
    }
  }

  &.clicked {
    @include card-hover;
  }
}

// ─── Tablet ────────────────────────────────────────────────────────────

@media screen and (min-width: 40em) {
  .work-card {
    gap: var(--spacing-s);

    .svg-number-wrapper,
    .top,
    .brand-name {
      height: 100%;
    }

    &:hover {
      @include card-hover;
    }
  }
}

// ─── Desktop ──────────────────────────────────────────────────────────────────

@media screen and (min-width: 80em) {
  .work-card::after {
    height: 130%;
  }
}
</style>