<template>
  <div>
    <p>You chose {{ $store.getters.flavor }}</p>
  </div>
</template>


<script>
  export default {
    name: "display"
  }
</script>
