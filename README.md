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
<title>AYprints Atelier | Order System</title>

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
  line-height: 1.5;
}

/* HERO */
.hero {
  text-align: center;
  padding: 70px 20px;
  background: linear-gradient(135deg, #5B21B6, #000);
}

.hero h1 {
  font-size: 28px;
  margin-bottom: 10px;
}

/* SECTION */
.section {
  padding: 50px 20px;
  max-width: 900px;
  margin: auto;
  text-align: center;
}

.section h2 {
  margin-bottom: 20px;
}

/* GRID */
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 15px;
}

/* CARD */
.card {
  background: rgba(255,255,255,0.05);
  padding: 18px;
  border-radius: 10px;
  cursor: pointer;
  transition: 0.3s;
}

.card:hover {
  background: rgba(255,255,255,0.1);
  transform: translateY(-3px);
}

/* FORM */
form {
  margin-top: 20px;
}

input, textarea {
  width: 100%;
  padding: 12px;
  margin-top: 10px;
  border-radius: 6px;
  border: none;
}

textarea {
  min-height: 100px;
}

/* BUTTON */
button {
  width: 100%;
  background: #5B21B6;
  color: white;
  padding: 14px;
  border: none;
  border-radius: 6px;
  margin-top: 15px;
  font-size: 16px;
  cursor: pointer;
}

button:hover {
  opacity: 0.9;
}

/* PORTFOLIO */
.portfolio img {
  width: 100%;
  border-radius: 8px;
}

/* FLOAT WHATSAPP */
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
  <p>Order printing, branding & design instantly</p>
</div>

<!-- SERVICES -->
<div class="section">
  <h2>Select Service</h2>
  <div class="grid">
    <div class="card" onclick="selectService('Printing')">Printing</div>
    <div class="card" onclick="selectService('Branding')">Branding</div>
    <div class="card" onclick="selectService('Graphic Design')">Graphic Design</div>
    <div class="card" onclick="selectService('Packaging')">Packaging</div>
  </div>
</div>

<!-- ORDER FORM -->
<div class="section">
  <h2>Place Your Order</h2>

  <form id="orderForm">
    <input type="text" id="name" placeholder="Your Name" required>
    <input type="tel" id="phone" placeholder="Phone Number" required>
    <input type="text" id="service" placeholder="Selected Service" readonly>
    <textarea id="details" placeholder="Describe your order" required></textarea>

    <button type="button" onclick="sendOrder()">Submit Order</button>
  </form>
</div>

<!-- PORTFOLIO -->
<div class="section portfolio">
  <h2>Our Work</h2>
  <div class="grid">
    <img src="https://images.unsplash.com/photo-1526498460520-4c246339dccb" alt="Print sample">
    <img src="https://images.unsplash.com/photo-1526948128573-703ee1aeb6fa" alt="Design sample">
    <img src="https://images.unsplash.com/photo-1522199755839-a2bacb67c546" alt="Branding sample">
  </div>
</div>

<!-- WHATSAPP FLOAT -->
<a class="whatsapp" href="https://wa.me/2347011687351">💬</a>

<script>
let selectedService = "";

// Select service
function selectService(service) {
  selectedService = service;
  document.getElementById("service").value = service;
}

// Send order to WhatsApp
function sendOrder() {
  let name = document.getElementById("name").value.trim();
  let phone = document.getElementById("phone").value.trim();
  let details = document.getElementById("details").value.trim();

  if (!name || !phone || !details || !selectedService) {
    alert("Please fill all fields and select a service.");
    return;
  }

  let message =
`NEW ORDER - AYprints Atelier
Name: ${name}
Phone: ${phone}
Service: ${selectedService}
Details: ${details}`;

  let whatsappURL = "https://wa.me/2347011687351?text=" + encodeURIComponent(message);

  window.open(whatsappURL, "_blank");
}
</script>

</body>
</html>
