<template>
  <router-view/>
  <app-footer/>
</template>

<script>
import AppFooter from '@/components/AppFooter.vue'

export default {
  components: {
    AppFooter,    
  }
}
</script>