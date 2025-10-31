<template>
  <div class="login">
    <h2>Login</h2>
    <!--
      @submit.prevent="handleLogin"
      mencegah form me-refresh halaman,
      dan memanggil method 'handleLogin'
    -->
    <form @submit.prevent="handleLogin">
      <div>
        <label for="username">Username:</label>
        <input type="text" v-model="username" required />
      </div>
      <div>
        <label for="password">Password:</label>
        <input type="password" v-model="password" required />
      </div>
      <button type="submit">Login</button>

      <!-- JAWABAN: tambahkan directive percabangan (v-if) -->
      <p v-if="errorMessage" class="error">{{ errorMessage }}</p>

    </form>
  </div>
</template>

<script lang="ts">
export default {
  name: 'UserLogin',
  data() {
    return {
      username: '',
      password: '',
      errorMessage: '' // State untuk menyimpan pesan error
    };
  },
  methods: {
    handleLogin() {
      // JAWABAN: cek jika user dan pass yang diinputkan adalah "admin"
      if (this.username === 'Tatang' && this.password === 'tatang123') {
        this.errorMessage = '';
        this.$emit('loginSuccess');
      } else {
        // JAWABAN: Definisikan kalimat "invalid user or pass" jika gagal login
        this.errorMessage = 'Invalid username or password';
      }
    }
  }
};
</script>

<!--
  'scoped' berarti style ini HANYA berlaku untuk komponen ini
  dan tidak akan "bocor" ke komponen lain.
-->
<style scoped>
 .error{
   color: red;
   text-align: center;
   margin-top: 10px;
 }

 /* (Saya tambahkan sedikit style agar form-nya terlihat lebih baik) */
 .login {
   width: 300px;
   margin: 50px auto;
   padding: 20px;
   border: 1px solid #ccc;
   border-radius: 8px;
   box-shadow: 0 2px 5px rgba(0,0,0,0.1);
 }
 .login h2 {
   text-align: center;
   margin-top: 0;
 }
 .login div {
   margin-bottom: 15px;
 }
 .login label {
   display: block;
   margin-bottom: 5px;
   font-weight: bold;
 }
 .login input {
   width: 100%;
   padding: 8px;
   box-sizing: border-box; /* Ini penting agar padding tidak merusak lebar */
   border: 1px solid #ddd;
   border-radius: 4px;
 }
 .login button {
   width: 100%;
   padding: 10px;
   background-color: #007bff;
   color: white;
   border: none;
   border-radius: 4px;
   cursor: pointer;
   font-size: 16px;
 }
 .login button:hover {
   background-color: #0056b3;
 }
</style>

