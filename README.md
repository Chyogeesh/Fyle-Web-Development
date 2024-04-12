# Fyle-Web-Development
It is a internship assignment
HTML (index.html):
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tax Calculator</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="container">
    <h1>Tax Calculator</h1>
    <form id="taxForm">
      <div class="form-group">
        <label for="income">Gross Annual Income (₹):</label>
        <input type="number" id="income" name="income" required>
        <span class="error-icon">!</span>
      </div>
      <!-- Other input fields for extra income, deductions, and age -->
      <button type="submit">Calculate Tax</button>
    </form>
  </div>

  <div id="modal" class="modal">
    <div class="modal-content">
      <span class="close">&times;</span>
      <h2>Tax Calculation Result</h2>
      <p id="taxAmount">Your calculated tax amount will appear here.</p>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>
CSS (styles.css):
#css
body {
  font-family: Arial, sans-serif;
}

.container {
  max-width: 600px;
  margin: 0 auto;
}

.form-group {
  margin-bottom: 20px;
}

input[type="number"] {
  width: 100%;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.error-icon {
  color: red;
}

.modal {
  display: none;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgb(0,0,0);
  background-color: rgba(0,0,0,0.4);
}

.modal-content {
  background-color: #fefefe;
  margin: 10% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}
JavaScript (script.js):
document.getElementById('taxForm').addEventListener('submit', function(event) {
  event.preventDefault();

  // Get form values
  const income = parseFloat(document.getElementById('income').value);
  // Get other input field values (extra income, deductions, and age)

  // Perform tax calculation based on provided formula
  let taxAmount = 0;
  // Your tax calculation logic here

  // Display tax amount in modal
  const modal = document.getElementById('modal');
  const taxAmountText = document.getElementById('taxAmount');
  taxAmountText.textContent = `Your calculated tax amount is: ₹${taxAmount}`;
  modal.style.display = 'block';
});

// Close modal when the close button is clicked
document.getElementsByClassName('close')[0].addEventListener('click', function() {
  document.getElementById('modal').style.display = 'none';
});
