<template>
  <div class="about">
    <h1>This is an about page</h1>
    <Name username="Daniel" ></Name>
    <InputLinks :message=message @messageChangedInChild="handleChangeInParent"></InputLinks>
    <FruitPicker :fruits=fruits></FruitPicker>
  </div>
</template>

<script>
// @ is an alias to /src
import Name from "@/components/Name.vue";
import InputLinks from "@/components/InputLinks.vue";
import FruitPicker from "@/components/FruitPicker.vue";

export default {
  name: "about",
  data: function() {
    // Make this array available in this component so that it can be sent as a prop to the FruitPicker component.
    return {
      fruits: ['Apple', 'Banana', 'Strawberry'],
      message: "Default Message"
    }
  },
  methods: {
    handleChangeInParent: function(updatedMessage) {
      this.message = updatedMessage
      console.log('Hello from the Parent', updatedMessage)
    }
  },
  components: {
    Name,
    InputLinks,
    FruitPicker,
  }
};
</script>
