<template>
  <div class="item ccenter">
    <article-head></article-head>
    <div class="article-content">
      前言
      免费申请通配符域名证书的渠道有很多，这里介绍的是来自allinssl的申请教程，可申请两种免费证书，均为3个月有效期，支持多域名及多通配符。
      CRAZYSSL Free
      Certificate（https://allinssl.com/zh/client/digitalcert/create/25）
      UbiquiTLS Free SSL （h…
    </div>
    <!-- 文章标签 -->
    <div class="article-tags flex-wrap">
      <div class="article-tags__item">
        <i class="iconfont icon-bianqian"></i>
        <span>sdasd</span>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import ArticleHead from './article-head.vue'

@Component({
  components: {
    ArticleHead,
  },
})
export default class ArticleListsItem extends Vue {}
</script>

<style lang="scss" scoped>
.item {
  padding: 30px;
  background-color: #fff;
  border-radius: $border-radius-main;
  margin-bottom: 10px;

  &:last-child {
    margin-bottom: 0;
  }

  .article {
    &-content {
      margin-top: 20px;
      line-height: 1.6;
    }

    &-tags {
      margin-top: 20px;
      width: 100%;
    }
  }
}
</style>
