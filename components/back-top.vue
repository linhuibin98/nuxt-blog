<template>
  <transition>
    <div
      v-show="show"
      class="back-top center"
      role="button"
      @click="handleBackTop()"
    >
      <i class="iconfont icon-shangsanjiaoxing"></i>
    </div>
  </transition>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'

@Component({})
export default class BackTop extends Vue {
  // props
  @Prop({
    type: Number,
    default: 0,
  })
  scrollPosition!: number

  // computed
  get show(): boolean {
    return this.scrollPosition > 150
  }

  // methods
  handleBackTop(time: number = 100, speed: number = 100) {
    const currentTop =
      document.documentElement.scrollTop || document.body.scrollTop
    const step = time / speed
    const stepDistance = currentTop / step
    const timer = setInterval(() => {
      const osTop =
        document.documentElement.scrollTop || document.body.scrollTop
      const computedTop = osTop - stepDistance < 0 ? 0 : osTop - stepDistance
      document.documentElement.scrollTop = document.body.scrollTop = computedTop
      if (computedTop === 0 || !computedTop) {
        clearInterval(timer)
      }
    }, speed)
  }
}
</script>

<style lang="scss" scoped>
.back-top {
  position: fixed;
  right: 6.5px;
  bottom: 60px;
  width: 42px;
  height: 42px;
  border-radius: 5px;
  background-color: #fff;

  &:hover {
    background-color: #eee;
    color: #063d37;
  }
}

.v-enter,
.v-leave-to {
  opacity: 0;
  transform: scale(0);
}

.v-enter-active,
.v-leave-active {
  transition: all 0.5s;
}

.v-leave,
.v-enter-to {
  opacity: 1;
  transform: scale(1);
}
</style>
