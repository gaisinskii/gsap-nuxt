<template>
    <nav class="nav">
        <div class="nav__logo">
            <nuxt-link to="/">
                <img src="~/assets/images/logo_text.black.png" alt="">
            </nuxt-link>
        </div>
        <div>
            <ul class="nav-list">
                <li class="nav-list__item">
                    <nuxt-link to="/">
                        Home
                    </nuxt-link>
                </li>
                <li class="nav-list__item"><a href="#">About</a></li>
                <li class="nav-list__item"><a href="#">Team</a></li>
                <li class="nav-list__item"><a href="#">Blog</a></li>
                <li class="nav-list__item"><a href="#">Contact Us</a></li>
            </ul>
        </div>
    </nav>
</template>

<script>
export default {};
</script>

<style lang="scss">
.nav {
  display: flex;
  align-items: center;
  justify-content: space-around;
  margin-top: 20px;
  visibility: hidden;
  .nav-list {
    display: flex;
    height: 100%;
    list-style: none;
    margin: 0;
    &__item {
      margin: 0 15px;
      a {
        color: #666;
      }
    }
  }
  &__logo {
  }
}
</style>
