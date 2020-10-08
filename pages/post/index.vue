<template>
  <div>PostIndex</div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component({})
export default class PostIndex extends Vue {
  validate({ params }: any): boolean {
    if (params.id && parseInt(params.id)) {
      return true
    } else {
      return false
    }
  }
}
</script>

<style lang="scss" scoped>
//
</style>
