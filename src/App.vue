<template>
  <div class="app">
    <header class="app-header">
      <h1>Chess Website</h1>
    </header>
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>

<script setup>
// Using Composition API
import { onMounted } from 'vue'

onMounted(() => {
  console.log('App mounted')
})
</script>

<style lang="scss" scoped>
.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  
  .app-header {
    height: var(--header-height);
    background-color: var(--primary-color);
    color: var(--piece-white);
    @include flex-center;
    
    h1 {
      font-size: 1.5rem;
      
      @include respond-to('tablet') {
        font-size: 2rem;
      }
    }
  }
  
  main {
    flex: 1;
    padding: 20px;
  }
}
</style>