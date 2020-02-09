<template>
  <nav class="menu">
    <nuxt-link to="/aboutme" class="no-underline">
      <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-about"></use>
      </svg>ABOUT ME
    </nuxt-link>
    <nuxt-link to="/archive" class="no-underline">
      <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-archive"></use>
      </svg>ACHIEVEMENTS
    </nuxt-link>
    <nuxt-link to="/laboratory" class="no-underline">
      <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-lab"></use>
      </svg>PROJECT
    </nuxt-link>
  </nav>
</template>

<script>
export default {
  methods: {

  }
};
</script>

<style lang="scss" scoped>
@import "~assets/sass/app";
.menu {
  position: fixed;
  top: 5.2em;
  a {
    display: block;
    margin-bottom: 0.8em;
    padding-left: 1em;
    height: 3em;
    font-size: 1.2em;
    color: #666;
    line-height: 3em;

    &.nuxt-link-exact-active {
      color: $base-color;
      background-color: #fff;
    }
    &.juejin {
      .icon {
        vertical-align: -0.05em;
      }
    }
  }
  .icon {
    width: 1em;
    height: 1em;
    margin-right: 0.5em;
  }
}
</style>


