<template>
  <section class="section section--dark">
    <div class="section__content">
      <div class="feature">
        <q-icon name="fas fa-flask" size="2.5rem" />
        <div class="content">
          <h3>Technical Excellence</h3>
          <p>At our lab, we pride ourselves with excellence mindset. We strive to know the in's-and-out's of whatever technology we're using, resulting to quality output. We adhere to the <span class="link" @click="openURL('http://manifesto.softwarecraftsmanship.org/')">Software craftsmanship manifesto</span> as our credo.</p>
        </div>
      </div>
      <div class="feature">
        <q-icon name="far fa-lightbulb" size="2.5rem" />
        <div class="content">
          <h3>Innovative Ideas</h3>
          <p>
            Innovation is in our blood. When we're not working, we're innovating, fiddling with new software and hardware technologies, building stuff. This innovation habit will reflect back into our work and services that we provide you.
          </p>
        </div>
      </div>
      <div class="feature">
        <q-icon name="fas fa-user-astronaut" size="2.5rem" />
        <div class="content">
          <h3>User-oriented</h3>
          <p>
            Ultimately, your product ends up on your users - their experience on the product will be their impression on you and your business. Our work finds the right balance between what your user needs, and what we and you think they need.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { openURL } from 'quasar'
export default {
  name: 'Features',
  methods: {
    openURL
  }
}
</script>

<style lang="stylus" scoped>
@import '~variables'
.section__content {
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
</style>
