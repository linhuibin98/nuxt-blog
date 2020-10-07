<template>
  <!-- 顶部 搜索条 -->
  <div
    class="search acenter"
    :class="{ 'search--open': show }"
    :style="{ width: show ? '243px' : '48px' }"
  >
    <div class="search-prepend center" @click="toggleShow">
      <i class="iconfont icon-sousuo"></i>
    </div>
    <input
      ref="searchIpt"
      class="search-input"
      :class="{ 'search-input--open': show }"
      type="text"
      placeholder="请输入要搜索的内容"
    />
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component({})
export default class SearchBar extends Vue {
  public show: boolean = false

  toggleShow() {
    this.show = !this.show
    // 为true的话，自动获取输入框焦点
    if (this.show) {
      this.$nextTick(() => {
        (this.$refs.searchIpt as any).focus()
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.search {
  border-radius: 10px;
  transition: width 0.5s;
  overflow: hidden;

  &--open {
    background-color: #eee;
  }

  &-prepend {
    padding: 10px 16px;
  }

  &:hover {
    color: rgba(0, 0, 0, 0.45);
  }

  &-input {
    width: 195px;
    height: 100%;
    padding: 10px 10px 10px 0;
    border: none;
    outline: none;
    font-size: 16px;
    color: #333;

    &--open {
      background-color: #eee;
    }
  }
}
</style>
