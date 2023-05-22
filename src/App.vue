<template>
  <app-content/>
  <app-footer/>
</template>

<script>
import AppContent from './components/AppContent.vue'
import AppFooter from './components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppContent,
    AppFooter,
  }
}
</script>

<style>
body { margin: 0 }
#app{
  width: 100%; height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  text-align: center;
}
</style>
