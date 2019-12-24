<template>
  <div id="about-page" class="page-wrapper about-page content-page">
    <site-hero
      title="About"
      subtitle=""
      image="/uploads/about-hero.jpg"
    ></site-hero>
    <main-section :one-column-constrained="true">
      <template v-slot:default>
        <!-- prettier-ignore -->
        <p>
          Will is a UX Designer working for CBORD and Horizon Software. His
          main topics of interest include design systems, accessibility, and
          human-centered design. He and his wife live in New York with their
          two cats, Jimmy and Tula.
        </p>
      </template>
      <template v-slot:sidebar>
        <post-sidebar />
      </template>
    </main-section>
  </div>
</template>
<script>
export default {
  head() {
    return {
      title: `About | ${this.$siteConfig.siteName}`
    }
  }
}
</script>
