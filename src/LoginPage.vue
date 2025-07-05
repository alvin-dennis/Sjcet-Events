<template>
  <div class="container">
    <div class="left-panel">
      <h1 class="login-heading">LOG IN</h1>
      <img src="/login-image.jpg" alt="Login Illustration" class="login-image" />
    </div>

    <div class="right-panel">
      <h2 class="hello">Hello <span class="green">!</span></h2>
      <p class="welcome">Welcome Back</p>
      <p class="subtitle">Log in your account</p>

      <form @submit.prevent="handleLogin">
        <input type="text" placeholder="Username" v-model="username" required />
        <input type="password" placeholder="Password" v-model="password" required />

        <div class="options">
          <label><input type="checkbox" /> Remember me</label>
          <a href="#">Forgot password?</a>
        </div>

        <button type="submit" class="login-btn">Log In</button>
        <button type="button" class="create-btn">Create Account</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LoginPage',
  data() {
    return {
      username: '',
      password: ''
    };
  },
  methods: {
    handleLogin() {
      alert(`Logging in as ${this.username}`);
    }
  }
};
</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: 'Poppins', sans-serif;
}

.container {
  display: flex;
  height: 100vh;
  width: 100%;
}

.left-panel {
  flex: 1;
  background-color: white;
  display: flex;
  flex-direction: column;
  align-items: flex-start; /* Align left */
  justify-content: center;
  padding-left: 60px; /* ⬅ Move content left */
}

.login-heading {
  color: #00c853;
  font-size: 36px;
  text-align: left;
  margin-bottom: 20px;
}

.login-image {
  width: 80%;
  max-width: 350px;
  height: auto;
}

.right-panel {
  flex: 1;
  background-color: #f5f5f5;
  padding: 40px;
  padding-left: 80px; /* ⬅ Push form slightly right */
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.hello {
  color: #00c853;
  font-size: 28px;
  font-weight: bold;
}

.welcome {
  font-size: 20px;
  font-weight: 600;
  margin-top: 5px;
}

.subtitle {
  color: #555;
  margin-bottom: 20px;
}

form {
  display: flex;
  flex-direction: column;
}

input[type="text"],
input[type="password"] {
  padding: 12px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 6px;
}

.options {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 14px;
  margin: 10px 0;
}

.login-btn {
  background-color: #00c853;
  color: white;
  padding: 12px;
  border: none;
  border-radius: 6px;
  margin-top: 10px;
  font-weight: bold;
  cursor: pointer;
}

.create-btn {
  background-color: transparent;
  color: #00c853;
  border: 2px solid #00c853;
  padding: 12px;
  border-radius: 6px;
  font-weight: bold;
  margin-top: 10px;
  cursor: pointer;
}
</style>
