<html lang="en">
<head>
  <meta charset="UTF-8">
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f5faff;
      padding: 20px;
    }
    h1 {
      color: #0d47a1;
      margin-bottom: 20px;
    }
    label {
      font-weight: bold;
    }
    input {
      padding: 8px;
      width: 200px;
      margin-bottom: 15px;
      display: block;
    }
    button {
      padding: 10px 20px;
      background-color: #1565c0;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
    button:hover {
      background-color: #0d47a1;
    }
    .result {
      margin-top: 20px;
      padding: 15px;
      background-color: #e3f2fd;
      border-left: 5px solid #1976d2;
      color: #333;
      font-size: 1.1em;
    }
  </style>
</head>
<body>

  <h1>Find your desired state in the range 2251–2431</h1>

  <label for="state">Enter Your State Number:</label>
  <input type="number" id="state" placeholder="e.g., 2300">

  <label for="power">Enter Your Power (in millions):</label>
  <input type="number" id="power" placeholder="e.g., 150">

  <button onclick="checkEligibility()">Check</button>

  <div class="result" id="result"></div>

  <script>
    function checkEligibility() {
      const state = parseInt(document.getElementById('state').value);
      const power = parseFloat(document.getElementById('power').value);
      const result = document.getElementById('result');
      result.innerHTML = "";

      if (!state || !power) {
        result.innerHTML = "Please enter both your state and power.";
        return;
      }

      if (state < 2251 || state > 2431) {
        result.innerHTML = "Your state is out of range.";
        return;
      }

      if (power <= 100) {
        result.innerHTML = "At the moment, we are only looking for players above 100 million power.";
        return;
      }

      result.innerHTML = `
        <strong>You should join STR alliance in state 2264!</strong><br><br>
        Contact Kartik at coordinates <strong>X:793 Y:724</strong> to join.<br><br>
        STR is a wonderful alliance in an amazing state with about 90 active players.
        They are a highly active alliance, in the top tier of most events, and currently
        looking for a rally leader. <br><br><strong>You would be perfect for this alliance!</strong>
      `;
    }
  </script>

</body>
</html>
