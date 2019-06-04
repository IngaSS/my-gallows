<template>
  <div class="field">
    <input type="text" name="letter" placeholder="Введите букву" class="input" v-bind:value="value"
      v-on:input="$emit('input', $event.target.value)">
    <button class="okButton" @click="submitLetter()">OK</button>
  </div>
</template>

<script>
export default {
  name: "InputletterField",
  props: ["submitLetter", "value"]
};
</script>
