<template>
  <div id="app">
    <AppLayout>
      <router-view />
    </AppLayout>
  </div>
</template>

<script>
import { setAuth } from '@/common/helpers';

export default {
  name: 'App',
  created() {
    if (this.$jwt.getToken()) {
      setAuth(this.$store);
    }
    this.$store.dispatch('init');
  }
};
</script>

<style lang="scss">
@import "~@/assets/scss/app";
</style>
