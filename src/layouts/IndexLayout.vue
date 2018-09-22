<template>
  <q-layout view="lHh Lpr lFf">
    <navigation @contactClick="showContact = true" />
    <q-page-container>
      <q-page>
        <router-view />
      </q-page>
    </q-page-container>
    <footnote></footnote>
    <q-modal v-model="showContact">
      <contact @submitted="showNotify()" @error="showError()"/>
    </q-modal>
  </q-layout>
</template>

<script>
import Navigation from 'components/navigation'
import Footnote from 'components/footnote'
import Contact from 'components/contact'
export default {
  name: 'IndexLayout',
  components: { Navigation, Footnote, Contact },
  created () {
    this.$root.$on('showContact', () => {
      this.showContact = true
    })
  },
  data () {
    return {
      showContact: false
    }
  },
  methods: {
    showNotify () {
      this.showContact = false
      this.$q.notify({
        message: 'Message sent!',
        detail: 'Thanks for messaging us, we\'ll get back to you shortly.',
        timeout: 5000,
        position: 'bottom-left',
        type: 'positive',
        color: 'black',
        textColor: 'white',
        icon: 'far fa-thumbs-up'
      })
    },
    showError () {
      this.showContact = false
      this.$q.notify({
        message: 'Something went wrong',
        detail: 'Try again sometime later. You could also us chat us in Facebook.',
        timeout: 5000,
        position: 'bottom-left',
        type: 'negative'
      })
    }
  }
}
</script>
