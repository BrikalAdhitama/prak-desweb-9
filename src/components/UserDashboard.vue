<template>
  <div class="dashboard">
    <h2>Welcome to the Dashboard</h2>
    <p>You are logged in.</p>
    <!-- JAWABAN: tambahkan directive event listener @click -->
    <button @click="logout">Logout</button>
  </div>
</template>

<script lang="ts">
export default {
  name: 'UserDashboard',
  methods: {
    logout() {
      // Baris ini sudah benar, ia mengirim sinyal 'logout'
      // kembali ke App.vue
      this.$emit('logout');
    }
  }
};
</script>

<style scoped>
.dashboard {
  text-align: center;
}
</style>
