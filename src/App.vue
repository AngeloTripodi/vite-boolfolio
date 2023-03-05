<script>
export default {
  name: 'App',
  components: {
    AppHeader,
  }
}
import AppHeader from './components/AppHeader.vue';

</script>

<template>
  <header>
    <AppHeader />
  </header>
  <main class="container">
    <router-view></router-view>
  </main>
</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use 'bootstrap/scss/bootstrap.scss' as *;
</style>
