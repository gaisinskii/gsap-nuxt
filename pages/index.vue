<template>
  <main-component></main-component>
</template>

<script>
import MainComponent from '../components/MainComponent.vue';

export default {
  components: {
    MainComponent,
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
      TweenMax.set(el, {
        visibility: 'visible',
      });
    },
    enter(el, done) {
      TweenMax.from(el, 1, {
        alpha: 0,
        delay: 1,
      });
      TweenMax.to(el, 1, {
        alpha: 1,
        delay: 1,
        rotationX: 360,
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

<style>
</style>
