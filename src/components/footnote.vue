<template>
  <footer class="section section--dark">
    <div class="content">
      <div class="side side--links">

        <div class="logo">
          <p class="logo__icon">Δ</p>
          <p class="logo__text">devlabs</p>
        </div>

        <ul>
          <router-link tag="li" exact to="/">Home</router-link>
          <li>Privacy Policy</li>
          <li>Terms and Conditions</li>
        </ul>

      </div>
      <div class="side side--copyright">
        <div class="socials">
          <div class="socials__link" @click="openURL('https://twitter.com/DevLaboratories')">
            <q-icon name="fab fa-twitter" size="1.4rem"/>
          </div>
          <div class="socials__link" @click="openURL('https://www.facebook.com/devlaboratories/')">
            <q-icon name="fab fa-facebook" size="1.4rem"/>
          </div>
          <div class="socials__link">devlaboratories@gmail.com</div>
        </div>
        <div class="q-mt-lg text-right copyright-text">Copyright &copy; 2018 Devlabs. All rights reserved.</div>
      </div>
    </div>
  </footer>
</template>

<script>
import {openURL} from 'quasar'
export default {
  name: 'Footnote',
  methods: {
    openURL
  }
}
</script>

<style lang="stylus" scoped>
@import '~variables'

.content {
  width 80vw
  margin 0 auto
  padding 3rem 0 2rem 0
  display flex
  justify-content space-between
  align-items center
  align-content space-between
  flex-wrap wrap
  +respond-max($breakpoint-sm) {
    width 90vw
  }
}
.logo {
  display flex
  align-items center
  color $primary-dark
  &__icon {
    font-size 2.5rem
    font-family 'Times New Roman', Times, serif
    margin-right .5rem
    color currentColor
    font-weight 700
  }
  &__text {
    color currentColor
    font-size 1.2rem
    font-family $font-display
    text-transform uppercase
    font-weight 700
    letter-spacing .2rem
  }
}
.side {
  flex 1 0 40%

  +respond-max($breakpoint-xs) {
    flex-direction column
  }

  &--links {
    display flex
    align-items center
    ul {
      display inline-block
      list-style none
      li {
        font-size .8rem
        cursor pointer
        color $accent-neutral
        transition .3s all ease
        text-transform uppercase
        letter-spacing .1rem
        &:hover {
          color $primary-dark
          text-decoration underline
        }
      }
    }
  }

  &--copyright {
    color $accent-neutral
    font-size .7rem
    .socials {
      display flex
      justify-content flex-end
      align-items center
      +respond-max($breakpoint-sm) {
        justify-content center
      }
      &__link {
        margin-left 1rem
        transition all .3s ease
        cursor pointer
        &:hover {
          color $primary-dark
        }
      }
    }
    .copyright-text {
      +respond-max($breakpoint-sm) {
        text-align center
      }
    }
  }
}
</style>
