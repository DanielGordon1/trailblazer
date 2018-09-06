<template>
  <div class="input-links">
    <hr>
    <h4>This is the InputLinks component</h4>
    <a class="link" :href="url">{{ linkText }}</a>
    <br>
    <input @change="handleChange()" v-model="dataMessage" placeholder="Enter a message">
    <p>Message is: {{ dataMessage }}</p>
  </div>
</template>

<style>
  .link {text-decoration: none; }
</style>

<script>
  export default {
    name: 'InputLinks',
    props: {
       message: {
        type: String,
        required: true
      }
    },
    data() {
      return {
        url: "www.google.com",
        linkText: "clickbait",
        dataMessage: this.message
      }
    },
    methods: {
      handleChange: function() {
        this.$emit('messageChangedInChild', this.dataMessage)
      }
    }
  }
</script>
