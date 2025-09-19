<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Random Background Color</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 50px;
      transition: background-color 0.5s ease;
    }

    button {
      padding: 10px 20px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background: #1c77a7;
      color: white;
    }

    button:hover {
      background: #023e8a;
    }
  </style>
</head>
<body>
  <h1>Click the Button to Change Background Color</h1>
  <button id="colorBtn">Change Color</button>

  <script>
    // Function to generate random hex color
    function getRandomColor() {
      const letters = "0123456789ABCDEF";
      let color = "#";
      for (let i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)];
      }
      return color;
    }

    // Add event listener to button
    document.getElementById("colorBtn").addEventListener("click", function() {
      document.body.style.backgroundColor = getRandomColor();
    });
  </script>
</body>
</html>
