<template>
  <div class="newGame">
    <button class="okButton newGameBtn" @click="startNewGame()">Новая игра</button>
  </div>
</template>

<script>
export default {
  name: "NewGame",
  props: ["startNewGame"]
};
</script>

<style>
.newGameBtn {
  margin-top: 20px;
  min-width: 200px;
  min-height: 40px;
  text-transform: uppercase;
}
</style>
