<template>
  <div id="app">
    <default-header />
    <site-desc />
    <site-content>
      <Nuxt />
    </site-content>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import DefaultHeader from '~/components/default-header.vue'
import SiteDesc from '~/components/site-desc.vue'
import SiteContent from '~/components/site-content.vue'

@Component({
  components: {
    DefaultHeader,
    SiteDesc,
    SiteContent,
  },
})
export default class Name extends Vue {}
</script>

<style lang="scss" scoped>
//
</style>
