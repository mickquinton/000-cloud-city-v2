<template>
  <section class="wrap-dialog" :dialog="isDialogshown">
    <div class="sideSheet">
      <div class="close-icon" @click="toggleDialog()"></div>
      <!-- <user-bl v-if="isLoggedin == false"></user-bl>
      <user-al v-if="isLoggedin == true"></user-al> -->
    </div>
  </section>
</template>

<script>
// import userBL from "../../components/theHeader/userBL.vue"
// import userAL from "../../components/theHeader/userAL.vue"

export default {
  // components: {
  //   "user-bl": userBL,
  //   "user-al": userAL
  // },

  props: {
    isDialogshown: Boolean,
    isLoggedin: Boolean,
  },

  inject: ["toggleDialog"]

}
</script>

<style lang="scss">
// <--- SIDE SHEET ---> //

.wrap-dialog {
  background-color: rgba($clr-black, 0.7);
  z-index: 1;
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;

  .sideSheet {
    display: flex;
    flex-direction: column;
    height: 100%;
    width: 25rem;
    background-color: $clr-primary;
    margin-left: auto;
    color: #fff;

     .close-icon {
      cursor: pointer;
      background-image: url("../../assets/icon-close-light.svg");
      background-repeat: no-repeat;
      background-size: contain;
      background-position: center;
      min-width: $UI-size-xl;
      min-height: $UI-size-xl;
      opacity: 0.8;
      height: $UI-size-kilo-xxxl;
      margin: 0 $UI-size-lg 0 auto;

      &:hover {
        opacity: 1;
      }
    }
  }
}
</style>
