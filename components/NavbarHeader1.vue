<template>
  <div class="navbar">
    <div class="navbar-left">
      <div class="logo">
        <img src="~/assets/logo.png" alt="Logo" />
        <span class="HiveMed-name">HiveMed</span>
      </div>
      <ul class="menu">
        <li><a href="#">Home</a></li>
        <li>
          <a href="#">Products</a>
          <ul class="dropdown">
            <li><a href="#" style="color:white">Product 1</a></li>
            <li><a href="#" style="color:white">Product 2</a></li>
            <li><a href="#" style="color:white">Product 3</a></li>
          </ul>
          <span class="dropdown-arrow">&#9660;</span>
        </li>
        <li><a href="#">About</a></li>
        <li>
          <a href="#">Services</a>
          <ul class="dropdown">
            <li><a href="#" style="color:white">Service 1</a></li>
            <li><a href="#" style="color:white">Service 2</a></li>
            <li><a href="#" style="color:white">Service 3</a></li>
          </ul>
          <span class="dropdown-arrow">&#9660;</span>
        </li>
        <li><a href="#">Contacts</a></li>
      </ul>
    </div>
    <div class="navbar-right">
      <button @click="redirectToLogout" class="btn-logout">Log Out</button>
    </div>
  </div>
</template>

<script>
import Cookies from'js-cookie'
export default {
  name: "NavbarHeader",
  methods: {
    redirectToLogout() {
      Cookies.remove('auth_token') 
      this.authToken = ''
      this.$router.push('/'); 
    },
  }
};
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  background-color: #f8f8f8;
  font-size: 20px;
  
}

.navbar-left {
  display: flex;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  font-family: Avenir, Helvetica, Arial, sans-serif; 
  font-weight: bold;
}

.logo img {
  width: 50px;
  height: 50px;
}

.logo span {
  margin-left: 10px;
  font-size: 25px;
  font-weight: bold;
}

.menu {
  display: flex;
  list-style-type: none;
  margin: 0;
  padding: 0;
  margin-left: 50px;
  justify-content: space-between;
  font-family: Avenir, Helvetica, Arial, sans-serif; 
}

.menu li {
  margin-right: 15px;
  padding: 10px;
  border-radius: 5px;
}

.menu li:hover
{
  background-color: rgb(207, 207, 207);
}
.menu a {
  text-decoration: none;
  color: #333;
}

.dropdown {
  display: none;
  position: absolute;
  background-color: black;
  padding: 10px;
}

.dropdown li {
  margin-bottom: 5px;
  color: white;
}

.dropdown-arrow {
  margin-left: 5px;
  font-size: 10px;
  justify-content: center;
}
.menu li:hover .dropdown {
  display: block;
}

.navbar-right {
  display: flex;
  align-items: center;
  font-family: Avenir, Helvetica, Arial, sans-serif; 
  font-size: 20px;
}

.btn-signup
{
  margin-left: 10px;
  padding: 10px;
  background-color: white;
  color: black;
  border: none;
  cursor: pointer;
  font-size: 20px;
  margin-right: 10px;
  border-radius: 5px;
}
.btn-login {
  margin-left: 5px;
  padding: 10px;
  padding-inline: 20px;
  background-color: black;
  color: white;
  border: none;
  cursor: pointer;
  font-size: 20px;
  margin-right: 10px;
  border-radius: 5px;
}

.btn-signup:hover,
.btn-login:hover {
  background-color: rgb(207, 207, 207);
}
</style>