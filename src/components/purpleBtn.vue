<template lang="">
  <button class="purple_btn">
    <img v-if="btnIcon" :src="btnIcon" alt="ButtonIcon" />
    {{ Btn_text }}
  </button>
</template>
<script>
export default {
  name: 'purple_button',
  props: {
    Btn_text: {
      type: String,
      required: true,
    },
    btnIcon: {
      type: String,
      default: null,
    },
  },
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');

.purple_btn {
  font-family: 'Inter', sans-serif;
  display: flex;
  background-color: #6944d3;
  border: none;
  outline: none;
  padding: 7px 14px;
  color: white;
  cursor: pointer;
  border-radius: 4px;
}
.purple_btn:hover {
  background-color: #9d7ef4;
}
img {
  margin-right: 2px;
}
</style>
