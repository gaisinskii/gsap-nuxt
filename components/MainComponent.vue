<template>
    <div class="container">
        <div class="row">
            <div class="col">
                <h1>Nuxt with Gsap</h1>
                <div class="rect">

                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { TweenMax } from 'gsap';

export default {
  name: 'Home',
  methods: {
    animate() {
      TweenMax.to('.rect', 1, { x: 100, alpha: 0, ease: Sine.easeIn });
      console.log('test');
    },
  },
  beforeMount() {
    this.animate();
  },
};
</script>

<style lang="scss">
.rect {
    background-color:blue;
    width: 10vw;
    height: 100px;
    position: absolute;
    z-index: -1;
}
</style>
