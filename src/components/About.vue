<template>
  <div class="login-page">
    <form @submit.prevent="login">
      <div class="form-group">
        <label for="username">Username</label>
        <input type="text" id="username" v-model="username" required>
      </div>
      <div class="form-group">
        <label for="password">Password</label>
        <input type="password" id="password" v-model="password" required>
      </div>
      <button type="submit">Login</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router'; // Assuming you're using Vue Router for navigation

const username = ref('');
const password = ref('');

const router = useRouter();

function login() {
  // Implement your login logic here
  if (username.value === 'admin' && password.value === 'password') {
    // Assuming successful login, navigate to the dashboard or home page
    router.push('/dashboard'); // Change '/dashboard' to the appropriate route
  } else {
    alert('Invalid username or password'); // Replace with appropriate error handling
  }
}
</script>

<style scoped>
.login-page {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.form-group {
  margin-bottom: 20px;
}

input[type="text"],
input[type="password"] {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>
