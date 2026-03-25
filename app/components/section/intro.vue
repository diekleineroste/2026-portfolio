<script setup lang="ts">

</script>

<template>
  <section id="intro">
    <div class="intro-container">
      <div class="image-wrapper">
        <img src="~/assets/images/most_profesional.png" alt="Me"/>
        <SvgSun class="svg-sun" :stroke-width="1.5"/>
      </div>
      <div class="intro-wrapper">
        <div class="name">
          <p class="display-96">Laurens</p>
          <p class="display-96">Rousseau</p>
          <p class="jobtitle body-20">Designer Developer Hybrid</p>
          <SvgScribble class="scribble"/>
        </div>
        <p class="intro-text">
          I work across design and development, shaping ideas into digital experiences. My focus is on combining visual direction with thoughtful implementation, ensuring each project is both aesthetically strong and technically sound. I approach each project as both a concept and a system, refining how it looks, performs, and responds to users.
        </p>
        <div class="contact">
          <p>22-10-2004</p>
          <p>laurensrousseau@gmail.com</p>
          <p>@roux_dsgn</p>
        </div>
      </div>
    </div>
    <div class="experience-container">
      <div class="container">
        <h3>experience</h3>
        <div class="wrapper">
          <h4>Designer Developer Hybrid - Independent</h4>
          <p>Haerens Visuals</p>
          <p>March 2025 - August 2025</p>
        </div>
        <div class="wrapper">
          <h4>Designer Developer Hybrid - Internship</h4>
          <p>Webatvantage</p>
          <p>February 2025 - May 2025</p>
        </div>
        <div class="wrapper">
          <h4>Frontend Developer - Internship</h4>
          <p>District09</p>
          <p>February 2022</p>
        </div>
        <div class="wrapper">
          <h4>Full-stack Developer - Volunteer</h4>
          <p>Judoclub Banzai</p>
          <p>July 2021 – Present</p>
        </div>
      </div>
      <div class="container">
        <h3>education</h3>
        <div class="wrapper">
          <h4>Odisee, Ghent</h4>
          <p>Professional Bachelor</p>
          <p>2022 - 2026</p>
        </div>
        <div class="wrapper">
          <h4>Sint-Lievenscollege, Ghent</h4>
          <p>IT & Netwerken</p>
          <p>2020 - 2022</p>
        </div>
        <div class="wrapper">
          <h4>Don Bosco College, Zwijnaarde</h4>
          <p>Wetenschappen</p>
          <p>2016 - 2020</p>
        </div>
      </div>
      <div class="container">
        <h3>languages</h3>
        <div class="wrapper">
          <p>Dutch - C2</p>
          <p>English - C1</p>
          <p>French - B1</p>
        </div>
      </div>
    </div>
    <div class="skills-container">
      <div class="container">
        <h3>technical skills</h3>
        <div class="wrapper">
          <h4>Frontend</h4>
          <p>HTML5</p>
          <p>CSS3 / SCSS</p>
          <p>Javascript / Typescript</p>
        </div>
        <div class="wrapper">
          <h4>Backend</h4>
          <p>Node.js</p>
          <p>Express</p>
          <p>PHP</p>
        </div>
        <div class="wrapper">
          <h4>Frameworks & Libraries</h4>
          <p>Vite</p>
          <p>Vue</p>
          <p>Nuxt</p>
          <p>React</p>
          <p>React Native</p>
          <p>Lit.dev</p>
          <p>Laravel</p>
        </div>
        <div class="wrapper">
          <h4>Animation & Interaction</h4>
          <p>GSAP</p>
          <p>Three.js</p>
          <p>P5.js</p>
        </div>
        <div class="wrapper">
          <h4>Tools</h4>
          <p>Git</p>
          <p>GitHub</p>
          <p>Figma</p>
          <p>Adobe Illustrator</p>
          <p>Affinity</p>
        </div>
      </div>
      <div class="container">
        <h3>other skills</h3>
        <div class="wrapper">
          <p>Twig</p>
          <p>Java</p>
          <p>Unity</p>
          <p>C# / .NET</p>
          <p>C++</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
// ─── Base styles ───────────────────────────────────────────────

#intro {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-s);

  p, h4, h3 { margin: 0; }

  h4, h3 {
    font-size: 1rem;
    font-weight: 550;
  }

  h3 { color: var(--accent); }

  .intro-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: var(--spacing-s);
    margin-top: var(--spacing-m);

    .image-wrapper {
      position: relative;
      width: calc(100% - (var(--spacing-l) * 2));
      margin: 0 var(--spacing-l);
      min-width: 20rem;
      aspect-ratio: .75;

      img {
        position: relative;
        width: 100%;
        height: 100%;
        object-fit: cover;
        opacity: .8;
        filter: grayscale(1) brightness(.8);
        border-top-left-radius: 40rem;
        border-top-right-radius: 40rem;
      }

      .svg-sun { display: none; }
    }

    .intro-wrapper {
      display: flex;
      flex-direction: column-reverse;
      gap: var(--spacing-s);

      .name {
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        width: fit-content;
        margin: 0 auto;

        .scribble {
          position: absolute;
          left: 50%;
          top: 50%;
          transform: translate(-50%, -50%);
          pointer-events: none;
          width: 120%;
        }

        .jobtitle { align-self: center; }
      }

      .contact {
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        width: 100%;
      }

      .intro-text {
        display: none;
        position: absolute;
        bottom: 0;
        right: 20%;
        width: 40%;
        transform: translateY(40%);
        text-align: justify;
        z-index: 1;
      }
    }
  }

  .experience-container,
  .skills-container {
    width: 100%;
    padding: 0 var(--spacing-m);

    .container {
      margin: var(--spacing-m) 0;

      .wrapper { margin: var(--spacing-s) 0; }
    }
  }

  .skills-container {
    text-align: right;

    .container .wrapper {
      display: flex;
      flex-wrap: wrap;
      justify-content: flex-end;
      column-gap: var(--spacing-xs);
      row-gap: var(--spacing-xxs);
    }
  }
}

// ─── Tablet ───────────────────────────────────────────────────────────────────

@media screen and (min-width: 40em) {
  #intro {
    align-items: center;
    margin: var(--spacing-m) 0;

    .intro-container {
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: center;
      gap: var(--spacing-m);

      .image-wrapper {
        width: 100%;
        min-width: 0;
        max-width: 25rem;
        margin: 0;

        img {
          border-top-left-radius: 0;
          border-top-right-radius: 0;
        }
      }

      .intro-wrapper {
        position: relative;
        flex-direction: column;
        gap: var(--spacing-m);
        justify-content: flex-end;
        width: 100%;
        max-width: 30rem;

        .name {
          margin: 0 auto 0 0;
          height: fit-content;

          .scribble { width: 110%; }
        }

        .contact {
          align-items: flex-start;
          width: fit-content;
          text-align: justify;
        }

        .intro-text {
          display: block;
          position: static;
          text-align: left;
          width: 100%;
          transform: none;
        }
      }
    }

    .experience-container,
    .skills-container {
      display: flex;
      gap: var(--spacing-l);
      padding: 0;

      .container {
        margin: 0;

        .wrapper { margin: var(--spacing-s) 0; }
      }
    }

    .experience-container { margin-top: var(--spacing-l); }

    .skills-container {
      flex-direction: row-reverse;
      align-items: flex-end;
    }
  }
}

// ─── Desktop ──────────────────────────────────────────────────────────────────

@media screen and (min-width: 80em) {
  #intro {
    display: grid;
    row-gap: 0;
    grid-template-columns: repeat(3, 1fr);

    .intro-container {
      grid-column: 1 / 4;
      grid-row: 1;
      align-items: center;
      justify-content: space-evenly;
      margin: var(--spacing-xl) 0;

      .image-wrapper {
        max-width: 30rem;
        height: fit-content;

        .svg-sun {
          display: block;
          position: absolute;
          top: 45%;
          left: 50%;
          transform: translate(-50%, -50%);
          width: fit-content;
          height: 150%;
          border-radius: 100%;
        }
      }

      .intro-wrapper {
        margin-bottom: var(--spacing-xxs);

        .name {
          .scribble { display: none; }
        }
      }
    }

    .experience-container {
      grid-column: 1 / 4;
      grid-row: 2;
      margin: 0;
    }

    .skills-container {
      grid-column: 1 / 4;
      grid-row: 3;
    }
  }
}
</style>