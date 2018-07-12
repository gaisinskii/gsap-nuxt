<template>
    <section class="section">
        <nav>
            <div class="nav__logo"></div>
            <div class="nav">
                <ul class="nav-list">
                    <li class="nav-list__item"><a href="#">Home</a></li>
                    <li class="nav-list__item"><a href="#">About</a></li>
                    <li class="nav-list__item"><a href="#">Team</a></li>
                    <li class="nav-list__item"><a href="#">Blog</a></li>
                    <li class="nav-list__item"><a href="#">Contact Us</a></li>
                </ul>
            </div>
        </nav>
    </section>
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
.section {
    display: flex;
    height: 100vh;
    flex-direction: column;
    &__content {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        width: 100%;
    }
}
.rect {
    background-color:blue;
    width: 10vw;
    height: 100px;
    position: absolute;
    z-index: -1;
}
</style>
