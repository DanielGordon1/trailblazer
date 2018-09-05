<template>
  <div class="about">
    <h1>This is an about page</h1>
    <Name username="Daniel"></Name>
  </div>
</template>

<script>
// @ is an alias to /src
import Name from "@/components/Name.vue";

export default {
  name: "about",
  components: {
    Name
  }
};
</script>
