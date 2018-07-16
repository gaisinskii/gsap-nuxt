<template>
    <comp1> </comp1>
</template>

<script>
import comp1 from '../components/sub-components/comp1.vue';

export default {
  components: {
    comp1,
  },
};
</script>

<style lang="scss">
.nav {
  .nav-list {
    opacity: 1;
  }
  &__logo {
      opacity: 1;
  }
}
</style>
