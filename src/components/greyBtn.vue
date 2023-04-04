<template lang="">
  <button class="grey_btn">
    <img v-if="btnIcon" :src="btnIcon" alt="ButtonIcon" />
    {{ Btn_text }}
  </button>
</template>
<script>
export default {
  name: 'gray_button',
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
.grey_btn {
  font-family: 'Inter', sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #3f3e47;
  border: none;
  outline: none;
  padding: 7px 14px;
  color: white;
  cursor: pointer;
  border-radius: 4px;
  z-index: 1000;
}

img {
  margin-left: 2px;
}
</style>
