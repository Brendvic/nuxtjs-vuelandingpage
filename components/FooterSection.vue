<template><!--FOOTER-->
  <footer>
  <div class="footer-links">
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About Us</a></li>
      <li><a href="#">Contact Us</a></li>
      <li><a href="#">Privacy Policy</a></li>
    </ul>
  </div>
  <div class="footer-logo">
    <img src='~/assets/logo.png' alt='HiveMed logo'>
  </div>
</footer>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: white;
  padding: 20px;
  font-size: 14px;
  font-family: Arial, sans-serif;
}

.footer-links ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.footer-links li {
  margin-right: 20px;
}

.footer-links a {
  color: #666;
  text-decoration: none;
}

.footer-logo img {
  height: 40px;
  width: auto;
}</style>