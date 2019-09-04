<template>
    <transition name="fade">
      <slot></slot>
    </transition>
</template>

<script>
export default {
  name: 'FadeAnimation'
}
</script>

<style lang="stylus" scoped>
  .fade-enter, .fade-leave-to
    opacity 0
  .fade-leave-active, .fade-enter-active
    transition opacity .3s
</style>
