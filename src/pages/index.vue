<template>
  <div>
    <masthead
      :companyName="companyName"
      :heading="masthead.headline"
      :intro="masthead.introduction"
      @click="getStarted"
    />
    <clients />
    <features :features="features" />
    <services :services="services" />
  </div>
</template>
<script>
import DATA from 'statics/data/landing.json'
import {name} from '../../package.json'

import Masthead from 'components/masthead'
import Clients from 'components/clients'
import Features from 'components/features'
import Services from 'components/services'
export default {
  name: 'PageIndex',
  components: { Masthead, Clients, Features, Services },
  created () {
    this.companyName = name
    this.masthead = DATA.masthead
    this.features = DATA.features
    this.services = DATA.services
  },
  methods: {
    getStarted () {
      alert("Let's get started!")
    }
  }
}
</script>
