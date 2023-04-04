<template>
  <nav>
    <img :src="logo" alt="brand logo" />
    <purple_button Btn_text="Login" />
  </nav>
</template>
<script>
import logo from '@/assets/logo.png'
import purple_button from '@/components/purpleBtn.vue'
export default {
  name: 'nav_bar',
  components: {
    purple_button,
  },
  data() {
    return {
      logo: logo,
    }
  },
}
</script>
<style>
nav {
  background-color: #18181b;
  min-width: 1000px;
  border: rgba(0, 0, 0, 0.2);
  min-height: 49px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
nav :nth-child(2) {
  margin-right: 5px;
}
nav img {
  margin-left: 5px;
}
</style>
