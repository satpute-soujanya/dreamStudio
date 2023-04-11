<template lang="">
  <div class="input_main">
    <div class="postive_prompt">
      <input type="text" v-model="prompt" />
      <!-- <textarea name="" id=""></textarea> -->
      <gray_button Btn_text="Shuffle" @click="shufflePrompt"></gray_button>
    </div>

    <br />
    <input type="text" v-model="neg_prompt" />

    <!-- <textarea name="" id=""></textarea> -->
  </div>
</template>
<script>
import gray_button from './greyBtn.vue'
// import generateIcon from '../assets/generate.png'
// import EditIcon from '../assets/edit.png'
import axios from 'axios'
export default {
  name: 'secondary_nav',
  components: {
    gray_button,
  },
  data() {
    return {
      // generateIcon,
      // EditIcon,
      apiKey: '$2b$10$PojdNjZYqsfrBblyX39CLu.bYTtoX.f0SfT13dlGHWQzf2dtPph/a',
      apiData: '',
      promptArray: '',
      prompt: '',
      neg_prompt: '',
    }
  },
  methods: {
    fetchData() {
      let config = {
        method: 'get',
        maxBodyLength: Infinity,
        url: 'https://api.jsonbin.io/v3/b/64243689ace6f33a22ffa5dd',
        headers: {
          'X-Access-Key':
            '$2b$10$PojdNjZYqsfrBblyX39CLu.bYTtoX.f0SfT13dlGHWQzf2dtPph/a',
        },
      }

      axios
        .request(config)
        .then((response) => {
          this.promptArray = response.data.record.prompts
          this.neg_prompt = response.data.record.negative_prompt
          this.prompt = this.promptArray[0]
        })
        .catch((error) => {
          console.log(error)
        })
    },
    shufflePrompt(e) {
      e.preventDefault()
      const randomIndex = Math.floor(Math.random() * 4)
      this.prompt = this.promptArray[randomIndex]
    },
  },

  mounted() {
    this.fetchData()
  },
}
</script>
<style>
.postive_prompt {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}
.sec_nav {
  display: flex;
  width: 90%;
  justify-content: space-between;
  margin: 10px;
}
.input_main {
  background-color: #18181b;
  width: 100%;
  width: 29vw;
  margin-top: 20px;
}
input[type='text'] {
  width: 20vw;
  height: 30px;
  /* border: 1px solid #000; */
  border-radius: 5px;
  padding: 0 10px;
  margin: 5px;
  outline: 0;
  border: 0;
  background-color: #26272b;
  color: white;
}
</style>
