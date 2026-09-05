<template>
  <main>
    <section class="hero">
      <div class="hero__overlay"></div>

      <div class="hero__content">
        <span class="hero__eyebrow"> PANGASINAN PROVINCE </span>

        <h1>
          Discover the
          <span>Heart of Pangasinan</span>
        </h1>

        <p>
          Explore remarkable places, timeless stories, and natural wonders that
          define our province.
        </p>

        <div class="hero__actions">
          <a href="#heritage" class="hero__button">
            Explore Heritage
            <span aria-hidden="true"> ↓ </span>
          </a>
        </div>
      </div>
    </section>

    <section id="heritage" class="heritage-section">
      <div class="container">
        <div class="section-header">
          <div>
            <span class="section-header__eyebrow"> EXPLORE </span>

            <h2>Places Worth Remembering</h2>
          </div>

          <p>
            From islands and lighthouses to natural hot springs, discover the
            destinations that tell the story of Pangasinan.
          </p>
        </div>

        <HeritageGrid :sites="heritageSites" />
      </div>
    </section>

    <section class="experience">
      <div class="container experience__container">
        <div class="experience__content">
          <span> EXPERIENCE PANGASINAN </span>

          <h2>More than a destination. It's a story.</h2>

          <p>
            Every landmark carries a piece of Pangasinan's history, culture, and
            identity. Discover them one destination at a time.
          </p>

          <a href="#heritage" class="experience__link"> Start exploring → </a>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import HeritageGrid from "../components/organisms/HeritageGrid.vue";

export default {
  name: "HomeView",

  components: {
    HeritageGrid,
  },

  data() {
    return {
      heritageSites: [
        {
          id: 1,

          title: "Hundred Islands",

          description:
            "Explore the breathtaking Hundred Islands National Park in Alaminos City.",

          image: "/images/hundred-islands.jpg",
        },

        {
          id: 2,

          title: "Bolinao Lighthouse",

          description:
            "Visit the historic lighthouse and enjoy panoramic views of the coastline.",

          image: "/images/bolinao-lighthouse.jpg",
        },

        {
          id: 3,

          title: "Balungao Hot Spring",

          description:
            "Experience the relaxing natural hot springs surrounded by beautiful landscapes.",

          image: "/images/balungao-hot-spring.jpg",
        },
      ],
    };
  },
};
</script>

<style scoped>
.hero {
  position: relative;

  min-height: 600px;

  display: flex;

  align-items: center;

  justify-content: center;

  overflow: hidden;

  background: linear-gradient(120deg, #12382b, #176b4d);
}

.hero::before {
  content: "";

  position: absolute;

  inset: 0;

  background: radial-gradient(
    circle at 80% 30%,
    rgba(217, 154, 50, 0.22),
    transparent 35%
  );
}

.hero__overlay {
  position: absolute;

  inset: 0;

  background: linear-gradient(
    90deg,
    rgba(8, 34, 25, 0.9),
    rgba(8, 34, 25, 0.4)
  );
}

.hero__content {
  position: relative;

  z-index: 1;

  width: 100%;

  max-width: 1200px;

  padding: 100px 20px;
}

.hero__eyebrow {
  display: inline-block;

  margin-bottom: 14px;

  color: #f1c56b;

  font-size: 0.78rem;

  font-weight: 800;

  letter-spacing: 0.15em;
}

.hero h1 {
  max-width: 750px;

  margin: 0;

  color: white;

  font-size: clamp(2.8rem, 8vw, 5.5rem);

  line-height: 0.98;

  letter-spacing: -0.04em;
}

.hero h1 span {
  display: block;

  color: #f1c56b;
}

.hero p {
  max-width: 600px;

  margin: 24px 0 32px;

  color: rgba(255, 255, 255, 0.8);

  font-size: 1.05rem;

  line-height: 1.8;
}

.hero__button {
  display: inline-flex;

  align-items: center;

  gap: 10px;

  padding: 13px 20px;

  border-radius: 10px;

  background: white;

  color: var(--color-primary);

  text-decoration: none;

  font-weight: 800;

  transition: transform 0.2s ease;
}

.hero__button:hover {
  transform: translateY(-3px);
}

.heritage-section {
  padding: 90px 20px;
}

.container {
  width: 100%;

  max-width: 1200px;

  margin: 0 auto;
}

.section-header {
  display: grid;

  grid-template-columns: 1fr 1fr;

  gap: 50px;

  align-items: end;

  margin-bottom: 42px;
}

.section-header__eyebrow {
  color: var(--color-primary);

  font-size: 0.75rem;

  font-weight: 800;

  letter-spacing: 0.14em;
}

.section-header h2 {
  max-width: 550px;

  margin: 8px 0 0;

  font-size: clamp(2rem, 5vw, 3.2rem);

  line-height: 1.1;

  letter-spacing: -0.03em;
}

.section-header p {
  margin: 0;

  color: var(--color-text-muted);

  line-height: 1.8;
}

.experience {
  padding: 80px 20px;

  background: var(--color-primary);
}

.experience__container {
  display: flex;

  justify-content: center;
}

.experience__content {
  max-width: 720px;

  text-align: center;

  color: white;
}

.experience__content > span {
  color: #f1c56b;

  font-size: 0.75rem;

  font-weight: 800;

  letter-spacing: 0.15em;
}

.experience h2 {
  margin: 12px 0 18px;

  font-size: clamp(2rem, 5vw, 3.5rem);

  line-height: 1.1;
}

.experience p {
  margin: 0 auto 24px;

  max-width: 600px;

  color: rgba(255, 255, 255, 0.75);

  line-height: 1.8;
}

.experience__link {
  color: white;

  font-weight: 800;

  text-decoration: none;

  border-bottom: 1px solid rgba(255, 255, 255, 0.5);

  padding-bottom: 4px;
}

@media (max-width: 700px) {
  .hero {
    min-height: 520px;
  }

  .hero__content {
    padding: 80px 20px;
  }

  .section-header {
    grid-template-columns: 1fr;

    gap: 16px;
  }

  .heritage-section {
    padding: 64px 16px;
  }
}
</style>
