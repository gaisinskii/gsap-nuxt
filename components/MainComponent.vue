<template>
    <section class="section">
        <navigation></navigation>
        <div class="section__content">
            <div class="nav__logo_fixed">
                <a href="">
                    <img src="~/assets/images/logo_text.black.png" alt="">
                </a>
            </div>
            <div class="section__content-cube">
                <div class="cube cube1">
                    <nuxt-link to="/circle1">
                    </nuxt-link>
                </div>
                <div class="cube cube2">
                    <nuxt-link to="/circle2">
                    </nuxt-link>
                </div>
                <div class="cube cube3">Component #4</div>
                <div class="cube cube4">Component #3</div>
            </div>
        </div>
    </section>
</template>

<script>
import { TimelineMax } from 'gsap';
import Navigation from './Navigation.vue';

export default {
  components: {
    Navigation,
  },
  methods: {
    animate() {
      const timeLine = new TimelineMax();
      timeLine.from('.nav__logo_fixed', 2, { alpha: 0, ease: Sine.easeIn });
      timeLine.to('.nav__logo_fixed', 2, { alpha: 1, ease: Sine.easeInm });
      timeLine.to('.nav__logo_fixed', 1, { alpha: 0, ease: Sine.easeIn, delay: 1 });
      timeLine.from('.section__content-cube', 1, { alpha: 0, ease: Sine.easeIn });
      timeLine.to('.section__content-cube', 1, { alpha: 1, ease: Sine.easeIn });
      timeLine.from('.nav-list', 0.5, {
        alpha: 0,
        ease: Sine.easeIn,
      });
      timeLine.to('.nav-list', 0.5, {
        alpha: 1,
        ease: Sine.easeIn,
      });
      timeLine.staggerFromTo('.nav-list__item', 0.5, { x: 50, alpha: 0 }, { x: 0, alpha: 1 }, 0.2);
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
    &-cube {
        display: flex;
        position:relative;
        height: 600px;
        width: 600px;
        background: azure;
        flex-wrap: wrap;
        border-radius: 50%;
        box-shadow:0 1px 4px rgba(0, 0, 0, 0.3), 0 0 40px rgba(0, 0, 0, 0.1) inset;
        overflow: hidden;
        .cube {
            display: flex;
            position: relative;
            width: 50%;
            height: 50%;
            justify-content: center;
            align-items: center;
            a {
                width: 100%;
                height: 100%;
                z-index: 1;
            }
            &:hover {
                background: pink;
            }
        }
        .cube1 {
            position: relative;
            &::after {
                position: absolute;
                content: 'Component #1';
                color: #666;
            }
        }
        .cube2 {
            position: relative;
            &::after {
                position: absolute;
                content: 'Component #2';
                color: #666;
            }
        }
    }
  }
}
</style>
