<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>

<script>
let totalProfit = 0;
let invoiceNumber = 1;

// Function to add a sale
function addSale() {
    const name = document.getElementById("customer").value.trim();
    const mobile = document.getElementById("mobile").value.trim();
    const helmet = document.getElementById("helmet").value.trim();
    const cost = parseFloat(document.getElementById("cost").value);
    const sale = parseFloat(document.getElementById("sale").value);

    if (!name || !mobile || !helmet || isNaN(cost) || isNaN(sale)) {
        alert("Please fill all fields correctly!");
        return;
    }

    const profit = sale - cost;
    totalProfit += profit;

    // Add row to table with Download Invoice button
    const row = `<tr>
        <td>${name}</td>
        <td>${mobile}</td>
        <td>${helmet}</td>
        <td>₹ ${profit}</td>
        <td><button onclick="downloadInvoice('${name}','${mobile}','${helmet}',${sale},${profit},${invoiceNumber})">Download Invoice</button></td>
    </tr>`;

    document.getElementById("data").innerHTML += row;
    document.getElementById("totalProfit").innerText = totalProfit;

    // Clear input fields
    document.getElementById("customer").value = "";
    document.getElementById("mobile").value = "";
    document.getElementById("helmet").value = "";
    document.getElementById("cost").value = "";
    document.getElementById("sale").value = "";

    invoiceNumber++;
}

// Function to download invoice as PDF
function downloadInvoice(customerName, mobile, helmet, salePrice, profit, invoiceNo) {
    const { jsPDF } = window.jspdf;
    const doc = new jsPDF();

    const now = new Date();
    const date = now.toLocaleDateString();
    const time = now.toLocaleTimeString();

    // Header
    doc.setFontSize(18);
    doc.text("Studio Helmet", 105, 20, null, null, "center");
    doc.setFontSize(12);
    doc.text("Owner: Aijaz Ahmed", 105, 28, null, null, "center");

    // Invoice details
    doc.text(`Invoice No: ${invoiceNo}`, 14, 40);
    doc.text(`Date: ${date}  Time: ${time}`, 14, 48);

    // Customer & sale details
    doc.text(`Customer: ${customerName}`, 14, 60);
    doc.text(`Mobile: ${mobile}`, 14, 68);
    doc.text(`Helmet Model: ${helmet}`, 14, 76);
    doc.text(`Sale Price: ₹${salePrice}`, 14, 84);
    doc.text(`Profit: ₹${profit}`, 14, 92);

    doc.setFontSize(10);
    doc.text("Thank you for shopping with Studio Helmet!", 105, 110, null, null, "center");

    // Save PDF
    doc.save(`Invoice_${invoiceNo}.pdf`);
}
</script>

