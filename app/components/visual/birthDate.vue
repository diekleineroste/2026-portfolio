<script setup lang="ts">
const loader = inject<Ref<boolean>>('loader')
</script>

<template>
  <div id="birthdate-visuals">
    <div class="svg-day-wrapper">
      <SvgNumber :number="'2'" :color="'primary'"/>
      <SvgNumber :number="'2'" :color="'primary'"/>
    </div>
    <div class="svg-month-wrapper">
      <SvgNumber :number="'1'" :color="'primary'"/>
      <SvgNumber :number="'0'" :color="'primary'"/>
    </div>
    <div class="svg-year-wrapper">
      <SvgNumber :number="'2'" :color="'primary'"/>
      <SvgNumber :number="'0'" :color="'primary'"/>
      <SvgNumber :number="'0'" :color="'primary'"/>
      <SvgNumber :number="'4'" :color="'primary'"/>
    </div>
  </div>
</template>

<style scoped lang="scss">
#birthdate-visuals {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  height: 100dvh;
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 115px));
  grid-template-rows: repeat(4, minmax(0, 1fr));
  justify-content: flex-end;
  gap: var(--spacing-xxs);
  padding: var(--spacing-xxs);
  overflow: hidden;
  z-index: -1;

  .svg-day-wrapper, .svg-month-wrapper, .svg-year-wrapper {
    display: flex;
    align-items: flex-end;
    justify-content: center;
    gap: var(--spacing-xxs);

    .number-container {
      display: flex;
      justify-content: flex-end;
      width: 100%;
      height: 100%;
    }
  }

  .svg-day-wrapper {
    grid-column: 3/5;
    grid-row: 2;
    justify-content: flex-start;
  }

  .svg-month-wrapper {
    grid-column: 2/4;
    grid-row: 3;
  }

  .svg-year-wrapper {
    grid-column: 1/5;
    grid-row: 4;
  }
}

@media screen and (min-width: 40em) {
  #birthdate-visuals {
    padding: var(--spacing-s);
    gap: var(--spacing-xs);
    grid-template-columns: repeat(4, 140px);
    grid-template-rows: repeat(3, minmax(0, 1fr));

    .svg-day-wrapper, .svg-month-wrapper, .svg-year-wrapper {
      display: flex;
      align-items: flex-end;
      justify-content: flex-end;
    }

    .svg-day-wrapper {
      grid-column: 3/5;
      grid-row: 1;
      justify-content: flex-start;
    }

    .svg-month-wrapper {
      grid-column: 2/4;
      grid-row: 2;
    }

    .svg-year-wrapper {
      grid-column: 1/5;
      grid-row: 3;
    }
  }
}

@media screen and (min-width: 80em) {
  #birthdate-visuals {
    padding: var(--spacing-m);
    gap: 0;
    grid-template-columns: repeat(10, minmax(0, 1fr));
    grid-template-rows: repeat(15, minmax(0, 1fr));

    .svg-day-wrapper, .svg-month-wrapper, .svg-year-wrapper {
      display: flex;
      justify-content: center;
      gap: var(--spacing-xxs);

      .number-container {
        width: 100%;
        height: fit-content;
      }
    }

    .svg-day-wrapper {
      grid-column: 1 / 3;
      grid-row: 1 / 8;
      align-items: flex-start;
    }

    .svg-month-wrapper {
      grid-column: 4 / 6;
      grid-row: 5 / 12;
      align-items: center;
    }

    .svg-year-wrapper {
      grid-column: 7 / 11;
      grid-row: 9 / 16;
      align-items: flex-end;
    }
  }
}
</style>