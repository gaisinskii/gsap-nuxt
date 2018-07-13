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
        <div class="circles">
            <div class="circle__one"></div>
            <div class="circle__two"></div>
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
      timeLine.from('.nav__logo', 2, {
        alpha: 0,
        ease: Sine.easeIn,
      });
      timeLine.to('.nav__logo', 2, {
        alpha: 1,
        ease: Sine.easeIn,
      });
      timeLine.to('.nav__logo', 2, {
        x: -460,
        y: -460,
        delay: 1,
        alpha: 1,
        ease: Sine.easeIn,
      });
      timeLine.from('.nav-list', 1, {
        alpha: 0,
        ease: Sine.easeIn,
      });
      timeLine.to('.nav-list', 1, {
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
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    opacity: 0;
  }
}

.circles {
  .circle__one {
    position: absolute;
    top: 50%;
    left: 55%;
    transform: translate(-50%, -50%);
    width: 100px;
    height: 200px;
    border-bottom-right-radius: 100px;
    border-top-right-radius: 100px;
    border: 5px solid gray;
    border-left: 0;
  }
  .circle__two {
    position: absolute;
    top: 50%;
    left: 45%;
    transform: translate(-50%, -50%);
    width: 90px;
    height: 180px;
    border-bottom-left-radius: 90px;
    border-top-left-radius: 90px;
    border: 5px solid red;
    border-right: 0;
  }
}
</style>
