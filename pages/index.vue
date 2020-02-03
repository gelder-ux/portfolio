<template>
  <div id="home-page" class="page-wrapper home-page main">
    <site-hero :title="title" :subtitle="subtitle" :image="featureImage">
      <!-- <button
        class="button is-primary"
        @click="$eventBus.$emit('modal-triggered', 'newsletter-modal')"
      >
        Subscribe To Newsletter
      </button> -->
      <section class="about-me">
        <p>I am passionate about clean & concise user experiences for businesses, employees, and consumers alike. My strengths are in facilitation, visualizing problems, interface design, accessibility, and front end development.</p>
        <p>Currently, I am a Senior Service Designer at CBORD & Horizon Software where I design solutions serving the K-12, Higher Education, Senior Living, and Healthcare markets.</p>
      </section> 
    </site-hero>
    <main-section theme="one-column">
      <template v-slot:default>
        <h3 class="grid-title">Work</h3>
        <!-- All Posts -->
        <posts-grid />
      </template>
      <!-- <template v-slot:sidebar>
        Nothing here
      </template> -->
    </main-section>
    <site-footer></site-footer>
    <!-- <news-letter-form-modal /> -->
  </div>
</template>

<script>
import { mapState } from 'vuex'
import { setPageData } from '../helper'
import NewsLetterFormModal from '~/components/NewsLetterFormModal'
import { getFormattedDate } from '~/helper'
export default {
  name: 'HomePage',
  head() {
    return {
      title: `${this.$siteConfig.siteName} | UX Designer`
    }
  },
  components: {
    NewsLetterFormModal
  },
  computed: {
    ...mapState(['title', 'subtitle', 'featureImage','date','market','role']),
    datePretty() {
      return getFormattedDate(this.date)
    }
  },
  fetch({ store, params }) {
    setPageData(store, { slug: 'home' })
  }
}
</script>

<style lang="scss">
.home-page .under-subtitle {
  border-top: none;
}

.main {
  grid-area: main;
  overflow: auto;
}

.grid-title {
  font-size: 2rem;
  text-align: center;
  margin-bottom: 2rem;
}

.about-me {
  text-align: left;
  margin-top: 1rem;
  max-width: 500px;
  font-size: 1rem;
  @media screen and (min-width: 1024px) {
    font-size: 1.25rem;
  }
  p {
    margin-top: 1rem;
  }
}

html {
  background-color: #fff;
  overflow: auto;
}

body {
  font-family: 'Asap', sans-serif;
}
</style>
