<template>
  <div class="q-pa-xl bg-primary contact">
    <q-btn size="sm" round flat icon="fas fa-times" color="white" class="close-btn" v-close-overlay />
    <h5 class="title">Have something in mind?</h5>
    <form name="Inquiries" @submit.prevent="submit" method="POST" data-netlify="true" data-netlify-honeypot="fullname">
      <input class="hidden" name="fullname"/>
      <input
        placeholder="Your name"
        v-model="name"
        name="name"
        @blur="$v.name.$touch"
        type="text"
        required
        :class="{ 'invalid-form': $v.name.$error }"
        class="input"/>
      <input
        placeholder="Email"
        v-model="email"
        name="email"
        @blur="$v.email.$touch"
        type="email"
        required
        :class="{ 'invalid-form': $v.email.$error }"
        class="input"/>
      <textarea
        placeholder="What's on your mind?"
        v-model="message"
        name="message"
        @blur="$v.message.$touch"
        required
        :class="{ 'invalid-form': $v.message.$error }"
        />
      <div class="actions q-mt-lg">
        <div class="socials">
          <q-icon @click.native="openURL(links.twitter)" class="social twitter" name="fab fa-twitter" size="1.5rem" />
          <q-icon @click.native="openURL(links.facebook)" class="social facebook" name="fab fa-facebook-square" size="1.5rem" />
        </div>
        <q-btn :disable="$v.$invalid" type="submit" size="md" class="submit" color="secondary">Submit</q-btn>
      </div>
      <a class="link mail" :href="`mailto:${links.email}`">{{links.email}}</a>
    </form>
  </div>
</template>

<script>
import {required, email} from 'vuelidate/lib/validators'
import {openURL} from 'quasar'
import axios from 'axios'

import LINKS from '../statics/data/links.json'
export default {
  name: 'Contact',
  created () {
    this.links = LINKS
  },
  data () {
    return {
      name: '',
      email: '',
      message: ''
    }
  },
  validations: {
    name: { required },
    email: { required, email },
    message: { required }
  },
  methods: {
    openURL,
    async submit (event) {
      const url = event.target.action
      const data = this.serialize({
        'form-name': 'devlabs-inquiry',
        name: this.name,
        email: this.email,
        message: this.message
      })
      try {
        await axios.post(url, data, {
          headers: {
            'Content-Type': 'application/x-www-form-urlencoded'
          }
        })
        this.$emit('submitted')
      } catch (error) {
        this.$emit('error')
      }
    },
    serialize (obj) {
      let str = []
      for (let p in obj) {
        if (obj.hasOwnProperty(p)) {
          str.push(encodeURIComponent(p) + '=' + encodeURIComponent(obj[p]))
        }
      }
      return str.join('&')
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~variables'

.contact {
  width 40vw
  +respond-max($breakpoint-md) {
    width 70vw
  }
  +respond-max($breakpoint-sm) {
    width 100%
    height 100%
  }

  .title {
    margin 0
    margin-bottom 1rem
    color $accent-light
    +respond-max($breakpoint-sm) {
      margin-top 5vh
    }
  }
}

form {
  width 100%
  .label {
    color $accent-neutral
    margin-bottom .3rem
    margin-top .5rem
  }

  .input, textarea {
    font-family $font-display
    color $accent-darkest
    font-size .8rem
    padding .4rem
    border-radius 2px
    display block
    width 100%
    border none
    border-bottom 3px solid transparent
    transition all .4s ease-in

    &:focus {
      outline none
      box-shadow 0 1rem 2rem rgba($secondary, .1)
      border-bottom: 3px solid $secondary
      &:invalid {
        border-bottom: 3px solid $negative
      }
    }

    &::-webkit-input-placeholder {
      color $accent-dark
    }
  }

  .invalid-form {
    background rgba($negative, .2)
    border-bottom: 3px solid $negative
    color $accent-neutral
    &::-webkit-input-placeholder {
      color $accent-neutral
    }
  }

  .input {
    height 2rem
    margin-bottom 1.4rem
  }

  textarea {
    min-height 10rem
    min-width 100%
  }

  .actions {
    display flex
    justify-content space-between
    align-items center
  }

  .mail {
    margin-top .7rem
    display block
    font-size .7rem
    text-align right
  }

  .social {
    cursor pointer
    transition all .2s ease-in

    &:hover {
      transform scale(1.2)
      filter brightness(200%)
    }

    &:not(:last-child) {
      margin-right 1rem
    }

    &.twitter {
      color #1dcaff
    }

    &.facebook {
      color #3b5998
    }
  }
}

.close-btn {
  position absolute
  top 1rem
  right 1rem
}
</style>
