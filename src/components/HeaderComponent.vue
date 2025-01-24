<template>
  <div class="navbar container py-4">
    <img alt="Vue logo" src="../assets/logo.png" width="75" height="75" />
    <div class="d-flex justify-content-end w-100">
      <router-link to="/" class="px-1 color-dark">Home</router-link>
      <router-link to="/about" class="px-1 color-dark" v-if="this.islogged"
        >About</router-link
      >
      <router-link to="/login" class="px-1 color-dark" v-if="!this.islogged">
        Login
        <!-- <i class="bi bi-person-circle"></i> -->
      </router-link>
      <router-link
        to="/"
        class="px-1 color-dark"
        v-if="this.islogged"
        @click="removeToken()"
      >
        Salir de la cuenta
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    islogged: {
      type: Boolean,
    },
  },
  methods: {
    removeToken() {
      localStorage.removeItem("token");
      this.updateisLogged();
      window.location.reload();
    },
    updateisLogged() {
      this.$emit("updateLogged");
    },
  },
};
</script>

<style scoped>
.navbar {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  flex-wrap: nowrap;
}
.bg-blueprin {
  background-color: #3a5c9e;
}
.color-dark {
  color: white;
  text-decoration: none;
}
@media (max-width: 900px) {
  .container {
    width: 80vw;
  }
}
</style>