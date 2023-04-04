<template>
  <!-- nav -->
  <div>
    <nav_bar />
    <hr />
  </div>
  <!-- Main -->
  <main>
    <!-- Left Pannel -->
    <left_dashboard />
    <!-- Right Pannel -->
  </main>
  <!-- Footer -->
  <footer>
    <!-- Question mark symbol and options  -->
  </footer>
</template>

<script>
import nav_bar from '@/components/Nav.vue'
import left_dashboard from './components/left_dashboard.vue'
export default {
  name: 'App',
  components: {
    // Nav,
    nav_bar,
    // Main,
    // Left Pannel
    left_dashboard,
    // Right Pannel
    // Footer
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  background-color: #27272a;
}
template {
  font-family: 'Inter', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
hr {
  border: 0.5px solid #3f3e47;
}
</style>
