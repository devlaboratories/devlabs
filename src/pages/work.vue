<template>
  <div>
    <section class="section section--dark">
      <div class="section__content heading">
        <h2 class="text-center">Projects</h2>
      </div>
    </section>
    <section class="section section--light">
      <div class="projects">
        <project />
        <project />
        <project />
      </div>
      <div class="playground q-py-xl">
        <p class="title">Playground</p>
        <ul>
          <li>
            <div class="icon"></div>
            <div class="project-details">
              <p class="project-name">Chronocross</p>
              <p class="project-description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores ratione accusantium saepe sint officiis laborum distinctio ducimus sunt sit! Facilis.</p>
            </div>
          </li>
          <li>
            <div class="icon"></div>
            <div class="project-details">
              <p class="project-name">Chronocross</p>
              <p class="project-description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores ratione accusantium saepe sint officiis laborum distinctio ducimus sunt sit! Facilis.</p>
            </div>
          </li>
          <li>
            <div class="icon"></div>
            <div class="project-details">
              <p class="project-name">Chronocross</p>
              <p class="project-description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores ratione accusantium saepe sint officiis laborum distinctio ducimus sunt sit! Facilis.</p>
            </div>
          </li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
import Project from 'components/project'
export default {
  name: 'Work',
  components: { Project }
}
</script>

<style lang="stylus" scoped>
@import '~variables'
.projects {
  padding-top 2.5rem
  width 90vw
  margin 0 auto
  display grid
  grid-template-columns repeat(auto-fit, minmax(18rem, 1fr))
  grid-gap 1rem
}
.playground {
  width 60%
  margin 0 auto
  .title {
    font-weight 700
    font-size 1.3rem
    color $accent-darkest
  }
  ul {
    list-style none
    padding-inline-start 0
    margin-top 2rem
    li {
      &:not(:last-child) {
        margin-bottom 1.5rem
      }
      display flex
      align-items center
      .icon {
        background-color $accent-darkest
        min-width 40px
        min-height 40px
        margin-right 1rem
        border-radius 50%
        vertical-align middle
      }

      .project-name {
        font-weight 700
        font-size .95rem
        margin 0
      }

      .project-description {
        margin 0
        margin-top .35rem
      }

    }
  }
}
</style>
