<template functional>
  <nav>
    <ul>
      <router-link tag="li" to="/" exact>
        <span class="logo">Δ</span>
      </router-link>
      <router-link tag="li" to="/about">about</router-link>
      <router-link tag="li" to="/work">work</router-link>
      <router-link tag="li" to="/blog">blog</router-link>
      <li>contact</li>
    </ul>
    <!-- <q-btn round flat color="black" icon="fas fa-bars" class="hamburger"/> -->
  </nav>
</template>

<script>
export default {
  name: 'Navigation'
}
</script>

<style lang="stylus" scoped>
@import '~variables'
.router-link-active {
  color $secondary
  transform scale(1.05)
}
nav {
  z-index 100
  position absolute
  display float
  top 2rem
  right 12rem
  width 36vw
  padding 0
  +respond-max($breakpoint-md) {
    right 2rem
  }
  +respond-max($breakpoint-sm) {
    width 100%
    right 0
  padding 0 10%
  }
  ul {
    padding 0
    margin 0
    width 100%
    list-style none
    display flex
    align-items center
    justify-content space-between
    li {
      text-transform uppercase
      padding 5px
      display inline-block
      color $accent-neutral
      cursor pointer
      transition .5s ease
      &:hover {
        color $primary-dark
        transform scale(1.07)
      }
    }
  }
}
.logo {
  text-transform uppercase
  font-size 2.5rem
  font-family serif
  font-weight bold
}
</style>
