<template>
  <article-lists />
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import ArticleLists from '~/components/article-lists.vue'

@Component({
  components: {
    ArticleLists,
  },
})
export default class Index extends Vue {}
</script>

<style lang="scss" scoped>
//
</style>
