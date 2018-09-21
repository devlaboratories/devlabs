<template>
  <q-layout view="lHh Lpr lFf">
    <navigation />
    <q-page-container>
      <q-page>
        <router-view />
      </q-page>
    </q-page-container>
    <footnote></footnote>
  </q-layout>
</template>

<script>
import Navigation from 'components/navigation'
import Footnote from 'components/footnote'
export default {
  name: 'IndexLayout',
  components: { Navigation, Footnote },
  data () {
    return {
      showing: true
    }
  }
}
</script>
