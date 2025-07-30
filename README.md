<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Último Dia</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      background-color: #f0f0f0;
      font-family: Arial, sans-serif;
    }
    #container {
      text-align: center;
      background-color: #fff;
      padding: 40px;
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
    }
    #title {
      font-size: 48px;
      color: #ff4444;
      margin-bottom: 20px;
      font-weight: bold;
      text-transform: uppercase;
    }
    #timer {
      font-size: 72px;
      color: #333;
      font-weight: bold;
    }
    .time-unit {
      display: inline-block;
      margin: 0 15px;
    }
    .label {
      font-size: 24px;
      color: #666;
    }
  </style>
</head>
  
<body>
  <div id="container">
    <div id="title">O ÚLTIMO DIA DE SOFRIMENTO</div>
    <div id="timer">
      <span class="time-unit"><span id="days">00</span><br><span class="label">Dias</span></span>
      <span class="time-unit"><span id="hours">00</span><br><span class="label">Horas</span></span>
      <span class="time-unit"><span id="minutes">00</span><br><span class="label">Minutos</span></span>
      <span class="time-unit"><span id="seconds">00</span><br><span class="label">Segundos</span></span>
    </div>
  </div>
  
  <script>
    const endDate = new Date('2025-08-28T00:00:00-03:00');

    function updateTimer() {
      const now = new Date();
      const timeLeft = endDate - now;

      if (timeLeft <= 0) {
        document.getElementById('days').innerText = '00';
        document.getElementById('hours').innerText = '00';
        document.getElementById('minutes').innerText = '00';
        document.getElementById('seconds').innerText = '00';
        return;
      }

      const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
      const hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

      document.getElementById('days').innerText = days.toString().padStart(2, '0');
      document.getElementById('hours').innerText = hours.toString().padStart(2, '0');
      document.getElementById('minutes').innerText = minutes.toString().padStart(2, '0');
      document.getElementById('seconds').innerText = seconds.toString().padStart(2, '0');
    }

    setInterval(updateTimer, 1000);

    updateTimer();
  </script>
</body>
</html>
