<template>
  <div class="input-links">
    <hr>
    <h4>This is the InputLinks component</h4>
    <a class="link" :href="url">{{ linkText }}</a>
    <br>
    <input v-model="message" placeholder="Enter a message">
    <p>Message is: {{ message }}</p>
  </div>
</template>

<style>
  .link {text-decoration: none; }
</style>

<script>
  export default {
    name: 'InputLinks',
    data() {
      return {
        url: "www.google.com",
        linkText: "clickbait",
        message: ""
      }
    }
  }
</script>
