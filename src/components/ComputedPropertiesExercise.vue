<template>
  <div class="computed-properties-exercise container">
    <div class="row">
      <div class="col-12">
        <div class="border p-1">
          <div class="reverse-message">
            <input v-model="state.inputMessage">
            <p>Original Message: {{state.inputMessage}}</p>
            <p>Computed Reversed Message: {{state.reversedMessage}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import { computed, reactive } from "vue";
export default {
  name: "computed-properties-exercise",
  setup() {
    const state = reactive({
      // After getting this to work, challenge yourself to add an input field and bind message to it, so as you type the message gets reversed!
      inputMessage: "Type your message",
      message: "Hello World!",
      reversedMessage: computed(() => { return state.inputMessage.split("").reverse().join("")}),
    });
    return {
      state,
    };
  },
};
</script>


<style scoped>
</style>
