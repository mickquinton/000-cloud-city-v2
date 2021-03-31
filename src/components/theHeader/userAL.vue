<template>
  <div class="close" @click="toggleDialog()">CLOSE</div>
  <div>
    <p>Yay! I am logged in.</p>
  </div>
</template>

<script>
export default {
  inject: ["toggleDialog"]
}
</script>

<style lang="scss">
// SAMPLE CSS ONLY //

.close {
  cursor: pointer;
  color: rgba(#fff, 0.6);
  font-weight: 600;

  &:hover {
    color: rgba(#fff, 1);
  }
}
</style>
