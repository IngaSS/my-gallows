<template>
  <div class="field">
    <input type="text" name="word" placeholder="Введите слово" class="input"  v-bind:value="value"
      v-on:input="$emit('input', $event.target.value)">
    <button class="okButton" @click="accept()">OK</button>
  </div>
</template>

<script>
export default {
  name: "InputField",
  props: ["accept", "show", "value"]
};
</script>

<style>
::placeholder {
  font-size: 20px;
  text-indent: 10px;
}

.input {
  min-width: 260px;
  border-radius: 10px;
  min-height: 35px;
  font-size: 20px;
  text-indent: 10px;
}

.okButton {
  margin-left: 10px;
  min-width: 45px;
  min-height: 45px;
  text-shadow: 0 1px rgba(255, 255, 255, 0.2), 0 -1px rgba(0, 0, 0, 0.8);
  outline: none;
  border: none;
  border-radius: 100px;
  background: rgb(28, 107, 114)
    radial-gradient(
      150% 100% at 50% 5px,
      rgba(255, 255, 255, 0.2),
      rgba(0, 0, 0, 0)
    );
  box-shadow: inset rgba(0, 0, 0, 0.6) 0 -2px 5px,
    inset rgba(252, 255, 255, 0.7) 0 2px 5px, rgba(0, 0, 0, 0.8) 0 2px 5px -1px;
  color: rgb(0, 79, 86);
  user-select: none;
}

.okButton:hover {
  color: rgb(0, 59, 66);
  cursor: pointer;
}

.okButton:active {
  padding-bottom: 1px;
  box-shadow: inset rgba(0, 0, 0, 1) 0 1px 3px,
    inset rgba(0, 0, 0, 0.6) 0 -2px 5px,
    inset rgba(252, 255, 255, 0.7) 0 2px 5px, 0 1px rgba(255, 255, 255, 0.08);
  color: rgb(128, 207, 214);
}
</style>
