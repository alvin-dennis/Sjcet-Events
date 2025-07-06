<template>
  <div class="login-container">
    <div class="login-left-custom">
      <div class="login-bg-rectangle"></div>
      <h1 class="login-title-custom">LOG IN</h1>
      <img class="login-svg-image" src="/assets/image.svg" alt="Login SVG" />
    </div>
    <div class="login-right">
      <div class="login-box">
        <h2 class="welcome">Hello !<br /><span>Welcome Back</span></h2>
        <p class="login-sub">Log in your account</p>
        <form @submit.prevent="onLogin">
          <div class="input-group">
            <label for="username">Username</label>
            <input type="text" id="username" v-model="username" required />
          </div>
          <div class="input-group">
            <label for="password">Password</label>
            <input type="password" id="password" v-model="password" required />
          </div>
          <div class="options">
            <label><input type="checkbox" v-model="showPassword" @change="togglePassword" /> Show Password</label>
            <a href="#" class="forgot">Forgot password?</a>
          </div>
          <button class="login-btn" type="submit">Log in</button>
          <button class="create-btn" type="button">Create Account</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const username = ref('');
const password = ref('');
const showPassword = ref(false);

function togglePassword() {
  const pwdInput = document.getElementById('password');
  if (pwdInput) {
    pwdInput.type = showPassword.value ? 'text' : 'password';
  }
}

function onLogin() {
  // Dummy login handler
  alert(`Logged in as ${username.value}`);
}
</script>

<style scoped>
.login-container {
  display: flex;
  min-height: 100vh;
  background: #333;
  align-items: center;
  justify-content: center;
}
.login-left-custom {
  position: relative;
  width: 520px;
  height: 700px;
  background: #26C061;
  border-top-left-radius: 16px;
  border-bottom-left-radius: 16px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
}
.login-bg-rectangle {
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  background: #26C061;
  z-index: 1;
}
.login-title-custom {
  position: absolute;
  left: 48px;
  top: 56px;
  font-family: 'Montserrat', sans-serif;
  font-style: normal;
  font-weight: 800;
  font-size: 72px;
  line-height: 90px;
  letter-spacing: 0.04em;
  text-transform: uppercase;
  color: #fff;
  z-index: 2;
}
.login-svg-image {
  position: absolute;
  left: 48px;
  top: 180px;
  width: 420px;
  height: 420px;
  object-fit: contain;
  z-index: 2;
}
.login-right {
  background: #fff;
  padding: 48px 40px;
  border-top-right-radius: 16px;
  border-bottom-right-radius: 16px;
  min-width: 400px;
  min-height: 700px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.login-box {
  width: 100%;
}
.welcome {
  color: #2ecc71;
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
  font-weight: 600;
}
.welcome span {
  color: #333;
  font-size: 1.1rem;
  font-weight: 400;
}
.login-sub {
  color: #888;
  margin-bottom: 1.5rem;
  font-size: 1rem;
}
.input-group {
  margin-bottom: 1.2rem;
}
.input-group label {
  display: block;
  color: #333;
  margin-bottom: 0.3rem;
  font-size: 0.95rem;
}
.input-group input {
  width: 100%;
  padding: 0.7rem 0.9rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 1rem;
  outline: none;
  transition: border 0.2s;
  color: #111;
  background: #fff;
}
.input-group input:focus {
  border: 1.5px solid #2ecc71;
}
.options {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.2rem;
}
.options label {
  font-size: 0.95rem;
  color: #1d1c1c;
}
.options .forgot {
  color: #2ecc71;
  text-decoration: none;
  font-size: 0.95rem;
}
.login-btn {
  width: 100%;
  background: #2ecc71;
  color: #fff;
  border: none;
  padding: 0.8rem 0;
  border-radius: 5px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  margin-bottom: 0.7rem;
  transition: background 0.2s;
}
.login-btn:hover {
  background: #27ae60;
}
.create-btn {
  width: 100%;
  background: #fff;
  color: #2ecc71;
  border: 1.5px solid #2ecc71;
  padding: 0.8rem 0;
  border-radius: 5px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.2s, color 0.2s;
}
.create-btn:hover {
  background: #2ecc71;
  color: #fff;
}
@media (max-width: 800px) {
  .login-container {
    flex-direction: column;
    min-height: unset;
  }
  .login-left, .login-right {
    border-radius: 10px 10px 0 0;
    min-width: unset;
    min-height: 300px;
    width: 100%;
    padding: 30px 10px;
  }
}
</style>
