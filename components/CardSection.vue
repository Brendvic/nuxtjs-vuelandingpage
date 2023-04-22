<template>
  <div class="card-container">
    <div class="card">
      <img src='~/assets/chat.jpg' alt="Card Image">
      <div class="card-body">
        <h5 class="card-title">Chat System</h5>
        <p class="card-text">Includes chat system for communication between entities.</p>
      </div>
    </div>
    <div class="card">
      <img src='~/assets/prescription.jpg' alt="Card Image">
      <div class="card-body">
        <h5 class="card-title">Online Prescription</h5>
        <p class="card-text">Allows the communication of medical prescription from one entity to another.</p>
      </div>
    </div>
    <div class="card">
      <img src='~/assets/ehr.jpg' alt="Card Image">
      <div class="card-body">
        <h5 class="card-title">EHR Integration</h5>
        <p class="card-text">Supports Electronic Health Record Integration for greater support on 
          medical records, histories, and healthcare features.</p>
      </div>
    </div>
  </div>
</template>



<script>
export default {
  name: 'CardSection',

}
</script>

<style scoped lang="scss">
img {
    width: 200;
    height: 259;
    object-fit: cover;
  }
.card-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 50px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
}

.card {
  width: 300px;
  margin: 20px;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  border-radius: 10px;
  
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.card-body {
  padding: 20px;
  height: 200px;
}

.card-title {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

.card-text {
  font-size: 16px;
  margin-bottom: 20px;
}
</style>