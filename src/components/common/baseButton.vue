<template>
  <section class="main-btn">{{ btnLabel }}</section>
</template>

<script>
export default {
  props: {
    btnLabel: String
  }
}
</script>

<style lang="scss">
.main-btn {
  cursor: pointer;
  font-weight: 700;
  font-size: $font-captionXS;
  color: $clr-white;
}
</style>
