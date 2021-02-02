<template>
  <div class="container">
    <div>
      <h1 class="title">
        HOME
      </h1>
      <Test />
      <div class="links">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/about">About</NuxtLink>
      </div>
      <pre>{{ post }}</pre>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  async asyncData({ params }) {
    const response = await axios.get('https://api.nuxtjs.dev/posts');
    const post = response.data;
    return { post };
  },
};
</script>
