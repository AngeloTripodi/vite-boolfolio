<script>
export default {
  name: 'App',
  components: {
    mainApp,
  }
}
import mainApp from './components/mainApp.vue';
</script>

<template>
  <div>

  </div>
  <mainApp />
</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use 'bootstrap/scss/bootstrap.scss' as *;
</style>
