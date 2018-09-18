<template>
  <div class="">
    <section class="section section--dark">
      <div class="section__content heading">
        <h2 class="text-center">DEVLABS</h2>
      </div>
    </section>
    <section class="section section--light">
      <div class="mission section__content">
        <p class="mission__title q-mb-lg">WHO WE ARE</p>
        <p class="mission__text">
          We're a group of passionate individuals based in Manila, Philippines ready and eager to work with you in building targeted software solutions that best suit your needs and demands &mdash; just the right balance of form that compliments function, technical expertise, and user-oriented along with technical consulting.
        </p>
        <p class="mission__text">
          We are life-long learners. We take caffeine and energy drinks, turn it into bits and circuits. We believe that life is too short to be mediocre - yes, it's not easy, and that's why we're doing this. There's no greater joy than witnessing your own ideas manifest into reality.
        </p>
        <p class="mission__text">
          Call it divinity or evolution, whatever it is, you can't deny it. The ability to create, build, and appreciate the whole process is exclusive to humans. It's what sets us apart from other species. Join us, build your projects or train with us.
        </p>
        <div class="text-center">
          <button class="btn black">Have something in mind?</button>
        </div>
      </div>
    </section>
    <section class="section section--dark q-py-lg">
      <h3 class="text-center">OUR TEAM</h3>
    </section>
    <section class="section section--light">
      <div class="team__item">
        <img class="team__item__img" src="~assets/images/team/harvey.jpg">
        <div class="team__item__side">
          <h6 class="name">Joseph Harvey Angeles</h6>
          <p class="handle">@yhev</p>
          <p class="text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquid, perspiciatis voluptate! Totam nam molestias odit vel necessitatibus numquam dolore qui delectus. Odit itaque illum, dicta labore consequatur vitae animi, doloribus voluptates cum odio ab quos ullam excepturi nihil unde. Cum, quaerat doloremque. Minima, cumque consectetur adipisci voluptatibus explicabo iste quis.
          </p>
        </div>
      </div>
      <div class="team__item">
        <img class="team__item__img" src="~assets/images/team/martin.jpg">
        <div class="team__item__side">
          <h6 class="name">Martin de Guzman</h6>
          <p class="handle">@martindeguzman9</p>
          <p class="text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquid, perspiciatis voluptate! Totam nam molestias odit vel necessitatibus numquam dolore qui delectus. Odit itaque illum, dicta labore consequatur vitae animi, doloribus voluptates cum odio ab quos ullam excepturi nihil unde. Cum, quaerat doloremque. Minima, cumque consectetur adipisci voluptatibus explicabo iste quis.
          </p>
        </div>
      </div>
      <div class="team__item">
        <img class="team__item__img" src="~assets/images/team/seth.jpg">
        <div class="team__item__side">
          <h6 class="name">Seth Juriste Aguilar</h6>
          <p class="handle">@sethjuriste</p>
          <p class="text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquid, perspiciatis voluptate! Totam nam molestias odit vel necessitatibus numquam dolore qui delectus. Odit itaque illum, dicta labore consequatur vitae animi, doloribus voluptates cum odio ab quos ullam excepturi nihil unde. Cum, quaerat doloremque. Minima, cumque consectetur adipisci voluptatibus explicabo iste quis.
          </p>
        </div>
      </div>
      <div class="team__item">
        <img class="team__item__img" src="~assets/images/team/tabor.jpg">
        <div class="team__item__side">
          <h6 class="name">Reuben Tabor</h6>
          <p class="handle">@artnew0rkz</p>
          <p class="text">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquid, perspiciatis voluptate! Totam nam molestias odit vel necessitatibus numquam dolore qui delectus. Odit itaque illum, dicta labore consequatur vitae animi, doloribus voluptates cum odio ab quos ullam excepturi nihil unde. Cum, quaerat doloremque. Minima, cumque consectetur adipisci voluptatibus explicabo iste quis.
          </p>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'About'
}
</script>

<style lang="stylus" scoped>
@import '~variables'
.heading {
  padding-bottom 3rem
}
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
    padding 3rem 10vw
    display flex
    align-items flex-start
    &:not(:last-child) {
      border-bottom 1px solid $accent-light
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
      }
      .handle {
        color $secondary
        font-family $font-display
        font-size .7rem
        margin 0
      }
      .text {
        margin-top .2rem
        margin-bottom 0
      }
    }
  }
}
</style>
