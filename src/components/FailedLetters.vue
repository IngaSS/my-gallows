<template>
  <div class="failedLetters">
    Вы использовали:
    <div class="wrong" v-for="letter of wrongLetters" :key="letter.name">
      <h3 class="wrongLetters">{{letter}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "FailedLetters",
  props: ["wrongLetters"]
};
</script>

<style>
.failedLetters {
  margin-top: 15px;
  display: inline-flex;
}

.wrongLetters {
  line-height: 4px;
  text-indent: 5px;
  color: brown;
}
</style>
