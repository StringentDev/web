<template>
  <div class="bg-gray-50">
    <div
      class="mx-auto max-w-screen-xl px-4 py-12 sm:px-6 lg:items-center lg:justify-between lg:py-16 lg:px-8"
    >
     
      <h1
        class="text-3xl font-extrabold leading-9 tracking-tight text-gray-900 sm:text-7xl sm:leading-15"
      >
        Now that's a
        <span class="text-indigo-600">404 error</span>.
      </h1>
      <br>
      <p class="text-gray-900">I'm too dedicated right now to find what you are looking for in the archeology cupboard. I can tell you a few jokes though.</p>
      <div class="py-3"></div>
      <p class="text-gray-900">{{ joke }}</p>
      <div class="py-8"></div>
      <div class="inline-flex rounded-md shadow mr-2">
        <router-link
          to="/"
          class="inline-flex items-center justify-center rounded-md border border-transparent px-5 py-3 text-base font-medium leading-6 text-gray-900 transition duration-150 ease-in-out bg-white focus:outline-none"
          >Re-enter the other room</router-link
        >
      </div>
    </div>
  </div>
</template>

<script>
// use axios to get a random joke from canihazdadjoke.com
import axios from 'redaxios';
// change value of :text to the content of the joke
export default {
  data() {
    return {
      joke: '...',
    };
  },
  mounted() {
    this.getJoke();
  },
  methods: {
    getJoke() {
      axios.get('https://icanhazdadjoke.com/', {
        headers: {
          Accept: 'application/json'
        }
      }).then(response => {
        this.joke = response.data.joke
        // set timeout for 5 seconds and repeat the joke
        // setTimeout(() => {
        //   this.getJoke();
        // }, 5000);
      })
    }
  }
}
</script>