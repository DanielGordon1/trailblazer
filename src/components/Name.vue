<template>
  <div class="username">
    <hr>
    <h4>This is the name component</h4>
    <h2 :style="{textDecoration: decoration}">{{ username }}</h2>
    <h2>{{ secondname.split('').reverse().join('') }}</h2>
    <h3 class="light">{{ thirdname | fallback | capitalize }}</h3>
  </div>

</template>

<style>
.light { font-weight: lighter; }
</style>

<script>

export default {
  name: "Name",
  props: {
    username: {
      type: String,
      required: true
    }
  },
  data() {
    return {
    secondname: "Jimmy",
    thirdname: "",
    decoration: "underline",
    message: ""
    }
  },
  filters: {
    fallback: (thirdname) => {
      return thirdname ? thirdname : "stranger"
    },
    capitalize: (fallback) => {
      return fallback.charAt(0).toUpperCase() + fallback.slice(1)
    }
  }
}
</script>
