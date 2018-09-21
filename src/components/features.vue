<template functional>
  <section class="section section--light">
    <div class="section__content features">
      <div class="feature" v-for="feature in props.features" :key="feature.id">
        <q-icon :name="feature.icon" size="2.5rem" />
        <div class="content">
          <h3>{{feature.title}}</h3>
          <p v-html="feature.description"/>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Features',
  props: ['features']
}
</script>

<style lang="stylus" scoped>
@import '~variables'
section {
  border-top none
}
.features {
  display grid
  grid-template-columns repeat(auto-fit, minmax(20rem, 1fr))
  grid-column-gap 3rem
  +respond-max($breakpoint-sm) {
    grid-template-columns 1fr
  }
  .feature {
    display flex
    justify-content space-between
    align-items baseline

    .q-icon {
      margin-top 1rem
      margin-right 1rem
      align-self flex-start
    }
  }
}

/deep/ a {
  text-decoration: none
}
</style>
