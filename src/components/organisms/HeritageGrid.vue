<template>
  <section
    class="heritage-grid"
    aria-label="Featured heritage sites"
  >

    <HeritageCard
      v-for="site in sites"
      :key="site.id"
      :id="site.id"
      :title="site.title"
      :description="site.description"
      :image="site.image"
    />

  </section>
</template>

<script>
import HeritageCard from '../molecules/HeritageCard.vue'

export default {
  name: 'HeritageGrid',

  components: {
    HeritageCard
  },

  props: {
    sites: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

.heritage-grid {
  width: 100%;

  display: grid;

  grid-template-columns:
    repeat(
      auto-fit,
      minmax(260px, 280px)
    );

  justify-content: center;

  gap: 24px;
}


@media (max-width: 600px) {

  .heritage-grid {
    grid-template-columns:
      minmax(0, 1fr);
  }

}

</style>