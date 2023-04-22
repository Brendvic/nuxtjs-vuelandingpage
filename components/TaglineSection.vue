<template>
  <div class="card">
    <div class="card-image">
      <img src="~/assets/main.jpg" alt="Card Image">
    </div>
    <div class="card-content">
      <h1 class="card-header">Changing the way you receive healtcare.</h1>
      <p class="card-paragraph">Get quick and easy access to medical services with HiveMed. 
        Find doctors, schedule appointments, order medications, and receive remote medical advice and treatment. 
        All from the comfort of your own home. Trust HiveMed for fast and convenient healthcare solutions.
      </p>
      <div class="card-buttons">
        <button class="btn btn-primary">Get Started</button>
        <button class="btn btn-secondary">Learn More</button>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.card {
  margin-top: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #ffffff;
  border-radius: 8px;
  overflow: hidden;
  display: flex;
}

.card-image {
  flex: 0 0 auto;
  width: 641px;
  height: 400px;
  display: flex;
  align-items: center;
  justify-content: center;
  img {
    width: 100%;
    height: 100%;
    object-fit: co;
  }
}

.card-content {
  margin-right: auto;
  margin-left: auto;
  margin-top: 0px;
  flex: 1;
  padding: 16px;
  font-family: Avenir, Helvetica, Arial, sans-serif; 
  text-align: center;
}

.card-header {
  color: black;
  font-family: Helvetica;
  font-weight: bold;
  font-size: 40px;
}

.card-paragraph {
  margin-top: 8px;
  font-size: 16px;
}

.card-buttons {
  margin-top: 16px;
}

.btn {
  margin-right: 8px;
  border: none;
  border-radius: 5px;
  padding: 12px 15px;
  font-size: 16px; 
}
.btn-primary {
  background-color: #000000; 
  color: #ffffff;
}

.btn-secondary {
  background-color: #ffffff;
  color: #000000;
}
</style>