<template>
  <div>
    <section class="section section--dark">
      <div class="section__content heading">
        <h2 class="text-center uppercase">{{companyName}}</h2>
      </div>
    </section>
    <section class="section section--light">
      <div class="mission section__content">
        <p class="mission__title q-mb-lg">WHO WE ARE</p>
        <p class="mission__text"
          v-for="(p, index) in companyInfo.we"
          :key="index"
          v-html="p"
          />
        <div class="text-center">
          <button class="btn black" @click="$root.$emit('showContact')">Have something in mind?</button>
        </div>
      </div>
    </section>
    <section class="section section--dark q-py-lg">
      <h3 class="text-center">OUR TEAM</h3>
    </section>
    <section class="section section--light">
      <div class="team__item" v-for="member in companyInfo.team" :key="member.id">
        <img class="team__item__img" v-if="member.image" :src="`statics/images/team/${member.image}`">
        <img class="team__item__img" v-else src="~assets/images/team/harvey.jpg">
        <div class="team__item__side">
          <h6 class="name">{{member.name}}</h6>
          <p class="handle" @click="openURL(`https://twitter.com/${member.handle}`)">{{member.handle}}</p>
          <p class="text" v-if="member.description" v-html="member.description"/>
          <p class="text" v-else>Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquid, perspiciatis voluptate! Totam nam molestias odit vel necessitatibus numquam dolore qui delectus. Odit itaque illum, dicta labore consequatur vitae animi, doloribus voluptates cum odio ab quos ullam excepturi nihil unde. Cum, quaerat doloremque. Minima, cumque consectetur adipisci voluptatibus explicabo iste quis.</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import {name} from '../../package.json'
import DATA from 'statics/data/about.json'
import {openURL} from 'quasar'
export default {
  name: 'About',
  created () {
    this.companyName = name
    this.companyInfo = DATA
  },
  methods: {
    openURL
  }
}
</script>

<style lang="stylus" scoped>
@import '~variables'
.mission {
  padding 3rem 0
  &__title {
    text-align center
    color $secondary
    text-transform uppercase
    font-weight 700
    font-size 1rem
  }
  &__text {
    text-indent 3rem
  }
  .btn {
    margin 0 auto
    margin-top 2rem
  }
}
.team {
  &__item {
    margin 0 auto
    padding 2.5rem 10vw
    display flex
    align-items flex-start
    &:not(:last-child) {
      border-bottom 1px solid $accent-light
    }
    &:hover {
      background-color $accent-lightest
    }

    &__img {
      height 4.5rem
      border-radius 50%
      margin-right 2rem
    }

    &__side {
      .name {
        margin 0
        padding-bottom .5rem
        font-family $font-display
        font-size 1.15rem
        font-weight 700
        color $accent-darkest
      }
      .handle {
        color $secondary
        font-family $font-display
        font-size .7rem
        margin 0
        display inline-block
        cursor pointer
        &:hover {
          font-weight 700
          font-style italic
        }
      }
      .text {
        margin-top .2rem
        margin-bottom 0
      }
    }
  }
}
</style>
