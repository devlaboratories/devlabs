<template functional>
  <section class="section section--dark">
    <div class="feedback" v-for="client in props.clients" :key="client.id">
      <p class="statement">{{client.statement}}</p>
      <p class="author">&mdash; {{client.author}}</p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ComponentName',
  props: ['clients']
}
</script>

<style lang="stylus" scoped>
@import '~variables'
.section {
  padding-top 5rem
  display flex
  flex-wrap wrap
  justify-content space-evenly
  align-items baseline
  align-content space-between
  .feedback {
    flex-basis 25%
    min-width 15rem
    padding 1.5rem
    padding-bottom 0
    margin-bottom 5rem
    position relative
    &::before {
      content "\201C"
      position absolute
      top -3rem
      left -2rem
      font-size 15rem
      font-family sans-serif
      color rgba($accent-neutral, .2)
    }
  }
  .statement {
    text-indent .5rem
    font-style italic
  }
  .author {
    text-align right
    margin-bottom 0
    font-weight bold
  }
}
</style>
