<template>
  <section class="section section--light">
    <div class="section__content">
      <div class="services">

        <div class="service">
          <div class="content">
            <h6>Software Development</h6>
            <p>
              <span class="text-secondary">Delivering your needs and exceeding your expections</span> is our success. The lab is fully-equipped with technologies and creativity that will surely provide you the best yet cost-efficient Desktop, Web or Mobile applications.
            </p>
          </div>
          <div class="icon"><q-icon name="fas fa-keyboard" size="1.5rem" /></div>
        </div>
        <div class="service">
          <div class="content">
            <h6>Database Design and Optimization</h6>
            <p>
              Service availability relies on data availability so as data availability relies on the backend architecture of an application. So we provide an engineered DB design that is normalized and optimized.
            </p>
          </div>
          <div class="icon"><q-icon name="fas fa-database" size="1.5rem" /></div>
        </div>
        <div class="service">
          <div class="content">
            <h6>Computer Networking</h6>
            <p>
              The laboratory is here to deliver a network design that best suits your workplace. Security, Reliability, and Availabilty are on top of our priority in providing you a converged network.
            </p>
          </div>
          <div class="icon"><q-icon name="fas fa-server" size="1.5rem" /></div>
        </div>
        <div class="service">
          <div class="content">
            <h6>UI/UX Design</h6>
            <p>
              <span class="text-secondary">Form complimenting function.</span> We design interface that highlights your niche and includes strategic content architecture. It is also our duty to comply with the industry standards while modernizing your interface and experience.
            </p>
          </div>
          <div class="icon"><q-icon name="fas fa-magic" size="1.5rem" /></div>
        </div>
        <div class="service">
          <div class="content">
            <h6>Trainings &amp; Tutorials</h6>
            <p>
              <span class="text-secondary">Learning is our passion</span> and we love to share it with you. This will equip you with the essential knowledge in facing the high IT demand of the industry.
            </p>
          </div>
          <div class="icon"><q-icon name="fas fa-university" size="1.5rem" /></div>
        </div>
        <div class="service">
          <div class="content">
            <h6>Consulting</h6>
            <p>
              Have any problems or uncertainties? The lab is here to help you. It was built to provide you the optimum solution to your impediments.
            </p>
          </div>
          <div class="icon"><q-icon name="fas fa-user-secret" size="1.5rem" /></div>
        </div>

      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Services'
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
  .service {
    display flex
    align-items center
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

    .icon {
      padding 1rem
      background-color $accent-dark
      border-radius 50%
      color $accent-lightest
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
