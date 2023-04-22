<template>
    <div class="signup-page">
      <div class="signup-card">
        <h2 class="card-title" style="text-align: center; font-size: 25px;">Create an Account</h2>
        <div class="input-container">
          <label for="email" class="input-label">Enter your email</label>
          <input v-model="email" id="email" type="email" class="input" placeholder="john@doe.com">
        </div>
        <div class="input-container">
          <label for="username" class="input-label">Enter your username</label>
          <input v-model="username" id="username" type="username" class="input" placeholder="johndoe">
        </div>
        <div class="input-container">
          <label for="password" class="input-label">Enter your password</label>
          <input v-model="password" id="password" type="password" class="input" placeholder="secret password">
        </div>
        <div class="checkbox-container">
          <input id="receive-updates" type="checkbox" class="checkbox">
          <label for="receive-updates">Receive updates and special offers</label>
        </div>
        <button type="submit" @click="signup" class="signup-button">Create my HiveMed account</button>
        <p class="terms-conditions">By creating an account, you agree to our <a href="/terms">Terms & Conditions</a> and <a href="/privacy">Privacy Policy</a></p>
      </div>
    </div>
  </template>

<script>
import Cookies from 'js-cookie'
 export default {
    data() {
      return {
        email: '',
        username: '',
        password: ''
      };
    },
    methods: {
      async signup() {

      console.log('Email:', this.email, 'Password:', this.password);
      try {
        const url = 'http://localhost:5000/api/auth/signup';
        const response = await fetch(url , {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify({
            email: this.email,
            username: this.username,
            password: this.password,
          }),
        });
        const data = await response.json();
        if (response.ok) {
          console.log('Signup successful:', data);
          Cookies.set('auth_token', 'your auth-token');
          this.email = '';
          this.password = '';
          this.$router.push('/login');
        } else {
          console.error('Signup failed:', data);
        }
      } catch (error) {
        console.error('Signup failed:', error.message);
      }
    },
  },
};
</script>
  
  <style scoped>
  .signup-page {
    display: flex;
    background: linear-gradient(to bottom, #e9df9f, #d9e3bd);
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-family: Avenir, Helvetica, Arial, sans-serif;
  }
  
  .page-title {
    font-size: 24px;
    text-align: center;
    margin-bottom: 20px;
  }
  
  .signup-card {
    max-width: 400px;
    padding: 30px;
    background-color: #f9f9f9;
    border-radius: 5px;
  }
  
  .card-title {
    font-size: 20px;
    margin-bottom: 20px;
  }
  
  .input-container {
    margin-bottom: 10px;
  }
  
  .input-label {
    display: block;
    font-size: 14px;
    margin-bottom: 5px;
  }
  
  .input {
    width: 379px;
    padding: 10px;
    font-size: 14px;
    border-radius: 3px;
    border: 1px solid #ccc;
  }
  
  .checkbox-container {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
  }
  
  .checkbox {
    margin-right: 5px;
  }
  
  .signup-button {
    width: 100%;
    padding: 12px;
    background-color: black;
    color: #fff;
    font-size: 16px;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    margin-top: 15px;
    margin-bottom: 20px;
  }
  
  .terms-conditions {
    font-size: 12px;
    text-align: center;
  }
  </style>