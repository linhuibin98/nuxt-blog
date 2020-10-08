<template>
  <div class="article-head">
    <h4 class="article-title center">免费试用的豆沙色</h4>
    <div class="article-info center">
      <div class="article-info__item article-info__time center">
        <i class="iconfont icon-06"></i>
        <span>2020-10-08 12:00</span>
      </div>
      <div class="article-info__splitline">|</div>
      <div class="article-info__item article-info__read">
        <i class="iconfont icon-ico_yueduliang"></i>
        <span>999</span>
      </div>
      <div class="article-info__splitline">|</div>
      <div class="article-info__item article-info__comment">
        <i class="iconfont icon-pinglun"></i>
        <span>9</span>
      </div>
      <div class="article-info__splitline">|</div>
      <div class="article-info__item article-info__cate">
        <i class="iconfont icon-leimupinleifenleileibie2"></i>
        <span>猜猜猜</span>
      </div>
    </div>
    <div class="article-info center">
      <div class="article-info__item article-info_word">
        <i class="iconfont icon-icon_xinyong_xianxing_jijin-"></i>
        <span>1323</span>
      </div>
      <div class="article-info__splitline">|</div>
      <div class="article-info__item article-info_readtime">
        <i class="iconfont icon-shalou"></i>
        <span>2min</span>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component({})
export default class ArticleHead extends Vue {}
</script>

<style lang="scss" scoped>
.article {
  &-title {
    font-size: 26px;
    color: #063d37;
    margin-bottom: 10px;
  }

  &-info {
    &__item {
      span {
        font-size: 14px;
        padding-left: 3px;
      }
    }

    &__splitline {
      padding: 0 5px;
      padding-bottom: 3px;
      color: #999;
      display: flex;
      align-items: flex-start;
    }
  }
}
</style>
