<template>
  <div class="flex1">
    <article-lists-item />
    <article-lists-item />
    <article-lists-item />
    <article-lists-item />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import ArticleListsItem from './article-lists-item.vue'

@Component({
  components: {
    ArticleListsItem,
  },
})
export default class ArticleList extends Vue {}
</script>

<style lang="scss" scoped>
//
</style>
