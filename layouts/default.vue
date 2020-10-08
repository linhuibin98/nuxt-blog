<template>
  <div id="app">
    <default-header :scroll-position="scrollPosition" />
    <site-desc />
    <site-subtitle />
    <site-content :scroll-position="scrollPosition">
      <Nuxt />
    </site-content>
    <back-top :scroll-position="scrollPosition" />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import DefaultHeader from '~/components/default-header.vue'
import SiteDesc from '~/components/site-desc.vue'
import SiteContent from '~/components/site-content.vue'
import SiteSubtitle from '~/components/site-subtitle.vue'
import BackTop from '~/components/back-top.vue'

@Component({
  components: {
    DefaultHeader,
    SiteDesc,
    SiteContent,
    SiteSubtitle,
    BackTop,
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
