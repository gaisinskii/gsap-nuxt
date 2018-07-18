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
        visibility: 'visible',
      });
    },
    enter(el, done) {
      TweenMax.from(el, 1, {
        alpha: 0,
      });
      TweenMax.to(el, 1, {
        alpha: 1,
      });
      done();
    },
  },
};
</script>

<style>
</style>
