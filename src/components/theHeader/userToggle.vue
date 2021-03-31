<template>
  <div class="wrap-user-info">
    <!------- Logged out ------->
    <div class="wrap-user-logged-out" v-if="isUserin == false">
      <base-button class="button" :btnLabel="btnLabels[0].forLogin" @click="logIn()"></base-button>
      <div class="loggedout-icon" @click="toggleDialog()"></div>
    </div>

    <!------- Logged in ------->
    <div class="wrap-user-logged-in" v-if="isUserin == true">
      <div class="loggedin-icon" @click="toggleDialog()"></div>
    </div>
  </div>
</template>

<script>
import baseButton from "../../components/common/baseButton.vue"

export default {
  components: {
    "base-button": baseButton
  },

  data() {
    return {
      btnLabels: [{ forLogin: "LOG IN" }, { forLogout: "LOG OUT" }],
      isUserin: false
    }
  },

  methods: {
    logIn() {
      this.isUserin = true
    }
  },

  props: {
    isDialogshown: Boolean,
    userStatus: String
    // isLoggedin: Boolean,
  },

  inject: ["toggleDialog"]
}
</script>

<style lang="scss">
// <----- USER TOGGLE -----> //

.wrap-user-info {
  margin: 0 $UI-size-xl 0 auto;

  // Logged out //

  .wrap-user-logged-out {
    display: flex;

    .button {
      cursor: pointer;
      font-weight: 600;
      background-color: $clr-swatchPrimary-850;
      padding: $UI-size-reg $UI-size-lg $UI-size-reg $UI-size-lg;
      margin: 0 $UI-size-xl 0 0;
      border-radius: $UI-size-reg;
      min-width: $UI-size-kilo-xxl;
      text-align: center;
      font-size: $font-body2;

      &:hover {
        background-color: rgba($clr-swatchPrimary-800, 0.6);
      }
    }

    .loggedout-icon {
      cursor: pointer;
      background-image: url("../../assets/icon-grid-menu-light.svg");
      background-repeat: no-repeat;
      background-size: contain;
      background-position: center;
      min-width: $UI-size-xl;
      min-height: $UI-size-xl;
      opacity: 0.8;
      margin: 0 $UI-size-reg 0 0;

      &:hover {
        opacity: 1;
      }
    }
  }

  // Logged in //

  .wrap-user-logged-in {
    display: flex;

    .loggedin-icon {
      cursor: pointer;
      background-image: url("../../assets/icon-user-light.svg");
      background-repeat: no-repeat;
      background-size: contain;
      background-position: center;
      min-width: $UI-size-xl;
      min-height: $UI-size-xl;
      opacity: 0.8;
      margin: 0 $UI-size-reg 0 0;

      &:hover {
        opacity: 1;
      }
    }
  }
}
</style>
