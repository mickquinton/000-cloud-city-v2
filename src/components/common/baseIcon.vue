<template>
  <section class="wrap-icon">
    <div><img :src="baseIcon" /></div>
  </section>
</template>

<script>
export default {
  props: {
    baseIcon: String
  }
}
</script>

<style lang="scss">
.wrap-icon {
  height: $UI-size-xxxl;
  width: $UI-size-xxxl;
  align-items: center;
}
</style>
