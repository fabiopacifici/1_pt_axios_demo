<script>
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      word: 'This is a word',
      words: []
    }
  },
  mounted() {
    /* Attention!! Use Arrow function  */
    axios
      .get('https://flynn.boolean.careers/exercises/api/random/word')
      .then((response) => {
        console.log(this);
        console.log(response);
        this.word = response.data.response;
      })

    for (let i = 0; i < 10; i++) {
      axios
        .get('https://flynn.boolean.careers/exercises/api/random/word')
        .then((response) => {
          console.log(this);
          console.log(response);
          this.words.push(response.data.response);
        })
    }
  }
}
</script>
<template>
  <div>{{ word }}</div>
</template>
<style></style>