<template>
  <div id="app">
    <default-header :scroll-position="scrollPosition" />
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
export default class Default extends Vue {
  public scrollPosition: number = 0

  mounted() {
    this.$nextTick(() => {
      window.addEventListener('scroll', () => {
        this.scrollPosition = window.scrollY
      })
    })
  }
}
</script>

<style lang="scss" scoped>
//
</style>
