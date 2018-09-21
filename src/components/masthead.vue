<template functional>
  <header>
    <div class="header__content">
      <h1 class="capitalize">{{props.companyName || 'devlabs'}}</h1>
      <div class="heading">{{props.heading || 'Welcome to our lab'}}</div>
      <p>{{props.intro || 'We are digital artisans and passionate software craftsmen fueled by caffeine. We are obsessed in figuring out the best solutions that clients need. We are the catalyst that your idea needs. Let\'s build it.'}}</p>
      <button class="btn black" @click="listeners.click">Let's get started</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Masthead',
  props: ['companyName', 'heading', 'intro']
}
</script>

<style lang="stylus" scoped>
@import '~variables'
header {
  background-color $accent-light
  background linear-gradient(
    to bottom,
    $primary-light,
    rgba($accent-lightest, .10),
    $primary-light
    ),
    url('~assets/images/bulb.jpg')
  background-size cover
  background-position center
  height 100vh
}

.header__content {
  margin 0 auto
  width 80vw
  height 100%
  display grid
  align-content center
  justify-items start
  grid-row-gap 2rem
  +respond-max($breakpoint-xxs) {
    grid-row-gap .2rem
  }
  h1 {
    margin 0
    font-size 1.5rem
    color $accent-neutral
    font-family $font-primary
  }
  .heading, p {
    width 50%
    +respond-max($breakpoint-sm) {
      width 80%
    }
    +respond-max($breakpoint-xs) {
      width 100%
    }
  }
  .heading {
    font-size 4.5rem
    font-family $font-display
    line-height 4.5rem
    +respond-max($breakpoint-xs) {
      font-size 3rem
      line-height 3rem
    }
    +respond-max($breakpoint-xxs) {
      font-size 2.8rem
    }
  }
  p {
    font-size 1rem
    color $accent-dark
    +respond-max($breakpoint-xxs) {
      font-size .8rem
    }
  }
}
</style>
