<template>
  <div class="letter">
    <h3 :v-show="visible">{{visible ? letter : ''}}</h3>
  </div>
</template>

<script>
export default {
  name: "LetterUnit",
  props: ["letter", "visible"]
};
</script>

<style>
.letter {
  display: inline-block;
  background-color: transparent;
  min-width: 35px;
  border-radius: 10px;
  border: 2px solid rgb(28, 107, 114);
  min-height: 35px;
  margin-left: 10px;
  box-shadow: rgba(0, 0, 0, 0.6) 0 -2px 5px, rgba(252, 255, 255, 0.7) 0 2px 5px,
    rgba(0, 0, 0, 0.8) 0 2px 5px -1px;
}

h3 {
  margin: 0;
  padding-top: 7px;
}
</style>
