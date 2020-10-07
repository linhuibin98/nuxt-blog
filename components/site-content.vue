<template>
  <div class="site-main main flex">
    <!-- 站点概览 -->
    <div
      ref="sitePreview"
      class="site-preview"
      :class="{ 'scroll-fixed': scrollPosition >= 262 }"
    >
      <!-- 个人信息：头像，名字 -->
      <div class="personal-info__wrapper ccenter">
        <div class="personal-avatar">
          <img src="/images/avatar.png" alt="avatar" />
        </div>
        <h3 class="personal-name">LinHuiBin</h3>
        <div class="personal-num center">
          <div class="personal-num__wrapper between">
            <div class="personal-num__item ccenter">
              <span>21</span>
              <span>文章</span>
            </div>
            <div class="personal-num__line flex"></div>
            <div class="personal-num__item ccenter">
              <span>21</span>
              <span>标签</span>
            </div>
          </div>
        </div>
      </div>
      <!-- 分类 -->
      <h4 class="cate-subtitle acenter">
        <i class="iconfont icon-leimupinleifenleileibie2"></i>
        <span class="pl8">分类</span>
      </h4>
      <ul class="cate-lists ccenter">
        <li class="cate-lists__item between">
          <span class="cate-lists__item--name">Node</span>
          <span class="cate-lists__item--num center">99</span>
        </li>
        <li class="cate-lists__item between">
          <span class="cate-lists__item--name">Node</span>
          <span class="cate-lists__item--num center">99</span>
        </li>
        <li class="cate-lists__item between">
          <span class="cate-lists__item--name">Node</span>
          <span class="cate-lists__item--num center">99</span>
        </li>
      </ul>
      <!-- 标签 -->
      <h4 class="cate-subtitle acenter">
        <i class="iconfont icon-leimupinleifenleileibie2"></i>
        <span class="pl8">标签</span>
      </h4>
      <ul class="tag-lists">
        <li class="tag-lists__item">sdfsdf</li>
        <li class="tag-lists__item">sfd</li>
        <li class="tag-lists__item">gfg</li>
        <li class="tag-lists__item">sdsdfsf</li>
        <li class="tag-lists__item">sfsdfd</li>
        <li class="tag-lists__item">gsfgsdf</li>
        <li class="tag-lists__item">ssdfsddf</li>
        <li class="tag-lists__item">sfd</li>
        <li class="tag-lists__item">gfg</li>
        <li class="tag-lists__item">sfsdfdf</li>
        <li class="tag-lists__item">sfd</li>
        <li class="tag-lists__item">gfg</li>
      </ul>
    </div>
    <div
      v-if="scrollPosition >= 262"
      class="site-preview2"
      :style="{ height: sitePreviewHeight + 'px' }"
    ></div>
    <!-- 站点内容 -->
    <div class="site-content flex1">
      <slot></slot>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'

@Component({})
export default class SiteContent extends Vue {
  @Prop({
    type: Number,
    default: 0,
  })
  scrollPosition!: number

  public sitePreviewHeight: number = 0

  mounted() {
    this.$nextTick(() => {
      this.sitePreviewHeight = (this.$refs
        .sitePreview as any).getBoundingClientRect().height
    })
  }
}
</script>

<style lang="scss" scoped>
.site-main {
  padding-top: 20px;
  padding-bottom: 20px;

  .site-preview2 {
    width: 280px;
  }

  .site-preview {
    width: 280px;
    padding: 10px;
    background-color: $content-bg;
    border-radius: $border-radius-main;
    height: min-content;

    &.scroll-fixed {
      position: fixed;
      top: 80px;
      left: 35px;
    }

    .personal-info__wrapper {
      .personal {
        &-avatar {
          padding: 10px;
          img {
            width: 98px;
            height: 98px;
            border-radius: 50%;
          }
        }

        &-name {
          font-size: 20px;
          font-weight: 500;
          color: $main-text-color;
        }

        &-num {
          padding: 10px 0;
          width: 100%;
          border-bottom: 1px solid #eee;

          &__wrapper {
            width: 120px;
          }

          &__line {
            width: 1px;
            height: 57.6px;
            background-color: #eee;
          }

          &__item {
            span {
              font-size: 12px;
            }
            span:first-child {
              font-size: 20px;
              font-weight: 600;
              color: $main-text-color;
            }
          }
        }
      }
    }

    .cate {
      &-subtitle {
        padding: 20px 0;
        font-size: 16px;
        font-weight: 500;
      }

      &-lists {
        width: 100%;
        &__item {
          padding: 5px 10px;
          width: 100%;
          background-color: #fff;
          border-radius: $border-radius-main;
          box-shadow: 1px 1px 10px 2px #eee;
          margin-bottom: 10px;
          transition: all 0.5s;
          cursor: pointer;

          &:last-child {
            margin-bottom: 0;
          }

          &:hover {
            transform: scale(1.03);
          }

          &--name {
            font-size: 16px;
            color: #333;
            font-weight: 600;
          }

          &--num {
            width: 22px;
            height: 22px;
            border-radius: 5px;
            background-color: #f8b26a;
            font-size: 12px;
            color: #fff;
          }
        }
      }
    }

    .tag {
      &-lists {
        display: flex;
        flex-wrap: wrap;

        &__item {
          margin-bottom: 8px;
          padding: 0 8px;
          background-color: skyblue;
          margin-right: 8px;
          border-radius: 5px;
          color: #fff;
          transition: all 0.5s;
          cursor: pointer;
          box-shadow: 0 0 10px 1px #eee;

          &:hover {
            transform: scale(1.08);
            color: rgba(255, 255, 255, 0.65);
          }
        }
      }
    }
  }

  .site-content {
    padding: 10px;
  }
}
</style>
