<template>
  <section class="social-proof">
  <div class="logos">
    <a href='https://vuejs.org/'></a><img src='~/assets/vuejs.png' alt="Partner 1">
    <img src='~/assets/css.png' alt="Partner 2">
    <img src='~/assets/html.png' alt="Partner 3">
    <img src='~/assets/js.png' alt="Partner 4">
    <img src='~/assets/bootstrap.png' alt="Partner 5">
  </div>
</section>

<blockquote class="quote">
  <p class="quote-text">"HiveMed is your partner in healthcare, where your health is our top priority."</p>
  <p class="quote-cite">Hypex, Company behind HiveMed</p>
</blockquote>
</template>

<script>
export default {
  name: 'SocialProof'
}
</script>


<style scoped lang="scss">
.social-proof {
  background-color: white;
  padding: 50px;
  text-align: center;
  border-top: 3px solid black;
  border-bottom: 3px solid black;
  width: 60%;
  margin: 0 auto;
  margin-top: 30px;
}

.social-proof h2 {
  margin-bottom: 30px;
  font-family: Avenir, Helvetica, Arial, sans-serif; 
}

.logos {
  display: flex;
  justify-content: center;
  align-items: center;
  filter: contrast(200%);
}

.logos img {
  max-height: 80px;
  margin: 0 30px;
  
}
.quote {
  text-align: center;
  margin: 30px auto;
  max-width: 80%;
  font-family: Avenir, Helvetica, Arial, sans-serif; 
}

.quote-text {
  font-style: italic;
  font-size: 50px;
  font-weight: bold;
  color: black;
  margin-bottom: 10px;
}

.quote-cite {
  font-weight: 0;
  font-size: 20px;
  color: black;
}
</style>
