<script setup lang="ts">
const loader = inject<Ref<boolean>>('loader')
</script>

<template>
  <section id="hero">
    <VisualSignatureRectangle class="signature-rectangle"/>
    <div class="display-title">
      <h2 class="display-96">designer</h2>
      <h2 class="display-96">developer</h2>
    </div>
    <div class="display-text">
      <p>
        I question conventions before I apply them. Grids are useful, until they aren’t. Patterns help, until they restrict. When rules block the concept, they go. The idea always comes first. Everything else is negotiable. That’s how boundaries shift. Small experiments lead the way. Subtle animation. Strange layout shift. Contrast that feels slightly off. Those moments matter. They reveal direction. They shape the final form.
      </p>
    </div>
    <p class="display-defaults">
      Question the defaults
    </p>
    <p class="display-name body-20">
      Laurens Rousseau
    </p>
    <p class="display-quote">
      the website should not only showcase<br>the designers work but also reflect<br>their unique style and personality
    </p>
    <VisualVisionCrosshair class="display-image"/>
  </section>
</template>

<style scoped lang="scss">
#hero {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr)) 115px;
  grid-template-rows: repeat(12, minmax(0, 1fr));
  gap: var(--spacing-xs);
  width: 100vw;
  width: 100dvw;
  height: 100vh;
  height: 100dvh;

  .signature-rectangle {
    grid-column: 1 / 4;
    grid-row: 2 / 6;
    margin: var(--spacing-xxs);
  }

  .display-title {
    grid-column: 1 / 5;
    grid-row: 11 / 13;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: flex-start;
  }

  .display-text {
    grid-column: 4;
    grid-row: 7 / 10;
    text-align: justify;
    margin: 0;
    font-size: 1vh;

    p {
      margin: 0 0 0 calc(112px - 10vh);
    }
  }

  .display-defaults {
    grid-column: 1;
    grid-row: 6 / 9;
    text-align: right;
    text-transform: uppercase;
    writing-mode: sideways-lr;
    margin: 0;
  }

  .display-name {
    grid-column: 1 / 5;
    grid-row: 1;
    text-align: center;
    text-transform: uppercase;
    margin: 0;
  }

  .display-quote {
    display: none;
    grid-column: 1/5;
    grid-row: 1/3;
    text-align: right;
    align-items: flex-end;
    justify-content: flex-end;
    margin: 0;
  }

  .display-image {
    display: none;
    grid-column: 1;
    grid-row: 1;
  }
}

@media screen and (min-width: 40em) {
  #hero {
    display: grid;
    grid-template-columns: repeat(7, minmax(0, 1fr)) 140px;
    grid-template-rows: repeat(12, minmax(0, 1fr));
    gap: var(--spacing-xs);
    width: 100vw;
    width: 100dvw;
    height: 100vh;
    height: 100dvh;

    .signature-rectangle {
      grid-column: 2 / 5;
      grid-row: 2 / 7;
    }

    .display-title {
      grid-column: 1 / 9;
      grid-row: 11 / 13;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      align-items: flex-start;
    }

    .display-text {
      grid-column: 1 / 4;
      grid-row: 7;
      text-align: justify;
      margin: 0;
      font-size: .9em;

      p {
        margin: 0;
      }
    }

    .display-defaults {
      grid-column: 8;
      grid-row: 5 / 9;
      text-align: center;
      margin: 0;
    }

    .display-name {
      grid-column: 1 / 9;
      grid-row: 1;
      text-align: center;
      text-transform: uppercase;
      margin: 0;
    }

    .display-quote {
      display: none;
      grid-column: 1/5;
      grid-row: 1/3;
      text-align: right;
      align-items: flex-end;
      justify-content: flex-end;
      margin: 0;
    }

    .display-image {
      display: none;
      grid-column: 1;
      grid-row: 1;
    }
  }
}

@media screen and (min-width: 80em) {
  #hero {
    display: grid;
    grid-template-columns: repeat(16, minmax(0, 1fr));
    grid-template-rows: repeat(9, minmax(0, 1fr));
    gap: var(--spacing-s);
    width: 100vw;
    width: 100dvw;
    height: 100vh;
    height: 100dvh;

    .signature-rectangle {
      grid-column: 3 / 8;
      grid-row: 2 / 7;
    }

    .display-title {
      grid-column: 1 / 5;
      grid-row: 8 / 10;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      align-items: flex-start;
    }

    .display-text {
      grid-column: 8 / 13;
      grid-row: 8 / 10;
      text-align: justify;
      margin: 0;
    }

    .display-defaults {
      grid-column: 9;
      grid-row: 4 / 7;
      text-align: center;
      text-transform: uppercase;
      writing-mode: sideways-lr;
      margin: 0;
    }

    .display-name {
      grid-column: 7 / 11;
      grid-row: 1;
      text-align: center;
      text-transform: uppercase;
      margin: 0;
    }

    .display-quote {
      display: block;
      grid-column: 12 / 17;
      grid-row: 1;
      text-align: right;
      margin: 0;
    }

    .display-image {
      display: block;
      grid-column: 11 / 15;
      grid-row: 2 / 5;
    }
  }
}
</style>