<template>
  <nav
    class="main-nav flex flex-col flex-lg-row v-start lg-v-center is-active"
    :class="{ 'is-active': isActive }"
  >
    <ul class="p-0 lg-flex">
      <li
        v-for="(nav, i) in menus"
        :key="i"
        class="main-nav__item"
        @click="closeMenu"
      >
        <nuxt-link class="header-link" :to="`${nav.url ? nav.url : '/'}`">{{
          nav.title
        }}</nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: {
    isActive: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      menus: [
        {
          title: 'Documentation',
          url: '/documentation',
        },
        {
          title: 'Github',
          url: '/github',
        },
        {
          title: 'About',
          url: '/about',
        },
      ],
    }
  },
  methods: {
    closeMenu() {},
  },
}
</script>

<style lang="scss" scoped>
.main-nav {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  background-color: white;
  transform: translateX(100%);
  transition: all 0.2s linear;
  z-index: 1;
  padding-top: 3em;

  @media #{$large} {
    position: relative;
    height: 100%;
    padding: 0;
    transform: translateX(0);
    background-color: transparent;
  }

  &.is-active {
    transform: translateX(0);
  }

  li {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding: 10px 16px;

    @media #{$large} {
      padding: 0;
      justify-content: flex-start;
    }
  }

  .main-nav__item {
    .header-link {
      color: palette('black');
      position: relative;
      display: flex;
      align-items: center;
      transition: all 0.15s linear;
      text-align: right;
      padding: 5px 10px;
      margin-right: 1rem;

      &:hover,
      &:focus,
      &.is-active {
        color: palette('blue');
      }

      &:after {
        transition: all 0.25s ease;
      }
    }

    .nuxt-link-active,
    .link-active {
      color: palette('blue');
    }
  }

  a {
    color: palette('grey');
    height: 100%;
    font-size: 26px;
    user-select: none;
    font-weight: 700;
    -webkit-user-drag: none;

    @media #{$large} {
      color: palette('dark-grey');
      font-size: 16px;
    }

    &:hover {
      color: palette('blue');
    }
  }
}
</style>
