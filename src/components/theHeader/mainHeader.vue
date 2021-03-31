<template>
  <base-dialog v-if="isDialogshown"></base-dialog>
  <section>
    <div class="wrap-main-header">
      <!------- Header Logo ------->
      <div class="wrap-header-logo">
        <div class="header-logo"></div>
      </div>

      <!------- Header Nav ------->
      <div class="wrap-header-nav">
        <div class="header-nav" v-for="nav in navLinks" :key="nav">{{ nav }}</div>
      </div>

      <!------- User Toggle ------->
      <user-toggle></user-toggle>
    </div>
  </section>
</template>

<script>
import baseDialog from "../../components/common/baseDialog.vue"
import userToggle from "../../components/theHeader/userToggle.vue"

export default {
  components: {
    "base-dialog": baseDialog,
    "user-toggle": userToggle
  },

  data() {
    return {
      navLinks: ["Stealth", "Shooter", "Magic", "Brawn", "Armor", "Reinforcement"],
      isDialogshown: false,
      userStatus: "",
      isLoggedin: false,
    }
  },

  methods: {

    toggleDialog() {
      this.isDialogshown = !this.isDialogshown
    },

    //   logIn(userStatus) {
    //     this.isLoggedin = !this.isLoggedin
    //     this.userStatus = userStatus
    //   },

    //   logOut(userStatus) {
    //     this.isDialogshown = !this.isDialogshown
    //     this.userStatus = userStatus
    //     this.isLoggedin = false
    //   }
  },

  provide() {
    return {
      toggleDialog: this.toggleDialog
      // logIn: this.logIn,
      // logOut: this.logOut,
    }
  }
}
</script>

<style lang="scss">
// <----- MAIN HEADER -----> //

.wrap-main-header {
  background-color: $clr-primary;
  height: $UI-size-kilo-xxxl;
  color: $clr-white;
  display: flex;
  align-items: center;

  // Header Logo //

  .wrap-header-logo {
    margin: 0 $UI-size-xl 0 $UI-size-xl;

    .header-logo {
      background-image: url("../../assets/cloudcity-logo-light.svg");
      background-repeat: no-repeat;
      background-size: contain;
      background-position: center;
      min-width: $UI-size-kilo-xxl;
      min-height: $UI-size-kilo-xxl;
    }
  }

  // Header Nav //

  .wrap-header-nav {
    display: flex;

    .header-nav {
      cursor: pointer;
      font-weight: 500;
      color: rgba($clr-white, 0.8);
      margin: 0 $UI-size-lg 0 $UI-size-lg;
      font-size: $font-body2;

      &:hover {
        color: rgba($clr-white, 1);
      }
    }
  }
}
</style>
