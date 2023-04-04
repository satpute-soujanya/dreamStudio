<template lang="">
  <div class="sec_nav">
    <greyBtn Btn_text="Generate" :btnIcon="generateIcon" />
    <greyBtn Btn_text="Edit" :btnIcon="EditIcon" />
  </div>
</template>
<script>
import greyBtn from './greyBtn.vue'
import generateIcon from '../assets/generate.png'
import EditIcon from '../assets/edit.png'
export default {
  name: 'secondary_nav',
  data() {
    return {
      generateIcon,
      EditIcon,
    }
  },
  components: {
    greyBtn,
  },
}
</script>
<style>
.sec_nav {
  display: flex;
  width: 90%;
  justify-content: space-between;
  margin: 10px;
}
</style>
