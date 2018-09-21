<template>
  <div>
    <section class="section section--dark">
      <div class="section__content heading">
        <h2 class="text-center">Projects</h2>
      </div>
    </section>
    <section class="section section--light">
      <div class="projects">
        <project
          v-for="project in clientProjects"
          :key="project.id"
          :project="project"
        />
      </div>
      <div class="playground q-py-xl">
        <p class="title">Playground</p>
        <ul>
          <li v-for="project in playground" :key="project.id">
            <img v-if="project.image" class="icon" :src="`statics/images/projects/playground/${project.image}`">
            <div class="project-details">
              <p class="project-name" @click="openURL(project.link)">{{project.name || 'Project'}}</p>
              <p class="project-description">{{project.description || 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores ratione accusantium saepe sint officiis laborum distinctio ducimus sunt sit! Facilis.'}}</p>
            </div>
          </li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
import CLIENT_PROJECTS from 'statics/data/projects/clients.json'
import PLAY_PROJECTS from 'statics/data/projects/playground.json'
import Project from 'components/project'
import {openURL} from 'quasar'
export default {
  name: 'Work',
  components: { Project },
  created () {
    this.clientProjects = CLIENT_PROJECTS
    this.playground = PLAY_PROJECTS
  },
  methods: {
    openURL
  }
}
</script>

<style lang="stylus" scoped>
@import '~variables'
.projects {
  padding 3.5rem 0
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
        margin-right 1rem
        align-self center
        width 40px
        max-width 100%
        border-radius 50%
      }

      .project-name {
        font-weight 700
        font-size .95rem
        margin 0
        display inline-block
        transition all .3s ease
        &:hover {
          text-decoration underline
          cursor pointer
          color $secondary
        }
      }

      .project-description {
        margin 0
        margin-top .35rem
      }

    }
  }
}
</style>
