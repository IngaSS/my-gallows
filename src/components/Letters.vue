<template>
  <div class="letters-field">
    <LetterUnit
      v-for="letter of wordUnits"
      :key="letter.name"
      :letter="letter.letter"
      :visible="letter.checked"
    ></LetterUnit>
  </div>
</template>

<script>
import LetterUnit from "./LetterUnit";

export default {
  name: "Letters",
  props: ["wordUnits"],
  components: {
    LetterUnit
  }
};
</script>

<style>
.letters-field {
  margin-top: 30px;
  margin-bottom: 20px;
}
</style>
