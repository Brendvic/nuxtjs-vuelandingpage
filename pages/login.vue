<template>
    <div class="login-page">
      <div class="login-card">
        <h2 class="card-title" style="font-size:20px;">Good to See you Again</h2>
        <div class="input-container">
          <label for="email" class="input-label">Your Email</label>
          <div class="input-icon-container">
            <img src="~/assets/user.png" style="width: 28px; height: 32px;" class="input-icon" alt="Email Icon">
            <input id="email" type="email" class="input-field" v-model="email" placeholder="e.g. john@doe.com">
            <i class="input-icon fas fa-user"></i>
          </div>
        </div>
        <div class="input-container">
          <label for="password" class="input-label">Your Password</label>
          <div class="input-icon-container">
            <img src="~/assets/lock.png" class="input-icon" alt="Email Icon">
            <input id="password" type="password" class="input-field" v-model="password" placeholder="e.g. ilovehivemed123">
            <i class="input-icon fas fa-lock"></i>
          </div>
        </div>
        <div class="forgot-password-container">
          <a href="#" class="forgot-password-link">Forgot Password?</a>
        </div>
        <div class="login-button-container">
          <button class="login-button" @click="login">Login</button>
        </div>
        <div class="signup-container">
          <p class="signup-text">Don't have an account? <a href="#" class="signup-link">Sign up</a></p>
        </div>
        <div class="social-media-icons-container">
          <i class="social-media-icon fab fa-facebook"></i>
          <i class="social-media-icon fab fa-twitter"></i>
          <i class="social-media-icon fab fa-google"></i>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import Cookies from 'js-cookie'
  export default {
    data() {
      return {
        email: '',
        password: ''
      };
    },
    methods: {
      async login() {

      console.log('Email:', this.email, 'Password:', this.password);
      try {
        const url = 'http://localhost:5000/api/auth/login';
        const response = await fetch(url , {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify({
            email: this.email,
            password: this.password,
          }),
        });
        const data = await response.json();
        if (response.ok) {
          console.log('Login successful:', data);
          Cookies.set('auth_token', 'your auth-token');
          this.email = '';
          this.password = '';
          // Redirect to the dashboard
          this.$router.push('/index1');
        } else {
          console.error('Login failed:', data);
        }
      } catch (error) {
        console.error('Login failed:', error.message);
      }
    },
  },
};
  </script>
  
<style scoped>
.input-icon-container img {
  width: 25px;
  height: 25px;
}

  .login-page {
    background: linear-gradient(to bottom, #e9df9f, #d9e3bd);
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: Avenir, Helvetica, Arial, sans-serif;
}
  
  .logo-container {
    text-align: center;
    margin-top: -20px;
}
  
  .logo-image {
    width: 50px;
    height: 50px;
}
  
  .logo-name {
    font-size: 20px;
    font-weight: bold;
    color: #FFFFFF;
    margin-top: 8px;
}
  
  .login-card {
    background-color: #FFFFFF;
    padding: 50px;
    border-radius: 8px;
    width: 300px;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
    margin-bottom: 20px;
}
  
  .card-title {
    font-size: 18px;
    font-weight: bold;
    color: #333333;
    margin-bottom: 24px;
    text-align: center;
}
  
  .input-container {
    margin-bottom: 16px;
} 
  
  .input-label {
    font-size: 14px;
    color: #666666;
}
  
  .input-field {
    width: 250px;
    height: 40px;
    border: 1px solid #CCCCCC;
    border-radius: 4px;
    padding: 8px;
    padding-left: 40px;
    font-size: 14px;
}

.input-icon-container {
position: relative;
}

.input-icon {
position: absolute;
top: 50%;
left: 12px;
transform: translateY(-50%);
color: #999999;
}

.forgot-password-container {
text-align: center;
margin-bottom: 16px;
}

.forgot-password-link {
font-size: 14px;
color: #3366FF;
text-decoration: underline;
}

.login-button-container {
display: flex;
justify-content: center;
margin-bottom: 24px;
}

.login-button {
background-color: black;
color: #FFFFFF;
padding: 12px 130px;
border: none;
border-radius: 50px;
font-size: 16px;
cursor: pointer;
}

.signup-container {
text-align: center;
margin-bottom: 16px;
}

.signup-text {
font-size: 14px;
color: #666666;
}

.signup-link {
color: #3366FF;
text-decoration: underline;
}

.social-media-icons-container {
display: flex;
justify-content: center;
}

.social-media-icon {
font-size: 24px;
color: #999999;
margin: 0 8px;
cursor: pointer;
}

</style>