<template>
  <div class="score">
    <img :src="img" alt="#" class="img">
  </div>
</template>

<script>
export default {
  name: "Score",
  props: ["errors", "img"]
};
</script>
