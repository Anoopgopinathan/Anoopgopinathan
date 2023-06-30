<!DOCTYPE html>
<!-- saved from url=(0048)file:///D:/OneDrive/Desktop/hagenpoisseuli12.htm -->
<html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
  <title>Hagen-Poiseuille's Equation Solver</title>
  <script>
    function calculateFlowRate() {
      var radius = parseFloat(document.getElementById("radius").value);
      var viscosity = parseFloat(document.getElementById("viscosity").value);
      var pressure = parseFloat(document.getElementById("pressure").value);
      var length = parseFloat(document.getElementById("length").value);

      var flowRate = (Math.PI * Math.pow(radius, 4) * pressure) / (8 * viscosity * length);

      document.getElementById("result").innerHTML = "Flow rate: " + flowRate.toFixed(2) + " units";

      // Update the URL with the input values
      var url = https://hagen123.com; // Get the base URL without query parameters
      url += "?radius=" + radius + "&viscosity=" + viscosity + "&pressure=" + pressure + "&length=" + length;
      history.pushState(null, null, url);
    }

    // Populate the input fields with values from the URL
    function populateInputsFromUrl() {
      var urlParams = new URLSearchParams(window.location.search);
      document.getElementById("radius").value = urlParams.get("radius") || "";
      document.getElementById("viscosity").value = urlParams.get("viscosity") || "";
      document.getElementById("pressure").value = urlParams.get("pressure") || "";
      document.getElementById("length").value = urlParams.get("length") || "";
    }
  </script>
</head>
<body onload="populateInputsFromUrl()">
  <h2>Hagen-Poiseuille's Equation Solver</h2>

  <label for="radius">Tube Radius (r) [m]:</label>
  <input type="text" id="radius" placeholder="Enter radius">

  <label for="viscosity">Fluid Viscosity (η) [Pa·s]:</label>
  <input type="text" id="viscosity" placeholder="Enter viscosity">

  <label for="pressure">Pressure Difference (ΔP) [Pa]:</label>
  <input type="text" id="pressure" placeholder="Enter pressure">

  <label for="length">Tube Length (L) [m]:</label>
  <input type="text" id="length" placeholder="Enter length">

  <button onclick="calculateFlowRate()">Calculate</button>

  <p id="result"></p>

</body></html>
