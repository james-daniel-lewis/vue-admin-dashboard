<template>
  <div
    class="container"
    :class="{'light-background' : !isDarkMode, 'dark-background' : isDarkMode}"
  >
    <RequestAccount/>
    <div class="login">
      <img src="@/assets/DCHQ.svg" v-show="isDarkMode">
      <img src="@/assets/DCHQ-dark.svg" v-show="!isDarkMode">

      <h4 :class="{'dark-text' : !isDarkMode, 'light-text' : isDarkMode}">Sign into Design+Code HQ</h4>
      <input
        :class="{'dark-field' : !isDarkMode, 'light-field' : isDarkMode}"
        type="email"
        placeholder="Email"
      >
      <input
        :class="{'dark-field' : !isDarkMode, 'light-field' : isDarkMode}"
        type="password"
        placeholder="Password"
      >
      <button>Sign In</button>
      <router-link
        :class="{'dark-link' : !isDarkMode, 'light-link' : isDarkMode}"
        to="/recover"
      >Forgot your password?</router-link>
      <!-- <button @click="toggleDarkMode">toggle</button>
      ?-->
      <ThemeSwitch/>
    </div>
  </div>
</template>

<script>
import RequestAccount from "@/components/RequestAccount.vue";
import ThemeSwitch from "@/components/ThemeSwitch.vue";

export default {
  name: "SignIn",
  components: {
    RequestAccount,
    ThemeSwitch
  },
  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    }
  }
};
</script>


<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.login {
  width: 400px;
}
</style>