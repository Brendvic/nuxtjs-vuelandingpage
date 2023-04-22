<template>
  <div class="card-section">
    <div class="card doctors">
      <img src='~/assets/doctor.png' alt="Doctor Icon">
      <h3>Doctors</h3>
      <p>Find a doctor near you.</p>
    </div>
  <div class="card pharmacies">
    <img src='~/assets/pharmacy.png' alt="Pharmacy Icon">
      <h3>Pharmacies</h3>
      <p>Find a pharmacy near you.</p>
  </div>
    <div class="card hospitals">
      <img src='~/assets/hospital.png' alt="Hospital Icon">
      <h3>Hospitals</h3>
      <p>Find a hospital near you.</p>
    </div>
  <div class="card health-schedule">
    <img src='~/assets/schedule.png' alt="Schedule Icon">
    <h3>Health Schedule</h3>
     <p>Manage your health appointments.</p>
    </div>
  <div class="card health-record">
    <img src='~/assets/record.png' alt="Record Icon">
    <h3>Health Record</h3>
      <p>View your health records.</p>
    </div>
  <div class="card ambulance-call">
    <img src='~/assets/call.png' alt="Call Icon">
    <h3>Ambulance Call</h3>
      <p>Call for emergency ambulance.</p>
    </div>
  </div>
</template>

<script>
export default {
	name: 'ContactSection'
}
</script>

<style scoped lang="scss">
.card img {
  width: 50px;
  height: auto;
  margin-bottom: 5px;
  display: inline-block;
}
.card-section {
  display: flex;
  flex-wrap: wrap;
  gap: 0;
  border-radius: 0px;
  overflow: hidden;
  box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.2);
  background-color: white;
  border-top: 1px solid #ccc;
  border-bottom: 1px solid #ccc;
  border-left: 1px solid #ccc;
  border-right: 1px solid #ccc;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.2); 
  width: 90%;
  margin: 0 auto;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

.card {
  background-color: white;
  border-radius: 0;
  box-shadow: none;
  transition: background-color 0.3s, color 0.3s;
  width: 33.33%;
  border: none;
  margin: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.card:first-child {
  border-top-left-radius: 0px;
  border-bottom-left-radius: 0px;
}

.card:last-child {
  border-top-right-radius: 0px;
  border-bottom-right-radius: 0px;
}

.doctors:hover {
  background-color: #8BC34A;
  color: #fff;
}

.pharmacies:hover {
  background-color: #2196F3;
  color: #fff;
}

.hospitals:hover {
  background-color: #F44336;
  color: #fff;
}

.health-schedule:hover {
  background-color: #FF9800;
  color: #fff;
}

.health-record:hover {
  background-color: #673AB7;
  color: #fff;
}

.ambulance-call:hover {
  background-color: #E91E63;
  color: #fff;
}
</style>