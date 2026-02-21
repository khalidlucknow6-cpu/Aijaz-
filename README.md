index.html
<html>
<head>
    <title>Studio Helmet - Aijaz Ahmed</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        body {
            font-family: Arial;
            background: #f4f4f4;
            margin: 0;
            padding: 20px;
        }
        h1 {
            text-align: center;
        }
        .box {
            background: white;
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 10px;
            box-shadow: 0 0 10px #ccc;
        }
        input, button {
            width: 100%;
            padding: 10px;
            margin-top: 8px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        button {
            background: black;
            color: white;
            font-weight: bold;
        }
        table {
            width: 100%;
            margin-top: 10px;
            border-collapse: 
             <button onclick="downloadInvoice('Ahmed','9876543210','Vega X',2000,300,1)">
Download Invoice
</button>   collapse;
        }
        table, th, td {
            border: 1px solid #ccc;
            padding: 8px;
        }
        th {
            background: #eee;
        }
        .profit {
            font-weight: bold;
            color: green;
        }
    </style>
</head>

<body>

<h1>Studio Helmet</h1>
<p style="text-align:center;">Owner: Aijaz Ahmed</p>

<div class="box">
    <h3>Add Sale</h3>
    <input type="text" id="customer" placeholder="Customer Name">
    <input type="text" id="mobile" placeholder="Mobile Number">
    <input type="text" id="helmet" placeholder="Helmet Model">
    <input type="number" id="cost" placeholder="Cost Price">
    <input type="number" id="sale" placeholder="Sale Price">
    <button onclick="addSale()">Add Sale</button>
</div>

<div class="box">
    <h3>Sales Data</h3>
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Mobile</th>
                <th>Model</th>
                <th>Profit</th>
            </tr>
        </thead>
        <tbody id="data"></tbody>
    </table>
</div>

<div class="box">
    <h3>Total Profit</h3>
    <p class="profit">₹ <span id="totalProfit">0</span></p>
</div>

<script>
let total = 0;

function addSale() {
    let name = document.getElementById("customer").value;
    let mobile = document.getElementById("mobile").value;
    let helmet = document.getElementById("helmet").value;
    let cost = parseFloat(document.getElementById("cost").value);
    let sale = parseFloat(document.getElementById("sale").value);

    if (!name || !mobile || !helmet || !cost || !sale) {
        alert("Please fill all fields");
        return;
    }

    let profit = sale - cost;
    total += profit;

    let row = `<tr>
        <td>${name}</td>
        <td>${mobile}</td>
        <td>${helmet}</td>
        <td>₹ ${profit}</td>
    </tr>`;

    document.getElementById("data").innerHTML += row;
    document.getElementById("totalProfit").innerText = total;

    document.getElementById("customer").value = "";
    document.getElementById("mobile").value = "";
    document.getElementById("helmet").value = "";
    document.getElementById("cost").value = "";
    document.getElementById("sale").value = "";
}
</script>

</body>
</html><!DOCTYPE html>
<html>
<head>
    <title>Studio Helmet - Aijaz Ahmed</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        body {
            font-family: Arial;
            background: #f4f4f4;
            margin: 0;
            padding: 20px;
        }
        h1 {
            text-align: center;
        }
        .box {
            background: white;
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 10px;
            box-shadow: 0 0 10px #ccc;
        }
        input, button {
            width: 100%;
            padding: 10px;
            margin-top: 8px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        button {
            background: black;
            color: white;
            font-weight: bold;
        }
        table {
            width: 100%;
            margin-top: 10px;
            border-collapse: collapse;
        }
        table, th, td {
            border: 1px solid #ccc;
            padding: 8px;
        }
        th {
            background: #eee;
        }
        .profit {
            font-weight: bold;
            color: green;
        }
    </style>
</head>

<body>

<h1>Studio Helmet</h1>
<p style="text-align:center;">Owner: Aijaz Ahmed</p>

<div class="box">
    <h3>Add Sale</h3>
    <input type="text" id="customer" placeholder="Customer Name">
    <input type="text" id="mobile" placeholder="Mobile Number">
    <input type="text" id="helmet" placeholder="Helmet Model">
    <input type="number" id="cost" placeholder="Cost Price">
    <input type="number" id="sale" placeholder="Sale Price">
    <button onclick="addSale()">Add Sale</button>
</div>

<div class="box">
    <h3>Sales Data</h3>
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Mobile</th>
                <th>Model</th>
                <th>Profit</th>
            </tr>
        </thead>
        <tbody id="data"></tbody>
    </table>
</div>

<div class="box">
    <h3>Total Profit</h3>
    <p class="profit">₹ <span id="totalProfit">0</span></p>
</div>

<script>
let total = 0;

function addSale() {
    let name = document.getElementById("customer").value;
    let mobile = document.getElementById("mobile").value;
    let helmet = document.getElementById("helmet").value;
    let cost = parseFloat(document.getElementById("cost").value);
    let sale = parseFloat(document.getElementById("sale").value);

    if (!name || !mobile || !helmet || !cost || !sale) {
        alert("Please fill all fields");
        return;
    }

    let profit = sale - cost;
    total += profit;

    let row = `<tr>
        <td>${name}</td>
        <td>${mobile}</td>
        <td>${helmet}</td>
        <td>₹ ${profit}</td>
    </tr>`;

    document.getElementById("data").innerHTML += row;
    document.getElementById("totalProfit").innerText = total;

    document.getElementById("customer").value = "";
    document.getElementById("mobile").value = "";
    document.getElementById("helmet").value = "";
    document.getElementById("cost").value = "";
    document.getElementById("sale").value = "";
}
</script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
</body>
</html>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script>
let total = 0;
let invoiceNumber = 1; // Auto-increment invoice number

function addSale() {
    let name = document.getElementById("customer").value;
    let mobile = document.getElementById("mobile").value;
    let helmet = document.getElementById("helmet").value;
    let cost = parseFloat(document.getElementById("cost").value);
    let sale = parseFloat(document.getElementById("sale").value);

    if (!name || !mobile || !helmet || !cost || !sale) {
        alert("Please fill all fields");
        return;
    }

    let profit = sale - cost;
    total += profit;

    // Add sale to table
    let row = `<tr>
        <td>${name}</td>
        <td>${mobile}</td>
        <td>${helmet}</td>
        <td>₹ ${profit}</td>
        <td><button onclick="downloadInvoice('${name}','${mobile}','${helmet}',${sale},${profit},${invoiceNumber})">Download Invoice</button></td>
    </tr>`;
    document.getElementById("data").innerHTML += row;
    document.getElementById("totalProfit").innerText = total;

    // Clear input fields
    document.getElementById("customer").value = "";
    document.getElementById("mobile").value = "";
    document.getElementById("helmet").value = "";
    document.getElementById("cost").value = "";
    document.getElementById("sale").value = "";

    invoiceNumber++; // Increment invoice number for next sale
}

// Function to download invoice as PDF
function downloadInvoice(customerName, mobile, helmet, salePrice, profit, invoiceNo) {
    const { jsPDF } = window.jspdf;
    const doc = new jsPDF();

    const today = new Date();
    const date = today.toLocaleDateString();
    const time = today.toLocaleTimeString();

    doc.setFontSize(18);
    doc.text("Studio Helmet", 105, 20, null, null, "center");
    doc.setFontSize(12);
    doc.text("Owner: Aijaz Ahmed", 105, 28, null, null, "center");
    doc.text(`Invoice No: ${invoiceNo}`, 14, 40);
    doc.text(`Date: ${date} Time: ${time}`, 14, 48);

    doc.text(`Customer: ${customerName}`, 14, 60);
    doc.text(`Mobile: ${mobile}`, 14, 68);
    doc.text(`Helmet Model: ${helmet}`, 14, 76);
    doc.text(`Sale Price: ₹${salePrice}`, 14, 84);
    doc.text(`Profit: ₹${profit}`, 14, 92);

    doc.setFontSize(10);
    doc.text("Thank you for shopping with Studio Helmet!", 105, 110, null, null, "center");

    doc.save(`Invoice_${invoiceNo}.pdf`);
}
</script>
