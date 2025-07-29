<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Segredo para Maria 💖</title>
  <style>
    html, body {
      height: 100%;
      margin: 0;
      background: linear-gradient(to bottom right, #ffe4e4, #f0f8ff);
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    #segredoBtn {
      padding: 16px 32px;
      font-size: 20px;
      border: none;
      background-color: #ff6f91;
      color: white;
      border-radius: 10px;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      transition: 0.3s;
    }

    #segredoBtn:hover {
      background-color: #ff3d6e;
    }

    #conteudo {
      display: none;
      flex-direction: column;
      align-items: center;
      margin-top: 20px;
    }

    h1 {
      font-size: 40px;
      color: #444;
      margin-bottom: 0;
    }

    .sub {
      font-size: 18px;
      color: #666;
      margin-top: 8px;
    }

    .hearts {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      z-index: -1;
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: pink;
      transform: rotate(45deg);
      animation: float 10s linear infinite;
      opacity: 0.6;
    }

    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: pink;
      border-radius: 50%;
    }

    .heart::before {
      top: -10px;
      left: 0;
    }

    .heart::after {
      left: -10px;
      top: 0;
    }

    @keyframes float {
      0% {
        transform: translateY(100vh) rotate(45deg);
        opacity: 0.6;
      }
      100% {
        transform: translateY(-10vh) rotate(45deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <!-- Botão inicial -->
  <button id="segredoBtn" onclick="mostrarSegredo()">Clique aqui para eu revelar um segredo</button>

  <!-- Conteúdo escondido -->
  <div id="conteudo">
    <h1>QUANDO VOCÊ ME ABRAÇA</h1>
    <div class="sub">o 🌎 gira devagar</div>
    <div class="hearts" id="hearts"></div>
  </div>

  <script>
    function mostrarSegredo() {
      document.getElementById('segredoBtn').style.display = 'none';
      const conteudo = document.getElementById('conteudo');
      conteudo.style.display = 'flex';

      const container = document.getElementById('hearts');
      for (let i = 0; i < 30; i++) {
        const heart = document.createElement('div');
        heart.classList.add('heart');
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = (5 + Math.random() * 5) + 's';
        container.appendChild(heart);
      }
    }
  </script>

</body>
</html>

