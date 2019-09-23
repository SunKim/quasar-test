<template>
  <div id="q-app">
    <transition name="page" mode="out-in">
      <router-view />
    </transition>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style scoped>
/* transition 관련 */
.page-enter-active,
.page-leave-active {
  transition: opacity 0.2s, transform 0.2s;
}
.page-enter,
.page-leave-to {
  opacity: 0;
  transform: translateX(-50%);
}
</style>
