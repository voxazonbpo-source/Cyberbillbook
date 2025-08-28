<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cyber Space CSC Bill</title>
    <!-- Tailwind CSS for modern styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');
        body {
            font-family: 'Inter', sans-serif;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }
        /* Custom styles for printing */
        @media print {
            .no-print {
                display: none !important;
            }
            body {
                background-color: #fff;
            }
            .container {
                box-shadow: none !important;
                border: 1px solid #000;
                padding: 1rem !important;
                margin: 0 !important;
                border-radius: 0;
            }
        }
    </style>
</head>
<body class="bg-gray-100 flex items-center justify-center p-4 min-h-screen">

    <div class="container bg-white rounded-lg shadow-2xl p-8 max-w-4xl w-full transition-all duration-300 transform scale-95 md:scale-100">
        
        <!-- Header -->
        <header class="text-center mb-8">
            <h1 class="text-4xl md:text-5xl font-extrabold text-blue-800 mb-2">CYBER SPACE CSC CENTER</h1>
            <h2 class="text-xl md:text-2xl font-semibold text-gray-700 mb-4">BILL</h2>
            <div class="text-sm text-gray-500">
                <p>Address: Vijayapuram Bldg, Aalmavu Jn, Pullad, Pathanamthitta Dist, Kerala 689548</p>
                <p>Phone: +91 - 9048623696 | Email: csc.aalmavu@gmail.com</p>
            </div>
        </header>

        <hr class="border-gray-300 mb-6">

        <!-- Invoice Details & Customer Info -->
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 text-sm mb-6">
            <div>
                <p class="font-bold text-gray-700">INVOICE DETAILS</p>
                <div class="flex items-center gap-2 mt-2">
                    <label for="invoice-no" class="text-gray-600 w-24">Invoice No.:</label>
                    <input type="text" id="invoice-no" value="PI-2025-001" class="border rounded-md px-3 py-1 bg-gray-50 w-full focus:outline-none focus:ring-2 focus:ring-blue-500">
                </div>
                <div class="flex items-center gap-2 mt-2">
                    <label for="invoice-date" class="text-gray-600 w-24">Date:</label>
                    <input type="date" id="invoice-date" value="" class="border rounded-md px-3 py-1 bg-gray-50 w-full focus:outline-none focus:ring-2 focus:ring-blue-500">
                </div>
            </div>
            
            <div>
                <p class="font-bold text-gray-700">CUSTOMER DETAILS</p>
                <div class="flex items-center gap-2 mt-2">
                    <label for="customer-name" class="text-gray-600 w-24">Name:</label>
                    <input type="text" id="customer-name" placeholder="Enter Customer Name" class="border rounded-md px-3 py-1 w-full focus:outline-none focus:ring-2 focus:ring-blue-500">
                </div>
                <div class="flex items-center gap-2 mt-2">
                    <label for="customer-phone" class="text-gray-600 w-24">Phone:</label>
                    <input type="text" id="customer-phone" placeholder="Enter Phone Number" class="border rounded-md px-3 py-1 w-full focus:outline-none focus:ring-2 focus:ring-blue-500">
                </div>
                <div class="flex items-center gap-2 mt-2">
                    <label for="customer-email" class="text-gray-600 w-24">Email:</label>
                    <input type="email" id="customer-email" placeholder="Enter Email Address" class="border rounded-md px-3 py-1 w-full focus:outline-none focus:ring-2 focus:ring-blue-500">
                </div>
            </div>
        </div>

        <!-- Service Details Table -->
        <div class="overflow-x-auto">
            <table id="services-table" class="w-full text-left border-collapse table-auto text-sm">
                <thead>
                    <tr class="bg-blue-100 text-blue-800 font-semibold text-center rounded-t-lg">
                        <th class="p-3 rounded-tl-lg">S.No.</th>
                        <th class="p-3">Service Description</th>
                        <th class="p-3">Quantity</th>
                        <th class="p-3">Rate (₹)</th>
                        <th class="p-3 rounded-tr-lg">Amount (₹)</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- Initial rows, more can be added via JS -->
                    <tr class="bg-gray-50">
                        <td class="p-3 border-b text-center text-gray-600">1</td>
                        <td class="p-3 border-b"><input type="text" placeholder="e.g., Aadhar Card Update" class="w-full bg-transparent focus:outline-none"></td>
                        <td class="p-3 border-b"><input type="number" value="1" min="0" oninput="updateAmount(this)" class="w-20 text-center bg-transparent focus:outline-none"></td>
                        <td class="p-3 border-b"><input type="number" value="50" min="0" step="0.01" oninput="updateAmount(this)" class="w-20 text-center bg-transparent focus:outline-none"></td>
                        <td class="p-3 border-b text-right font-medium amount">50.00</td>
                    </tr>
                    <tr class="bg-white">
                        <td class="p-3 border-b text-center text-gray-600">2</td>
                        <td class="p-3 border-b"><input type="text" placeholder="e.g., Document Printouts (B/W)" class="w-full bg-transparent focus:outline-none"></td>
                        <td class="p-3 border-b"><input type="number" value="10" min="0" oninput="updateAmount(this)" class="w-20 text-center bg-transparent focus:outline-none"></td>
                        <td class="p-3 border-b"><input type="number" value="5" min="0" step="0.01" oninput="updateAmount(this)" class="w-20 text-center bg-transparent focus:outline-none"></td>
                        <td class="p-3 border-b text-right font-medium amount">50.00</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <div class="flex justify-end mt-4 no-print">
            <button onclick="addRow()" class="bg-blue-500 text-white px-4 py-2 rounded-lg text-sm font-semibold shadow-md hover:bg-blue-600 transition-colors duration-200">
                + Add Service
            </button>
        </div>

        <!-- Totals Section -->
        <div class="flex justify-end mt-8">
            <div class="w-full md:w-1/2">
                <div class="flex justify-between items-center text-lg font-bold text-gray-800 mb-2">
                    <p>Subtotal:</p>
                    <p id="subtotal">₹ 0.00</p>
                </div>
                <div class="flex justify-between items-center text-lg font-bold text-gray-800 mb-2">
                    <div class="flex items-center">
                        <p>GST:</p>
                        <input type="number" id="gst-rate" value="18" min="0" oninput="calculateTotal()" class="w-16 text-center border-b mx-2 focus:outline-none focus:ring-1 focus:ring-blue-500">
                        <p>%</p>
                    </div>
                    <p id="gst-amount">₹ 0.00</p>
                </div>
                <div class="flex justify-between items-center text-2xl font-extrabold text-blue-800 border-t-2 border-blue-800 pt-4 mt-4">
                    <p>Total Amount:</p>
                    <p id="total-amount">₹ 0.00</p>
                </div>
            </div>
        </div>

        <!-- Print & Signature Section -->
        <div class="mt-8 flex justify-between items-end">
            <div class="flex flex-col items-center">
                <hr class="w-48 h-px bg-gray-500 border-0 mb-2">
                <p class="text-sm text-gray-600">Authorized Signatory</p>
            </div>
            <div class="no-print">
                <button onclick="printBill()" class="bg-green-600 text-white px-8 py-3 rounded-lg text-lg font-bold shadow-lg hover:bg-green-700 transition-colors duration-200">
                    <svg class="w-6 h-6 inline-block mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 17h2a2 2 0 002-2v-4a2 2 0 00-2-2H5a2 2 0 00-2 2v4a2 2 0 002 2h2m2 4h6a2 2 0 002-2v-4a2 2 0 00-2-2H9a2 2 0 00-2 2v4a2 2 0 002 2zm8-12V5a2 2 0 00-2-2H9a2 2 0 00-2 2v4m4 6h.01"></path></svg>
                    Print Bill
                </button>
            </div>
        </div>

    </div>

    <script>
        const servicesTable = document.getElementById('services-table').getElementsByTagName('tbody')[0];
        const subtotalEl = document.getElementById('subtotal');
        const gstRateEl = document.getElementById('gst-rate');
        const gstAmountEl = document.getElementById('gst-amount');
        const totalAmountEl = document.getElementById('total-amount');

        // Set today's date
        document.getElementById('invoice-date').valueAsDate = new Date();

        /**
         * Calculates and updates the amount for a specific service row.
         * @param {HTMLElement} element - The input element (quantity or rate) that was changed.
         */
        function updateAmount(element) {
            const row = element.closest('tr');
            const quantityInput = row.cells[2].querySelector('input');
            const rateInput = row.cells[3].querySelector('input');
            const amountCell = row.cells[4];

            const quantity = parseFloat(quantityInput.value) || 0;
            const rate = parseFloat(rateInput.value) || 0;
            const amount = (quantity * rate).toFixed(2);
            amountCell.textContent = amount;

            // Recalculate the entire bill
            calculateTotal();
        }

        /**
         * Calculates the subtotal, GST, and final total amount for the entire bill.
         */
        function calculateTotal() {
            let subtotal = 0;
            // Iterate through all rows to sum up the amounts
            document.querySelectorAll('#services-table tbody tr').forEach(row => {
                const amountText = row.cells[4].textContent;
                subtotal += parseFloat(amountText) || 0;
            });

            const gstRate = parseFloat(gstRateEl.value) || 0;
            const gstAmount = (subtotal * gstRate / 100).toFixed(2);
            const totalAmount = (subtotal + parseFloat(gstAmount)).toFixed(2);

            // Update the display elements
            subtotalEl.textContent = `₹ ${subtotal.toFixed(2)}`;
            gstAmountEl.textContent = `₹ ${gstAmount}`;
            totalAmountEl.textContent = `₹ ${totalAmount}`;
        }

        /**
         * Adds a new, empty service row to the table.
         */
        function addRow() {
            const newRow = servicesTable.insertRow();
            const sNo = servicesTable.rows.length;
            newRow.className = sNo % 2 === 0 ? 'bg-white' : 'bg-gray-50';

            newRow.innerHTML = `
                <td class="p-3 border-b text-center text-gray-600">${sNo}</td>
                <td class="p-3 border-b"><input type="text" placeholder="Service Description" class="w-full bg-transparent focus:outline-none"></td>
                <td class="p-3 border-b"><input type="number" value="1" min="0" oninput="updateAmount(this)" class="w-20 text-center bg-transparent focus:outline-none"></td>
                <td class="p-3 border-b"><input type="number" value="0" min="0" step="0.01" oninput="updateAmount(this)" class="w-20 text-center bg-transparent focus:outline-none"></td>
                <td class="p-3 border-b text-right font-medium amount">0.00</td>
            `;
            calculateTotal(); // Recalculate after adding a new row
        }

        /**
         * Triggers the browser's print dialog.
         */
        function printBill() {
            window.print();
        }

        // Initial calculation on page load
        window.onload = function() {
            calculateTotal();
        };

    </script>
</body>
</html>
