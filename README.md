<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Parking System</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Smart Parking System</h1>
        <p><strong>Team:</strong> Madhankumar (Project Head), Pavanlal (Lead Developer), Gowtham (Lead Designer), Kamaleshnee (Designer)</p>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#timeline">Timeline</a></li>
                <li><a href="#team">Team</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="home">
        <h2>Welcome to Smart Parking System</h2>
        <p>The Smart Parking System is designed to optimize parking space usage and make the parking experience more efficient using modern technology.</p>
    </section>

    <section id="about">
        <h2>About the Project</h2>
        <p>The Smart Parking System aims to provide real-time parking availability updates, automated payment systems, and efficient parking space management using IoT (Internet of Things) and sensor technologies. This project is designed to reduce the time spent searching for parking spots and help cities better manage parking resources.</p>
    </section>

    <section id="timeline">
        <h2>Project Timeline</h2>
        <p>Our project is divided into several key phases:</p>
        <ul>
            <li><strong>Phase 1:</strong> Research and Planning (Jan 2023 - Feb 2024)</li>
            <li><strong>Phase 2:</strong> Design and Development (Mar 2023 - Jun 2024)</li>
            <li><strong>Phase 3:</strong> Testing and Deployment (Jul 2023 - Sep 2024)</li>
            <li><strong>Phase 4:</strong> Feedback and Optimization (Oct 2023 - Dec 2024)</li>
        </ul>
    </section>

    <section id="team">
        <h2>Meet the Team</h2>
        <p>Our team consists of professionals from various domains who are committed to making the Smart Parking System a success:</p>
        <ul>
            <li><strong>Madhankumar:</strong> Project Head</li>
            <li><strong>Pavanlal:</strong> Lead Developer</li>
            <li><strong>Gowtham:</strong> Lead Designer</li>
            <li><strong>Kamaleshnee:</strong> Designer</li>
        </ul>
    </section>

    <section id="contact">
        <h2>Contact</h2>
        <p>If you have any questions or would like to get involved, feel free to reach out:</p>
        <p>Email: <a href="mailto:madhankumar@gmail.com">madhankumar@gmail.com</a></p>
        <p>Phone:+917687980982</p>
    </section>

    <footer>
     
    </footer>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Parking System</title>
    <link rel="stylesheet" href="styles.css">
    <script src="https://cdn.jsdelivr.net/npm/qrcodejs/qrcode.min.js"></script>
</head>
<body>

    <div id="loginPage">
        <h2>Login / Register</h2>
        <input type="email" id="email" placeholder="Enter Email">
        <input type="password" id="password" placeholder="Enter Password">
        <button onclick="login()">Login</button>
        <button onclick="googleLogin()">Login with Google</button>
    </div>

    <div id="locationPage" style="display:none;">
        <h2>Enter Your Location</h2>
        <input type="text" id="location" placeholder="Enter Location">
        <button onclick="findParking()">Find Parking</button>
    </div>

    <div id="parkingSelection" style="display:none;">
        <h2>Select Parking Slot</h2>
        <label>Date:</label><input type="date" id="date">
        <label>Time:</label><input type="time" id="time">
        <label>vehicle:</label><input type="number" id="vehicle" min="1" value="1">
        <label>Floor:</label>
        <select id="floor">
            <option>1st Floor</option>
            <option>2nd Floor</option>
            <option>3rd Floor</option>
        </select>
        <label>Slot:</label>
        <select id="slot" onchange="markSlotRed()">
            <option value="A1">A1</option>
            <option value="A2">A2</option>
            <option value="A3">A3</option>
        </select>
        <button onclick="proceedToPayment()">Proceed to Payment</button>
    </div>

    <div id="paymentPage" style="display:none;">
        <h2>Payment</h2>
        <p>Total Amount: ₹<span id="totalAmount"></span></p>
        <button onclick="generateQRCode()">Pay with UPI</button>
        <div id="qrcode"></div>
        <button onclick="confirmBooking()">Confirm Booking</button>
    </div>

    <div id="confirmationPage" style="display:none;">
        <h2>Booking Confirmed</h2>
        <p>Order ID: <span id="orderId"></span></p>
        <p>Slot: <span id="selectedSlot"></span></p>
        <p>Total Amount Paid: ₹<span id="paidAmount"></span></p>
        <div id="bookingQRCode"></div>
        <h3>Receipt</h3>
        <pre id="receipt"></pre>
    </div>

    <script src="script.js"></script>
</body>
</html>
/* Styling for Team Information Section */
#team-info {
    background-color: #f4f4f4;
    padding: 20px;
    border-radius: 10px;
    margin: 20px 0;
    text-align: center;
    font-family: Arial, sans-serif;
}

#team-info p {
    font-size: 18px;
    color: #333;
    margin: 5px 0;
}

/* Additional Styles */
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    margin: 0;
    padding: 0;
}

header {
    background-color: #4CAF50;
    color: white;
    padding: 20px;
    text-align: center;
}

nav ul {
    list-style-type: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 10px;
}

nav ul li a {
    color: white;
    text-decoration: none;
    font-size: 18px;
}

section {
    padding: 20px;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px;
    position: fixed;
    width: 100%;
    bottom: 0;
}
document.addEventListener('DOMContentLoaded', function() {
    // Optional: Display a welcome alert when the page loads
    alert("Welcome to the Smart Parking System!");
});
document.addEventListener("DOMContentLoaded", function () {
    alert("Welcome to the Smart Parking System!");
});

function login() {
    let email = document.getElementById("email").value;
    let password = document.getElementById("password").value;

    if (email && password) {
        alert("Login Successful");
        document.getElementById("loginPage").style.display = "none";
        document.getElementById("locationPage").style.display = "block";
    } else {
        alert("Enter valid details");
    }
}

function googleLogin() {
    alert("Google Login (Simulated)");
    document.getElementById("loginPage").style.display = "none";
    document.getElementById("locationPage").style.display = "block";
}

function findParking() {
    let location = document.getElementById("location").value;

    if (location.trim()) {
        alert(`Showing nearby parking for: ${location}`);
        document.getElementById("locationPage").style.display = "none";
        document.getElementById("parkingSelection").style.display = "block";
    } else {
        alert("Enter a valid location");
    }
}

function markSlotRed() {
    let selectedSlot = document.getElementById("slot").value;

    // Reset all options first
    document.querySelectorAll("#slot option").forEach(slot => slot.classList.remove("selected"));

    // Apply 'selected' class to chosen option
    document.querySelector(`#slot option[value='${selectedSlot}']`).classList.add("selected");
}

function proceedToPayment() {
    let vehicle = document.getElementById("vehicle").value;
    let totalAmount = vehicle * 100; // ₹100 per vehicle (Example Pricing)

    document.getElementById("totalAmount").innerText = totalAmount;
    document.getElementById("parkingSelection").style.display = "none";
    document.getElementById("paymentPage").style.display = "block";
}

function generateQRCode() {
    let upiID = "madhankodhandan2005@okicici";
    let totalAmount = document.getElementById("totalAmount").innerText;

    let upiUrl = `upi://pay?pa=${upiID}&pn=Madhankumar&am=${totalAmount}&cu=INR`;

    document.getElementById("qrcode").innerHTML = ""; // Clear previous QR code
    new QRCode(document.getElementById("qrcode"), upiUrl);
}

function confirmBooking() {
    let orderId = "ORD" + Math.floor(1000 + Math.random() * 9000);
    let selectedSlot = document.getElementById("slot").value;
    let totalAmount = document.getElementById("totalAmount").innerText;

    document.getElementById("orderId").innerText = orderId;
    document.getElementById("selectedSlot").innerText = selectedSlot;
    document.getElementById("paidAmount").innerText = totalAmount;

    document.getElementById("paymentPage").style.display = "none";
    document.getElementById("confirmationPage").style.display = "block";

    let bookingInfo = `Order ID: ${orderId} | Slot: ${selectedSlot} | Amount: ₹${totalAmount}`;
    
    document.getElementById("bookingQRCode").innerHTML = ""; // Clear previous QR code
    new QRCode(document.getElementById("bookingQRCode"), bookingInfo);

    generateReceipt(orderId, selectedSlot, totalAmount);
    alert("Booking Confirmed! QR code sent to email & phone.");
}

function generateReceipt(orderId, slot, amount) {
    let receiptText = `
    =====================
      PARKING RECEIPT
    =====================
    Order ID: ${orderId}
    Slot: ${slot}
    Amount Paid: ₹${amount}
    Payment Mode: UPI
    =====================
    Thank You!
    `;

    document.getElementById("receipt").innerText = receiptText;
}
