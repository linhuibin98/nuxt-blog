<template>
  <header class="default-header" :class="{ hover: scrollPosition > 100 }">
    <nav class="between">
      <div class="toggle-btn none"></div>
      <div class="author-info center">
        <img src="/images/avatar.png" alt="avatar" />
        <span class="fw600 pl8">沐风</span>
      </div>
      <div class="nav-lists between flex1">
        <ul class="nav center">
          <li class="nav-item center">归档</li>
          <li class="nav-item center">友人</li>
          <li class="nav-item center">留言板</li>
          <li class="nav-item center">关于</li>
        </ul>
        <search-bar></search-bar>
      </div>
    </nav>
  </header>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'
import SearchBar from './search-bar.vue'

@Component({
  components: {
    SearchBar,
  },
})
export default class DefaultHeder extends Vue {
  @Prop({
    type: Number,
    default: 0,
  })
  scrollPosition!: number
}
</script>

<style lang="scss" scoped>
@mixin headerHover {
  background-color: #fff;
  box-shadow: 1px 1px 10px 1px #eee;
}
.default-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 60px;
  transition: all 0.5s;
  z-index: 2;

  &.hover {
    @include headerHover();
  }

  &:hover {
    @include headerHover();
  }

  nav {
    padding: 0 35px;
    height: 100%;

    .author-info {
      height: 100%;
      cursor: pointer;

      img {
        width: 45px;
        height: 45px;
        border-radius: 45px;
      }
    }

    .nav-lists {
      padding-left: 20px;
      padding-right: 20px;
      height: 100%;

      .nav {
        height: 100%;
        font-size: 16px;
        color: #333;

        &-item {
          padding: 0 16px;
          height: 100%;
          font-weight: 600;
          cursor: pointer;

          &:hover {
            color: rgba(0, 0, 0, 0.45);
          }
        }
      }
    }
  }
}
</style>
