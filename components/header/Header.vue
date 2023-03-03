<template>
  <header class="site-header">
    <div class="container full-height flex f-space-between">
      <div class="flex flex-row h-center">
        <headerLogo />
        <div class="primary-nav">
          <headerMainNav />
        </div>
      </div>
      <div class="flex flex-row h-end full-height">
        <button
          class="btn--primary menu-toggle"
          :class="{ 'is-active': isActive }"
          @click="toggleMenu"
        >
          <span class="bzi-bars"></span>
        </button>
        <headerSecondNav />
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'DefaultHeader',
  data() {
    return {
      isActive: false,
    }
  },
  methods: {
    toggleMenu() {},
  },
}
</script>

<style lang="scss" scoped>
.site-header {
  display: flex;
  position: fixed;
  z-index: 10;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #fff;
  height: 60px;
  box-shadow: 0px 3px 4px rgba(palette('black'), 0.15);

  @media #{$large} {
    height: 70px;
  }

  .menu-toggle {
    position: relative;
    display: block;
    padding: 4px;
    margin-right: 8px;
    z-index: 2;
    background-color: transparent;

    @media #{$large} {
      display: none;
    }

    .bzi-bars:before {
      font-size: 24px;
      color: palette('black');
    }

    &:hover {
      background: transparent;
    }

    &.is-active {
      background-color: palette('white');
      .bzi-bars:before {
        content: '\e93d';
        color: palette('black');
      }
    }
  }
}

.header-right {
  > * {
    margin-right: 6px;

    &:last-child() {
      margin-right: 0px;
    }
  }
}

.primary-nav {
  @media #{$large} {
    margin-left: 78px;
  }
}
</style>
