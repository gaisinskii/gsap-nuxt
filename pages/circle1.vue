<template>
    <comp1> </comp1>
</template>

<script>
import comp1 from '../components/sub-components/comp1.vue';

export default {
  components: {
    comp1,
  },
  transition: {
    mode: 'out-in',
    css: false,
    beforeEnter(el) {
      TweenMax.set(el, {
        transformPerspective: 600,
        perspective: 300,
        transformStyle: 'preserve-3d',
      });
    },
    enter(el, done) {
      TweenMax.to(el, 1, {
        rotationY: 360,
        transformOrigin: '50% 50%',
        ease: Back.easeOut,
      });
      done();
    },
    leave(el, done) {
      TweenMax.to(el, 1, {
        rotationX: 0,
        transformOrigin: '50% 50%',
        ease: Back.easeIn,
      });
      done();
    },
  },
};
</script>

<style lang="scss">
.nav {
  .nav-list {
    opacity: 1;
  }
  &__logo {
      opacity: 1;
  }
}
</style>
