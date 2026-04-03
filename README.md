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
<title>AYprints Atelier | Business System</title>

<style>
body {
  margin: 0;
  font-family: Arial;
  background: #0b0b0f;
  color: white;
}

.hero {
  text-align: center;
  padding: 80px 20px;
  background: linear-gradient(135deg, #5B21B6, #000);
}

.section {
  padding: 60px 20px;
  text-align: center;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit,minmax(220px,1fr));
  gap: 20px;
}

.card {
  background: rgba(255,255,255,0.05);
  padding: 20px;
  border-radius: 12px;
}

input, select, textarea {
  width: 100%;
  padding: 12px;
  margin: 8px 0;
  border-radius: 8px;
  border: none;
}

button {
  background: #5B21B6;
  color: white;
  padding: 14px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
}

.portfolio img {
  width: 100%;
  border-radius: 10px;
}

.whatsapp {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: #25D366;
  padding: 15px;
  border-radius: 50%;
  text-decoration: none;
  color: white;
}
</style>
</head>

<body>

<div class="hero">
  <h1>AYprints Atelier Business System</h1>
  <p>Order printing, branding & design instantly</p>
</div>

<!-- SERVICES -->
<div class="section">
  <h2>Choose Service</h2>
  <div class="grid">
    <div class="card" onclick="selectService('Printing')">Printing</div>
    <div class="card" onclick="selectService('Branding')">Branding</div>
    <div class="card" onclick="selectService('Graphic Design')">Graphic Design</div>
    <div class="card" onclick="selectService('Packaging')">Packaging</div>
  </div>
</div>

<!-- ORDER FORM -->
<div class="section">
  <h2>Place Order</h2>

  <form id="orderForm">
    <input type="text" id="name" placeholder="Your Name" required>
    <input type="text" id="phone" placeholder="Phone Number" required>
    <input type="text" id="service" placeholder="Selected Service" readonly>
    <textarea id="details" placeholder="Describe your order" required></textarea>

    <button type="button" onclick="sendOrder()">Submit Order</button>
  </form>
</div>

<!-- PORTFOLIO -->
<div class="section portfolio">
  <h2>Portfolio</h2>
  <div class="grid">
    <img src="https://images.unsplash.com/photo-1526498460520-4c246339dccb">
    <img src="https://images.unsplash.com/photo-1526948128573-703ee1aeb6fa">
    <img src="https://images.unsplash.com/photo-1522199755839-a2bacb67c546">
  </div>
</div>

<a class="whatsapp" href="https://wa.me/2347011687351">💬</a>

<script>
let selectedService = "";

function selectService(service){
  selectedService = service;
  document.getElementById("service").value = service;
}

function sendOrder(){
  let name = document.getElementById("name").value;
  let phone = document.getElementById("phone").value;
  let details = document.getElementById("details").value;

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
