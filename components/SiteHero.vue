<template>
  <section :class="`hero is-large hero-theme-${computedTheme}`">
    <img
      class="hero-bg-img"
      :src="responsiveImage.src"
      :lazy="false"
      :srcset="responsiveImage.srcSet"
    />
    <div class="hero-body">
      <div class="container">
        <h1 class="title fadeInUp">
          {{ title }}
        </h1>
        <h2 class="subtitle fadeInUp slower">
          {{ subtitle }}
        </h2>
        <!-- <div class="details-wrapper">
          <span v-if="role">Role: {{ role }}</span>
          <span v-if="date">Timeframe: {{ datePretty }}</span>
          <span v-if="market">Market: {{ market }}</span>
        </div> -->
        <div
          v-if="$slots.default"
          class="under-subtitle fadeInDown slower"
        >
          <slot />
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import { getFormattedDate } from '~/helper'
export default {
  name: 'SiteHero',
  props: {
    title: { type: String, default: '' },
    subtitle: { type: String, default: '' },
    role: { type: String, default: '' },
    date: { type: String, default: '' },
    market: { type: String, default: '' },
    image: { type: String, default: '' },
    color: { type: String, default: '#469af0' },
    theme: { type: String, default: '' }
  },
  computed: {
    responsiveImage() {
      if (this.image.indexOf('/uploads') === 0) {
        return require(`~/assets${this.image}`)
      }
      return { src: this.image, srcSet: '' }
    },
    computedTheme() {
      if (this.theme === '' && this.$siteConfig.hero.theme) {
        return this.$siteConfig.hero.theme
      }
      return this.theme || 'mist'
    },
    datePretty() {
      return getFormattedDate(this.date)
    }
  }
}
</script>

<style lang="scss" scoped>
.hero {
  background-size: cover !important;
  background-position: center;
  text-align: center;
  position: relative;
}

.title {
  font-weight: 600;
  @media (min-width: 768px) {
    font-size: 6rem;
  }
}
.subtitle,
.under-subtitle {
  padding: 0;
  margin: 0;
}
.subtitle {
  font-size: 1.5rem;
  margin-bottom: 0 !important;
}
.under-subtitle {
  display: flex;
  justify-content: center;
  font-size: 0.8rem;
  // border-top: 2px solid $primary;
}
.opti-image {
  opacity: 0;
}
.opti-image-loaded {
  opacity: 0.12;
  animation: blurIn 4.5s ease;
}
</style>
<style lang="scss">
.hero {
  &.is-large .hero-body {
    padding-top: 4rem;
    @media screen and (min-width: 1024px) {
      padding-top: 14rem;
    }
    padding-bottom: 8rem;
  }

  overflow: auto;
  .hero-bg-img {
    display: none;
    // position: absolute;
    // top: 0;
    // left: 0;
    // right: 0;
    // bottom: 0;
    // object-fit: cover;
    // width: 100%;
    // height: 100%;
  }
  .opti-image {
    opacity: 0;
  }
  .opti-image-loaded {
    opacity: 1;
  }
}
.hero-theme-mist {
  .hero-bg-img {
    filter: grayscale(1);
  }
  .opti-image-loaded {
    opacity: 0.12;
    animation: blurInGrayscale 4.5s ease;
  }
}
.hero-theme-dark,
.hero-theme-light {
  &.hero:after {
    content: '';
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.65);
    position: absolute;
  }
  .hero-body {
    position: relative;
    z-index: 2;
    .container {
      display: flex;
      flex-direction: column;
    }
  }
}
.hero-theme-dark {
  .title,
  .subtitle,
  .under-subtitle,
  .under-subtitle strong {
    color: white;
  }
}
.hero-theme-light.hero {
  &:after {
    background: rgba(255, 255, 255, 1);
  }
}
</style>
