<template>
  <router-link to="/login">Zaloguj się</router-link>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({})
</script>

<style lang="scss" scoped>
@import '@/styles/index.scss';
a {
  background: theme(main_dark);
  color: theme(light) !important;
  font-weight: 500;
  font-size: 18px;
  padding: 7px 10px;
  border-radius: 5px;
  cursor: pointer;
  @media (max-width: 1000px) {
    background: theme(dark);
    color: theme(light);
    padding: 10px 20px;
  }
}
</style>
