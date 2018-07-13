<template>
    <section class="section">
        <nav class="nav">
            <div class="nav__logo">
                <a href="">
                    <img src="~/assets/images/logo_text.black.png" alt="">
                </a>
            </div>
            <div>
                <ul class="nav-list">
                    <li class="nav-list__item"><a href="#">Home</a></li>
                    <li class="nav-list__item"><a href="#">About</a></li>
                    <li class="nav-list__item"><a href="#">Team</a></li>
                    <li class="nav-list__item"><a href="#">Blog</a></li>
                    <li class="nav-list__item"><a href="#">Contact Us</a></li>
                </ul>
            </div>
        </nav>
        <div class="section__content">
            <div class="nav__logo_fixed">
                <a href="">
                    <img src="~/assets/images/logo_text.black.png" alt="">
                </a>
            </div>
            <div class="section__content-cube">
                <div class="cube cube1">Component #1</div>
                <div class="cube cube2">Component #2</div>
                <div class="cube cube3">Component #3</div>
                <div class="cube cube4">Component #4</div>
            </div>
        </div>
    </section>
</template>

<script>
import { TimelineMax } from 'gsap';

export default {
  name: 'Home',
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
        opacity: 0;
        overflow: hidden;
        .cube {
            display: flex;
            width: 50%;
            height: 50%;
            justify-content: center;
            align-items: center;
            &:hover {
                background: pink;
            }
        }
    }
  }
}

.nav {
  display: flex;
  align-items: center;
  justify-content: space-around;
  margin-top: 20px;
  .nav-list {
    display: flex;
    height: 100%;
    list-style: none;
    margin: 0;
    opacity: 0;
    &__item {
      margin: 0 15px;
      a {
        color: #666;
      }
    }
  }
  &__logo {
    opacity: 0;
    &_fixed {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        z-index: 3;
        opacity: 0;
    }
  }
}
</style>
