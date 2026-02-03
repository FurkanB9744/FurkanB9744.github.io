<html lang="de">
<head>
  <meta charset="UTF-8">
  <title>Countdown</title>
  <style>
    body {
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: system-ui, sans-serif;
      font-size: 3rem;
    }
  </style>
</head>
<body>
  <div id="counter"></div>

  <script>
    const target = new Date("2026-06-22T00:00:00").getTime();

    function update() {
      const now = Date.now();
      const diff = target - now;

      if (diff <= 0) {
        document.getElementById("counter").textContent = "Es ist soweit 🎉";
        return;
      }

      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((diff / (1000 * 60)) % 60);
      const seconds = Math.floor((diff / 1000) % 60);

      document.getElementById("counter").textContent =
        `${days} Tage ${hours}h ${minutes}m ${seconds}s`;
    }

    update();
    setInterval(update, 1000);
  </script>
</body>
</html>
