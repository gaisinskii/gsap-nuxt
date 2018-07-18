<template>
  <div>
    <loader class="loader"> </loader>
    <navigation class="navigation"> </navigation>
    <nuxt class="content"> </nuxt>
  </div>
</template>

<script>
import { TimelineMax } from 'gsap';
import Navigation from '../components/Navigation.vue';
import Loader from '../components/Loader.vue';

export default {
  components: {
    Navigation,
    Loader,
  },
  methods: {
    animate() {
      const timeLine = new TimelineMax();
      timeLine.set('.loader', { visibility: 'visible', delay: 1 });
      timeLine.from('.loader', 1, { alpha: 0, ease: Sine.easeInm });
      timeLine.to('.loader', 1, { alpha: 1, ease: Sine.easeIn });
      timeLine.to('.loader', 1.5, { alpha: 0, ease: Sine.easeIn });
      timeLine.set('.content', { visibility: 'visible', delay: 1 });
      timeLine.from('.content', 1, { alpha: 0, ease: Sine.easeInm });
      timeLine.to('.content', 1, { alpha: 1, ease: Sine.easeIn });
      timeLine.set('.navigation', { visibility: 'visible' });
      timeLine.from('.nav-list', 0.5, {
        alpha: 0,
        ease: Sine.easeIn,
      });
      timeLine.to('.nav-list', 0.5, {
        alpha: 1,
        ease: Sine.easeIn,
      });
      timeLine.staggerFromTo('.nav-list__item', 0.5, { x: 50, alpha: 0 }, { x: 0, alpha: 1 }, 0.2);
      timeLine.from('.nav__logo', 2, {
        alpha: 0,
        ease: Sine.easeIn,
      });
      timeLine.to('.nav__logo', 2, {
        alpha: 1,
        ease: Sine.easeIn,
      });
    },
  },
  beforeMount() {
    this.animate();
  },
};
</script>


<style>
</style>
