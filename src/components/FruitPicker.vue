<template>
  <div class="fruit-picker">
    <div v-if="shouldThisBeShown">
      <hr>
      <h4>This is the FruitPicker component</h4>
      <select v-model="selectedFruit">
        <option disabled value="">Choose a fruit</option>
        <option v-for="fruit in fruits">{{ fruit }}</option>
      </select>
      <br>
    <span>Fruit chosen: {{ selectedFruit }}</span>
    <br>
    <br>
    <!-- <a v-on:click="handleClick('No it should not')">Click me!</a> -->
    <!-- Shorthand syntax -->
    <a @click="handleClick('No it should not')">Click me!</a>
    </div>
    <hr v-show="!shouldThisBeShown">
    <p v-on:click="handleShown($event)" v-show="showThis">Woop Whoop, I get shown</p>
  </div>
</template>

<script>
  export default {
    name: "FruitPicker",
    props: {
      fruits: {
        type: Array,
        required: true
      }
    },
    data() {
      return {
        selectedFruit: "",
        shouldThisBeShown: true,
        showThis: true
      }
    },
    methods: {
      handleClick: function(text) {
        alert(text)
        this.shouldThisBeShown = false
      },
      handleShown: function(event) {
        console.log(event);
        this.showThis = false
      }
    }
  }
</script>
