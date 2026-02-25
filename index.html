<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Studio Helmet - Trading System</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>

<style>
body {
  font-family: Arial;
  margin: 0;
  background: #F4F7FB;
}

header {
  background: #0B5ED7;
  color: white;
  padding: 15px;
  text-align: center;
  font-size: 22px;
  font-weight: bold;
}

.container {
  padding: 20px;
}

.card {
  background: white;
  padding: 15px;
  margin-bottom: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

input, button {
  padding: 8px;
  margin: 5px 0;
}

button {
  border: none;
  cursor: pointer;
  border-radius: 5px;
  font-weight: bold;
}

/* Button Colors */
.excel { background: #198754; color: white; }
.pdf { background: #DC3545; color: white; }
.invoice { background: #6F42C1; color: white; }
.profit-box { background: #20C997; color: white; padding: 15px; font-size: 18px; font-weight: bold; border-radius: 8px; }

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 10px;
}

th {
  background: #E9EEF6;
  padding: 8px;
}

td {
  padding: 8px;
  border-bottom: 1px solid #ddd;
}

.switch {
  width: 60px;
  height: 30px;
  background: #FF6B00;
  border-radius: 20px;
  position: relative;
  cursor: pointer;
}

.switch::after {
  content: "";
  width: 26px;
  height: 26px;
  background: white;
  position: absolute;
  top: 2px;
  left: 2px;
  border-radius: 50%;
  transition: 0.3s;
}

.switch.active {
  background: #198754;
}

.switch.active::after {
  left: 32px;
}
</style>
</head>

<body>

<header>Studio Helmet - General Trading System (₹ INR)</header>

<div class="container">

<div class="card">
<h3>Add Sale</h3>
<input id="customer" placeholder="Customer Name">
<input id="item" placeholder="Item Name">
<input id="saleAmount" type="number" placeholder="Sale Amount (₹)">
<button onclick="addSale()">Add Sale</button>
</div>

<div class="card">
<h3>Add Purchase</h3>
<input id="purchaseItem" placeholder="Item Name">
<input id="purchaseAmount" type="number" placeholder="Purchase Amount (₹)">
<button onclick="addPurchase()">Add Purchase</button>
</div>

<div class="card profit-box">
Total Profit: ₹ <span id="profit">0</span>
</div>

<div class="card">
<h3>Sales History</h3>
<button class="excel" onclick="exportExcel()">Export Excel</button>
<button class="pdf" onclick="exportPDF()">Export PDF</button>
<table id="salesTable">
<thead>
<tr>
<th>Customer</th>
<th>Item</th>
<th>Amount (₹)</th>
</tr>
</thead>
<tbody></tbody>
</table>
</div>

<div class="card">
<h3>Invoice</h3>
<button class="invoice" onclick="generateInvoice()">Generate Invoice PDF</button>
</div>

<div class="card">
<h3>Insurance CSR Switch</h3>
<div class="switch" onclick="toggleSwitch(this)"></div>
</div>

</div>

<script>
let sales = JSON.parse(localStorage.getItem("sales")) || [];
let purchases = JSON.parse(localStorage.getItem("purchases")) || [];

function saveData() {
  localStorage.setItem("sales", JSON.stringify(sales));
  localStorage.setItem("purchases", JSON.stringify(purchases));
  calculateProfit();
  displaySales();
}

function addSale() {
  let customer = document.getElementById("customer").value;
  let item = document.getElementById("item").value;
  let amount = parseFloat(document.getElementById("saleAmount").value);

  if (!customer || !item || !amount) return alert("Fill all fields");

  sales.push({customer, item, amount});
  saveData();
}

function addPurchase() {
  let item = document.getElementById("purchaseItem").value;
  let amount = parseFloat(document.getElementById("purchaseAmount").value);

  if (!item || !amount) return alert("Fill all fields");

  purchases.push({item, amount});
  saveData();
}

function calculateProfit() {
  let totalSales = sales.reduce((a,b)=>a+b.amount,0);
  let totalPurchase = purchases.reduce((a,b)=>a+b.amount,0);
  document.getElementById("profit").innerText = totalSales - totalPurchase;
}

function displaySales() {
  let tbody = document.querySelector("#salesTable tbody");
  tbody.innerHTML = "";
  sales.forEach(s => {
    tbody.innerHTML += `<tr><td>${s.customer}</td><td>${s.item}</td><td>₹ ${s.amount}</td></tr>`;
  });
}

function exportExcel() {
  let ws = XLSX.utils.json_to_sheet(sales);
  let wb = XLSX.utils.book_new();
  XLSX.utils.book_append_sheet(wb, ws, "Sales");
  XLSX.writeFile(wb, "StudioHelmetSales.xlsx");
}

async function exportPDF() {
  const { jsPDF } = window.jspdf;
  const doc = new jsPDF();
  doc.text("Studio Helmet Sales Report", 10, 10);
  let y = 20;
  sales.forEach(s => {
    doc.text(`${s.customer} - ${s.item} - ₹ ${s.amount}`, 10, y);
    y += 10;
  });
  doc.save("SalesReport.pdf");
}

async function generateInvoice() {
  const { jsPDF } = window.jspdf;
  const doc = new jsPDF();
  doc.text("Studio Helmet Invoice", 10, 10);
  doc.text("Thank you for your business!", 10, 20);
  doc.save("Invoice.pdf");
}

function toggleSwitch(el) {
  el.classList.toggle("active");
}

calculateProfit();
displaySales();
</script>

</body>
</html>
