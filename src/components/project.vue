<template>
  <q-card inline>
    <q-card-media>
      <img src="statics/logo.png" >
    </q-card-media>
    <q-card-separator />
    <q-card-main>
      <p class="title">Project Title</p>
      <p class="text">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Possimus quia totam corrupti, assumenda dolorum accusamus quisquam repellat aliquid voluptates, dolores provident ad. Exercitationem dolorum quod delectus nulla id est labore.</p>
    </q-card-main>
  </q-card>
</template>

<script>
export default {
  name: 'Project'
}
</script>

<style lang="stylus" scoped>
@import '~variables'
.q-card {
  box-shadow none
  border 1px solid $accent-light
  transition all .3s ease
  &:hover {
    border 1px solid $accent-neutral
  }
  .title {
    margin 0
    padding-bottom .4rem
    font-weight 700
    font-size 1.1rem
    font-family $font-display
    color $accent-darkest
  }
}
img {
  width 150px
  margin 0 auto
}
.q-card-media {
  min-height 100px
}
</style>
