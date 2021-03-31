<template>
  <section class="wrap-dialog" :dialog="isDialogshown">
    <div class="sideSheet">
      <!-- <component :is="userType"></component> -->
      <user-bl v-if="isLoggedin == false"></user-bl>
      <user-al v-if="isLoggedin == true"></user-al>
    </div>
  </section>
</template>

<script>
import userBL from "../../components/theHeader/userBL.vue"
import userAL from "../../components/theHeader/userAL.vue"

export default {

  components: {
    "user-bl": userBL,
    "user-al": userAL
  },

  props: {
    isDialogshown: Boolean,
    userStatus: String,
    isLoggedin: Boolean,
  }
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
    height: 100%;
    width: 25rem;
    background-color: $clr-primary;
    margin-left: auto;
    color: #fff;
  }
}
</style>
