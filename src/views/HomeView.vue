<template>
  <app-content/>
</template>

<script>
import AppContent from '@/components/AppContent.vue';
// import AppFooter from '@/components/AppFooter.vue'

export default {
  components: {
    AppContent,
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