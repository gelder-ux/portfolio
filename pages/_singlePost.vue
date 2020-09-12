<template>
  <div id="post-page" class="page-wrapper post-page main">
    <site-hero :title="title" :subtitle="subtitle" :image="featureImage" :role="role" :market="market" :date="date" :duration="duration" :users="users">
      <!-- <span
        v-if="author && $siteConfig.posts.displayAuthor"
        class="author-wrapper"
      >
        <strong>Author:</strong> {{ author }}
      </span>
      <span v-if="date" class="date-wrapper">
        <strong>Published on:</strong> {{ date }}
      </span> -->
    </site-hero>
    <main-section :one-column-constrained="true">
      <template v-slot:default>
        <div class="post-wrapper">
          <!-- <div class="post-meta-details">
            <span v-if="role"><strong>Role: </strong>{{ role }}</span>
            <span v-if="market"><strong>Market: </strong>{{ market }}</span>
            <span v-if="duration"><strong>Project Length: </strong>{{ duration }}</span>
            <span v-if="users"><strong>Users: </strong>{{ users }}</span>
          </div> -->
          <markdown :markdown="$store.state.content" />
          <!-- <div class="other-posts">
            <h6 class="subtitle is-size-4">
              Related Projects
            </h6>
            <posts-grid :number="3" :category="category" :exclude="slug" />
          </div> -->
          <!-- <disqus-comments :identifier="$route.params.singlePost" /> -->
        </div>
      </template>
      <!-- <template v-slot:sidebar>
        <post-sidebar />
      </template> -->
    </main-section>
    <site-footer></site-footer>
  </div>
</template>
<script>
import { mapState } from 'vuex'
import { setPageData, getFormattedDate } from '../helper'
// import 'highlight.js/styles/github.css'
import Markdown from '~/components/Markdown'
import PostSidebar from '~/components/PostSidebar'
export default {
  components: {
    Markdown,
    PostSidebar
  },
  computed: {
    ...mapState([
      'title',
      'subtitle',
      'featureImage',
      'underSubtitle',
      'author',
      'category',
      'slug',
      'role',
      'market',
      'duration',
      'users'
    ]),
    date() {
      return getFormattedDate(this.$store.state.date)
    },
    url() {
      return `${process.env.URL}/${this.$route.fullPath}`
    }
  },
  fetch({ store, params }) {
    setPageData(store, { resource: 'post', slug: params.singlePost })
  }
}
</script>
<style scoped lang="scss">
.edit-post {
  margin-bottom: 20px;
}
.post-meta-details {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  margin-bottom: 1rem;
  @media screen and (min-width: 1024px) {
    margin-bottom: 4rem;
  }
  & span {
    margin-bottom: 1rem;
    background: #f7f7f7;
    border-radius: 4rem;
    padding: 0.25rem 1rem;
    margin-right: 1rem;
    font-size: 0.75rem;
    @media screen and (min-width: 1024px) {
      font-size: 1rem;
    }
  }
}
</style>
