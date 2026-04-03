# ayprintsatelier.com
Branding 
Graphic Designing
Printing
Souvenirs
Frame

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AYprints Atelier</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  background: #0b0b0f;
  color: white;
}

/* CONTAINER */
.container {
  max-width: 900px;
  margin: auto;
  padding: 20px;
}

/* HERO */
.hero {
  text-align: center;
  padding: 60px 20px;
  background: linear-gradient(135deg, #5B21B6, #000);
}

.hero h1 {
  font-size: 26px;
  margin-bottom: 10px;
}

/* SECTION */
.section {
  margin-top: 40px;
}

.section h2 {
  text-align: center;
  margin-bottom: 20px;
}

/* SERVICES */
.services {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
}

.card {
  background: rgba(255,255,255,0.05);
  padding: 18px;
  border-radius: 8px;
  text-align: center;
  cursor: pointer;
  transition: 0.3s;
}

.card:hover {
  background: rgba(255,255,255,0.1);
}

/* FORM */
form {
  display: flex;
  flex-direction: column;
}

input, textarea {
  margin-top: 10px;
  padding: 12px;
  border-radius: 6px;
  border: none;
}

textarea {
  min-height: 100px;
}

/* BUTTON */
button {
  margin-top: 15px;
  padding: 14px;
  background: #5B21B6;
  color: white;
  border: none;
  border-radius: 6px;
  font-size: 16px;
  cursor: pointer;
}

/* WHATSAPP */
.whatsapp {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: #25D366;
  padding: 14px;
  border-radius: 50%;
  text-decoration: none;
  color: white;
  font-size: 18px;
}
</style>
</head>

<body>

<!-- HERO -->
<div class="hero">
  <h1>AYprints Atelier</h1>
  <p>Professional Printing • Branding • Design</p>
</div>

<div class="container">

  <!-- SERVICES -->
  <div class="section">
    <h2>Select Service</h2>
    <div class="services">
      <div class="card" onclick="selectService('Printing')">Printing</div>
      <div class="card" onclick="selectService('Branding')">Branding</div>
      <div class="card" onclick="selectService('Graphic Design')">Graphic Design</div>
      <div class="card" onclick="selectService('Packaging')">Packaging</div>
    </div>
  </div>

  <!-- FORM -->
  <div class="section">
    <h2>Place Your Order</h2>

    <form>
      <input type="text" id="name" placeholder="Your Name" required>
      <input type="tel" id="phone" placeholder="Phone Number" required>
      <input type="text" id="service" placeholder="Selected Service" readonly>
      <textarea id="details" placeholder="Describe your order" required></textarea>

      <button type="button" onclick="sendOrder()">Submit Order</button>
    </form>
  </div>

</div>

<!-- WHATSAPP FLOAT -->
<a class="whatsapp" href="https://wa.me/2347011687351">💬</a>

<script>
let selectedService = "";

function selectService(service) {
  selectedService = service;
  document.getElementById("service").value = service;
}

function sendOrder() {
  let name = document.getElementById("name").value.trim();
  let phone = document.getElementById("phone").value.trim();
  let details = document.getElementById("details").value.trim();

  if (!name || !phone || !details || !selectedService) {
    alert("Please fill everything.");
    return;
  }

  let message =
`NEW ORDER - AYprints Atelier
Name: ${name}
Phone: ${phone}
Service: ${selectedService}
Details: ${details}`;

  let url = "https://wa.me/2347011687351?text=" + encodeURIComponent(message);
  window.open(url, "_blank");
}
</script>

</body>
</html>
