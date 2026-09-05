<template>
  <article class="heritage-card">

    <div class="heritage-card__image">

      <BaseImage
        :src="image"
        :alt="title"
      />

      <span class="heritage-card__badge">
        Heritage Site
      </span>

    </div>


    <div class="heritage-card__content">

      <BaseTypography
        tag="h3"
        variant="subheading"
      >
        {{ title }}
      </BaseTypography>


      <BaseTypography variant="body">
        {{ description }}
      </BaseTypography>


      <div class="heritage-card__action">

        <BaseButton @click="viewDetails">
          View Details
          <span aria-hidden="true">
            →
          </span>
        </BaseButton>

      </div>

    </div>

  </article>
</template>

<script>
import BaseButton from '../atoms/BaseButton.vue'
import BaseTypography from '../atoms/BaseTypography.vue'
import BaseImage from '../atoms/BaseImage.vue'

export default {
  name: 'HeritageCard',

  components: {
    BaseButton,
    BaseTypography,
    BaseImage
  },

  props: {

    id: {
      type: Number,
      required: true
    },

    image: {
      type: String,
      required: true
    },

    title: {
      type: String,
      required: true
    },

    description: {
      type: String,
      required: true
    }

  },

  methods: {

    viewDetails() {
      this.$router.push(
        `/heritage/${this.id}`
      )
    }

  }
}
</script>

<style scoped>

.heritage-card {
  display: flex;

  flex-direction: column;

  height: 100%;

  overflow: hidden;

  background:
    var(--color-surface);

  border:
    1px solid rgba(0, 0, 0, 0.06);

  border-radius:
    var(--radius-lg);

  box-shadow:
    var(--shadow-sm);

  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease;
}


.heritage-card:hover {
  transform:
    translateY(-6px);

  box-shadow:
    var(--shadow-lg);
}


.heritage-card__image {
  position: relative;

  height: 210px;

  overflow: hidden;
}


.heritage-card__image :deep(.base-image) {
  width: 100%;

  height: 100%;

  object-fit: cover;

  transition:
    transform 0.5s ease;
}


.heritage-card:hover
.heritage-card__image
:deep(.base-image) {
  transform:
    scale(1.05);
}


.heritage-card__badge {
  position: absolute;

  top: 14px;

  left: 14px;

  padding:
    6px 10px;

  border-radius: 999px;

  background:
    rgba(255, 255, 255, 0.92);

  color:
    var(--color-primary);

  font-size:
    0.7rem;

  font-weight: 800;

  letter-spacing:
    0.04em;

  backdrop-filter:
    blur(5px);
}


.heritage-card__content {
  display: flex;

  flex-direction: column;

  flex: 1;

  padding: 22px;

  gap: 10px;
}


.heritage-card__content
:deep(.typography--subheading) {
  color:
    var(--color-text);

  font-size:
    1.25rem;
}


.heritage-card__content
:deep(.typography--body) {
  color:
    var(--color-text-muted);

  font-size:
    0.92rem;

  line-height:
    1.65;
}


.heritage-card__action {
  margin-top: auto;

  padding-top: 12px;
}


.heritage-card__action
:deep(.base-button) {
  width: 100%;
}


@media (max-width: 600px) {

  .heritage-card__image {
    height: 220px;
  }

}

</style>