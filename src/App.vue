<script setup>
import ChatComponent from './components/ChatComponent.vue';
</script>

<template>
  <h1>Chat</h1>
  <main>
    <ChatComponent/>
  </main>
</template>

<style scoped>
h1 {
    font-size: 50px;
}
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
