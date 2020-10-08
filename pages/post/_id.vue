<template>
  <div>Post {{ $route.params.id }}</div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component({})
export default class Post extends Vue {}
</script>

<style lang="scss" scoped>
//
</style>
