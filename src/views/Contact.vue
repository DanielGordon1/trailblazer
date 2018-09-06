<template>

</template>


<script>
  export default {
    name: 'contact',
    mounted() {
      console.log('mounted contact component')
    this.$root.$on('messageChanged', (dataMessage) => {
      alert("Hello from the main Contact component" + " " + dataMessage);
    })
  }
  }
</script>
