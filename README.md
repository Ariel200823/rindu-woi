<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Happy Birthday Niar</title>
  <style>
    body {
      margin: 0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background-color: black;
      color: pink;
      overflow: hidden;
    }

    .container {
      text-align: center;
      padding-top: 20vh;
    }

    h1 {
      color: pink;
      font-size: 3em;
    }

    button {
      padding: 12px 24px;
      font-size: 1.2em;
      background-color: #ff80bf;
      color: white;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      transition: background 0.3s;
    }

    button:hover {
      background-color: #ff4da6;
    }

    .flowers {
      position: absolute;
      inset: 0;
      background: url('https://i.imgur.com/Qw7npIg.png') repeat center center;
      background-size: 100px;
      animation: bloom 3s ease-in-out forwards;
      display: none;
    }

    .grass {
      position: absolute;
      bottom: 0;
      width: 100%;
      height: 100px;
      background: url('https://i.imgur.com/yXfBYsZ.png') repeat-x;
      background-size: contain;
    }

    .petal {
      position: absolute;
      width: 20px;
      height: 20px;
      background: url('https://i.imgur.com/nYQX0vL.png') no-repeat;
      background-size: cover;
      animation: fall 8s linear infinite;
      opacity: 0.8;
    }

    @keyframes bloom {
      from {opacity: 0;}
      to {opacity: 1;}
    }

    @keyframes fall {
      0% {
        transform: translateY(-100px) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(100vh) rotate(360deg);
        opacity: 0;
      }
    }

    audio {
      display: none;
    }
  </style>
</head>
<body>
  <div class="container" id="main">
    <h1>HAPPY BIRTHDAY NIAR</h1>
    <button onclick="showFlowers()">TEKAN AKU</button>
  </div>

  <div class="flowers" id="flowers">
    <div class="grass"></div>
    <audio id="music" autoplay loop>
      <source src="https://dl.sndup.net/k9tw/Raim%20Laode%20-%20Lesung%20Pipi.mp3" type="audio/mpeg">
    </audio>
  </div>

  <script>
    function showFlowers() {
      document.getElementById('main').style.display = 'none';
      const flowers = document.getElementById('flowers');
      flowers.style.display = 'block';
      document.getElementById('music').play();

      for (let i = 0; i < 30; i++) {
        const petal = document.createElement('div');
        petal.classList.add('petal');
        petal.style.left = Math.random() * window.innerWidth + 'px';
        petal.style.animationDelay = (Math.random() * 5) + 's';
        petal.style.width = (10 + Math.random() * 20) + 'px';
        petal.style.height = petal.style.width;
        flowers.appendChild(petal);
      }
    }
  </script>
</body>
</html>
