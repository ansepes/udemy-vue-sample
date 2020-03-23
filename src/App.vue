<template>
  <div style="width:700px; margin:auto; padding-top: 50px;">
    <router-view name="header"></router-view>
    <transition name="fade" mode="out-in" @before-enter="beforeEnter">
      <router-view></router-view>
    </transition>
  </div>
</template>

<script>
export default {
  methods: {
    beforeEnter() {
      this.$root.$emit('triggerScroll');
    },
  },
};
</script>

<style scoped>
.fade-move {
  transition: transform 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-to,
.fade-leave {
  opacity: 1;
}

.fade-enter-active {
  transition: opacity 0.5s;
}

.fade-leave-active {
  transition: opacity 0.5s;
  position: absolute;
  width: 200px;
}
</style>
