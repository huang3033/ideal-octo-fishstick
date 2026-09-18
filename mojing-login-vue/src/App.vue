<script setup>
import { ref, onMounted } from 'vue'
import InkScene from './components/InkScene.vue'
import LoginCard from './components/LoginCard.vue'

const theme = ref('light')

function toggleTheme() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
  document.documentElement.setAttribute('data-theme', theme.value)
}

onMounted(() => {
  document.documentElement.setAttribute('data-theme', theme.value)
})
</script>

<template>
  <button class="theme-toggle" :title="theme === 'light' ? '切换暗色' : '切换亮色'" @click="toggleTheme">
    {{ theme === 'light' ? '☾' : '☀' }}
  </button>

  <main class="page">
    <InkScene />
    <LoginCard />
  </main>
</template>

<style scoped>
.page {
  width: 1440px;
  height: 900px;
  margin: 0 auto;
  display: flex;
  overflow: hidden;
  background: var(--right-bg);
  box-shadow: 0 0 80px rgba(0, 0, 0, 0.08);
}

.theme-toggle {
  position: fixed;
  top: 20px;
  right: 24px;
  z-index: 50;
  width: 40px;
  height: 40px;
  border: 1px solid var(--card-border);
  border-radius: 50%;
  background: var(--card-bg);
  color: var(--ink);
  font-size: 18px;
  cursor: pointer;
  transition: transform 0.2s ease, background 0.3s ease;
}
.theme-toggle:hover {
  transform: scale(1.08);
}

/* 小屏：上下堆叠 */
@media (max-width: 960px) {
  .page {
    width: 100%;
    height: auto;
    flex-direction: column;
  }
}
</style>
