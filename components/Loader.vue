<template>
  <div class="loader__img">
    <a href="">
      <img src="~/assets/images/logo_text.black.png" alt="">
    </a>
  </div>
</template>

<script>
export default {
};
</script>

<style>
  .loader__img {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 3;
    visibility: hidden;
  }
</style>
