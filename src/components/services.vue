<template functional>
  <section class="section section--light">
    <div class="section__content">
      <div class="services">

        <div class="service" v-for="service in props.services" :key="service.id">
          <div class="content">
            <h6>{{service.title}}</h6>
            <p v-html="service.description" />
          </div>
          <div class="icon"><q-icon :name="service.icon" size="1.5rem" /></div>
        </div>

      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Services',
  props: ['services']
}
</script>

<style lang="stylus" scoped>
@import '~variables'
.services {
  width 100%
  display grid
  grid-template-columns repeat(auto-fit, minmax(25rem, 1fr))
  grid-column-gap 3.5rem
  grid-row-gap 3rem

  +respond-max($breakpoint-xs) {
    grid-template-columns 1fr
  }

  .service {
    display flex
    align-items baseline
    &:nth-child(odd) {
      flex-direction flex-start
      text-align right
      .content {
        margin-right 1rem
      }
    }
    &:nth-child(even) {
      flex-direction row-reverse
      .content {
        margin-left 1rem
      }
    }

    +respond-max($breakpoint-xs) {
      &:nth-child(odd), &:nth-child(even) {
        flex-direction column-reverse
        .content {
          margin 0
          margin-top 2rem
          text-align left
          h6 {
            text-align center
          }
        }
      }
    }

    .icon {
      padding 1rem
      background-color $accent-dark
      border-radius 50%
      color $accent-lightest
      align-self center
    }
  }
}
h6 {
  margin 1rem 0
  margin-top 0
  font-family $font-display
  font-size 1.2rem
  color $accent-darkest
}

</style>
