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
import { onMounted } from 'vue'
import './assets/scss/main.scss'

onMounted(() => {
  console.log('App mounted')
})
</script>

<style lang="scss">
.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  
  .app-header {
    height: var(--header-height);
    background-color: var(--primary-color);
    color: var(--piece-white);
    display: flex;
    justify-content: center;
    align-items: center;
    
    h1 {
      font-size: 1.5rem;
      
      @media screen and (min-width: 768px) {
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