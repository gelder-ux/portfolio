<template>
  <nav
    class="navbar navigation" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <hamburger-button @click="active = !active" />
      <nuxt-link class="navbar-item logo" to="/">
        <site-logo v-if="$siteConfig.logo === 'logo-component'" />
        <img
          v-else
          :src="$siteConfig.logo"
          :alt="$siteConfig.siteName"
          class="logo"
        />
      </nuxt-link>
    </div>

    <div
      :class="{
        'navbar-menu': true,
        'is-active': active
      }"
    >
      <ul class="navbar-end">
        <li
          v-for="item in $siteConfig.mainMenu"
          :key="item.link"
          class="navbar-item"
          @click="active = false"
        >
          <component
            :is="item.link.startsWith('http') ? 'a' : 'nuxt-link'"
            :href="item.link"
            :to="item.link"
            :target="item.target ? item.target : '_self'"
          >
            {{ item.name }}
          </component>
        </li>
        <li class="navbar-item cta-wrapper">
          <a class="cta" href="mailto:willgelder9@gmail.com?subject=Hello Will">Email Me</a>
        </li>
        <!-- <li class="navbar-item site-search-wrapper">
          <site-search />
        </li> -->
      </ul>
    </div>
  </nav>
</template>
<script>
import SiteSearch from '~/components/SiteSearch'
import HamburgerButton from '~/components/HamburgerButton'
export default {
  name: 'SiteNav',
  components: { SiteSearch, HamburgerButton },
  data() {
    return {
      active: false
    }
  }
}
</script>
<style lang="scss" scoped>
.navigation {
  grid-area: nav;
  display: flex;
  width: 100%;
  flex-direction: column;
  justify-content: space-between;
  @media screen and (min-width: 1024px) {
    justify-content: flex-start;
    width: auto;
    height: 100%;
  }
}

a.logo {
  @media screen and (min-width: 1024px) {
    width: 100%;
    display: flex;
    justify-content: center;
  }  
  &:hover,
  &:focus {
    background-color: mix(white, #191A20, 5);
  }
}

.navbar {
  background-image: linear-gradient(179deg, #191A20 0%, #1E202D 100%);
  width: 100%;
  &-brand {
    justify-content: space-between;
    @media screen and (min-width: 1024px) {
      justify-content: center;
    }
  }
  &-end {
    @media screen and (min-width: 1024px) {
      margin-left: 0;
    }
  }
}

.navbar-item img {
  max-height: 4rem;
}
.site-search-wrapper {
  transform: translateX(5px);
  @media (max-width: 1023px) {
    display: none;
  }
}
.navbar-burger {
  width: 5rem;
  height: 5rem;
  margin-left: 0;
  color: #fff;
  &:hover,
  &focus {
    background-color: mix(white, #191A20, 5);
  }
}

.navbar-menu a {
  display: block;
}

.navbar-menu {
  flex-grow: 0;
  box-shadow: none;
  padding: 0;
  background-image: linear-gradient(179deg, #191A20 0%, #1E202D 100%);
  @media screen and (min-width: 1024px) {
    background-image: none;
  }

  & ul {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    width: 100%;
    & li {
      width: 100%;
      padding: 0;
      &.cta-wrapper {
        padding: 1rem;
        position: fixed;
        bottom:0;
        @media screen and (min-width: 1024px) {
          position: relative;
          bottom: initial;     
        }
        // &:hover,
        // &focus {
        //   background-color: mix(white, #191A20, 5);
        // }
      }
      a {
        width: 100%;
        padding: 1rem 2rem;
        color: #fff;
        font-weight: 600;
        &:hover,
        &:focus {
          color: #fff;
          background-color: mix(white, #191A20, 5);
        }
        &.cta {
          background-color:#acfcc4;
          border-radius: 4rem;
          color:#1b1d26;
          padding: 1rem 1rem;
          text-align: center;
          font-size: 1rem;
          @media screen and (min-width: 1024px) {
            padding: 0.75rem 0;
            font-size: 1rem;
          }
        }
      }
    }
  }
  &.is-active {
    position: fixed;
    top: 80px;
    height: 100%;
    width: 100%;
    display: flex;
    flex-direction: column;
    @media screen and (min-width: 1024px) {
      position: relative;
      top: initial;
      height: auto;
      flex-direction: row;
    }
    & ul {
      flex-grow: 0;
      margin-bottom: 10rem;
      @media screen and (min-width: 1024px) {
        flex-grow: 1;
        margin-bottom: initial;
      }
      & a {
        font-size: 1rem;
        padding: 1.5rem 2rem;
        @media screen and (min-width: 1024px) {
          font-size: initial;
          padding: 1rem 2rem;
        }
      }
    }
  }
}
</style>
