<template>
  <div class="card">
    <nuxt-link :to="link">
      <div class="card-image">
        <figure :class="`image is-${imageRatioClass}`">
          <opti-image
            v-if="image"
            :src="responsiveImage.src"
            :srcset="responsiveImage.srcSet"
            :width="imageRatio[0]"
            :height="imageRatio[1]"
            :sizes="`(min-width: 768px) ${100 / $siteConfig.posts.perRow}vw`"
          />
          <loading-spinner position="absolute" />
        </figure>
      </div>
      <div class="card-content">
        <div class="media">
          <div class="media-content">
            <h3
              :class="
                `title
                is-5
                has-text-weight-light
                ${title ? '' : 'empty-content-placeholder'}`
              "
            >
              {{ title }}
            </h3>
            <!-- <h4
              :class="{
                subtitle: true,
                'is-6': true,
                'empty-content-placeholder': !$slots.default
              }"
            >
              <slot></slot>
            </h4> -->
            <slot></slot>
          </div>
        </div>
      </div>
    </nuxt-link>
  </div>
</template>
<script>
const imageDimensionDefault = '16x9'
export default {
  props: {
    title: { type: String, default: '' },
    image: { type: String, default: '' },
    link: { type: String, default: '' },
    imageDimensions: { type: String, default: imageDimensionDefault }
  },
  computed: {
    imageRatioClass() {
      const imageDimensions = this.imageDimensions || imageDimensionDefault
      return imageDimensions.toLowerCase().replace('x', 'by')
    },
    imageRatio() {
      const imageDimensions = this.imageDimensions || imageDimensionDefault
      return imageDimensions
        .toLowerCase()
        .split('x')
        .map((size) => {
          return size * 2000
        })
    },
    responsiveImage() {
      if (this.image.indexOf('/uploads') === 0) {
        return require(`~/assets${this.image}`)
      }
      return { src: this.image, srcSet: '' }
    }
  }
}
</script>
<style scoped lang="scss">
.subtitle {
  opacity: 0.5;
  font-size: 0.8rem;
}
.empty-content-placeholder {
  background: transparent;
  color: transparent;
  position: relative;
  height: 1em;
  &:before {
    transform-origin: left;
    content: '';
    background: #eee;
    width: 100%;
    position: absolute;
    top: 0;
    bottom: 0;
    animation: fillHorizontal 2s linear infinite;
  }
  &.subtitle {
    width: 70%;
  }
}
</style>
<style lang="scss">
.opti-image-loaded + .spinner-wrapper {
  display: none;
}
.card img {
  transition: 0.8s ease-in-out all;
  &:hover {
    transform: scale(1.02);
  }
}
.card {
  border-radius: 1rem;
  .image {
    border-radius: 1rem 1rem 0 0;
  }
  box-shadow: none;
  border: 1px solid #efefef;
}
</style>
