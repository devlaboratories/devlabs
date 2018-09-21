<template>
  <div>
    <masthead
      :companyName="companyName"
      :heading="masthead.headline"
      :intro="masthead.introduction"
      @click="openURL('https://m.me/devlaboratories')"
    />
    <features :features="features" />
    <clients :clients="clients" />
    <services :services="services" />
  </div>
</template>
<script>
import {openURL} from 'quasar'

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
    this.clients = DATA.clients
    this.services = DATA.services
  },
  methods: {
    openURL,
    getStarted () {
      alert("Let's get started!")
    }
  }
}
</script>
