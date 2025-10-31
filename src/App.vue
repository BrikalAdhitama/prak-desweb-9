<template>
  <div id="app">
    <!-- JAWABAN: Tag HTML di sini adalah nama komponen yang sudah didaftarkan, yaitu 'UserLogin' -->
    <UserLogin v-if="!isLoggedIn" @loginSuccess="handleLoginSuccess" />

    <!-- JAWABAN: Tag HTML di sini adalah 'UserDashboard' -->
    <UserDashboard v-else @logout="handleLogout" />
  </div>
</template>

<script lang="ts">
// JAWABAN: Definisikan variabel import
import UserLogin from './components/UserLogin.vue';
import UserDashboard from './components/UserDashboard.vue';

export default {
  name: 'App',
  components: {
    // JAWABAN: Panggil components yang akan digunakan
    UserLogin,
    UserDashboard
  },
  data() {
    return {
      isLoggedIn: false
    };
  },
  // Saya tambahkan 'methods' untuk membuat kode lebih rapi
  // (Meskipun @loginSuccess="isLoggedIn = true" juga valid)
  methods: {
    handleLoginSuccess() {
      this.isLoggedIn = true;
    },
    handleLogout() {
      this.isLoggedIn = false;
    }
  }
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
}
</style>
