<script setup>
import gitHubIcon from "./icons/gitHubIcon.vue";
</script>

<template>
  <nav>
    <div>
      <gitHubIcon class="github-icon" />
      <h1>Osemeke C. Victor Rep</h1>
    </div>
  </nav>
</template>

<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  background: var(--color-background);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.github-icon {
  width: 32px;
  height: 32px;
  font-size: 2rem;
}
</style>
