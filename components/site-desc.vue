<template>
  <!-- 站点描述 -->
  <div class="site-desc ccenter">
    <div class="site-desc__title">沐风</div>
    <div class="site-desc__content">
      听，一颗星星落地作响！你别赤脚在这草地上散步， 我的花园到处是星星的碎片。
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component({})
export default class SiteDesc extends Vue {}
</script>

<style lang="scss" scoped>
.site-desc {
  margin-top: 64px;
  width: 100%;
  height: 260px;
  padding: 20px;
  background-image: url('/images/blog_bg.jpg');
  background-size: 100% 100%;
  background-repeat: no-repeat;

  &__title {
    padding-bottom: 8px;
    font-size: 28px;
    color: #fff;
    font-weight: 500;
  }

  &__content {
    font-size: 16px;
    color: #fff;
  }
}
</style>
