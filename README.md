<!DOCTYPE html>
weight: bold; border-radius: 8px; }

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
