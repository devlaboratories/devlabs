<template>
  <div>
    <masthead />
    <clients />
    <features />
    <services />
  </div>
</template>

<style>
</style>

<script>
import Masthead from 'components/masthead'
import Clients from 'components/clients'
import Features from 'components/features'
import Services from 'components/services'
export default {
  name: 'PageIndex',
  components: { Masthead, Clients, Features, Services }
}
</script>
