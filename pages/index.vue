<template>
  <div class="container">
    <div>
      <h1 class="title test">
        HOME
      </h1>
      <br />
      message: {{ message }}
      <br />
      myNewMessage: {{ myNewMessage }}
    </div>
    <button @click="clickMe">Click Me</button>
    <br />
    <br />
    API Data: <br />{{ post }}
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Home',
  head: {
    title: 'Home page',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Home page description',
      },
    ],
  },
  data() {
    return {
      message: 'hello',
    };
  },
  computed: {
    myNewMessage() {
      return `${this.message} world`;
    },
  },
  methods: {
    clickMe() {
      alert('i was clicked');
    },
  },
  async asyncData({ params }) {
    const response = await axios.get('https://api.nuxtjs.dev/posts');
    const post = response.data;
    return { post };
  },
};
</script>
