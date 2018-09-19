<template functional>
  <section class="section section--dark">
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
.features {
  display grid
  grid-template-columns repeat(auto-fit, minmax(20rem, 1fr))
  grid-column-gap 3rem
  .feature {
    display flex
    justify-content space-between
    align-items flex-start

    .q-icon {
      margin-top 1rem
      margin-right 1rem
    }
  }
}

/deep/ a {
  text-decoration: none
}
</style>
