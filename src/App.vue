<template>
  <main>
    <Navbar />
    <notifications position="bottom left" width="400px" />
    <router-view />
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Navbar from '@/components/Shared/Navbar/Index.vue'

export default defineComponent({
  components: {
    Navbar,
  },
})
</script>

<style lang="scss">
@import './styles/index.scss';
main {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 100vh;
}
</style>
