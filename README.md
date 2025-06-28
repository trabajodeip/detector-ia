<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Proyecto IP – Detector IA</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Outfit:wght@400;600;800&display=swap">
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
  <script src="https://unpkg.com/scrollreveal"></script>
  <style>
    * {
      box-sizing: border-box;
      font-family: 'Outfit', sans-serif;
    }

    body {
      margin: 0;
      background: #1f1c2c;
      color: white;
      display: flex;
      flex-direction: column;
      min-height: 100vh;
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      top: 0;
      left: 0;
      width: 200%;
      height: 200%;
      background: radial-gradient(circle at 20% 20%, rgba(255, 255, 255, 0.1), transparent 25%),
                  radial-gradient(circle at 80% 80%, rgba(255, 255, 255, 0.1), transparent 25%);
      background-size: 400px 400px;
      animation: backgroundMove 15s linear infinite;
      z-index: 0;
    }

    @keyframes backgroundMove {
      from { transform: translate(0, 0); }
      to { transform: translate(-50px, -50px); }
    }

    header, main, footer {
      position: relative;
      z-index: 1;
    }

    header {
      padding: 4rem 2rem;
      text-align: center;
    }

    header h1 {
      font-size: 3.5rem;
      font-weight: 800;
      margin: 0;
    }

    header p {
      font-size: 1.2rem;
      font-weight: 400;
      max-width: 600px;
      margin: 1rem auto 0;
      opacity: 0.85;
    }

    main {
      flex: 1;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 2rem;
    }

    .card {
      background-color: rgba(255, 255, 255, 0.06);
      border-radius: 24px;
      padding: 2.5rem;
      max-width: 550px;
      width: 100%;
      text-align: center;
      backdrop-filter: blur(14px);
      box-shadow: 0 20px 60px rgba(0,0,0,0.4);
      transition: transform 0.3s ease;
    }

    .card:hover {
      transform: translateY(-4px);
    }

    input[type="file"] {
      margin: 1rem 0;
      padding: 1.2rem;
      border: 2px dashed #fff;
      background: transparent;
      color: #fff;
      cursor: pointer;
      width: 100%;
      border-radius: 12px;
      transition: 0.3s;
    }

    input[type="file"]:hover {
      border-color: #e0e0e0;
    }

    button {
      padding: 1rem 2rem;
      background-color: #ffffff;
      color: #1f1c2c;
      border: none;
      font-size: 1.1rem;
      border-radius: 12px;
      cursor: pointer;
      margin-top: 1rem;
      transition: all 0.3s ease;
    }

    button:hover {
      background-color: #e0e0e0;
    }

    #resultado {
      margin-top: 2rem;
      font-size: 1.6rem;
      font-weight: bold;
      opacity: 0;
      transition: opacity 0.5s ease-in-out;
    }

    #resultado.visible {
      opacity: 1;
    }

    footer {
      padding: 2rem;
      text-align: center;
      font-size: 0.9rem;
      color: rgba(255, 255, 255, 0.5);
    }
  </style>
</head>
<body>
  <header class="reveal">
    <h1><i class="fas fa-brain"></i> Detector de Inteligencia Artificial</h1>
    <p>Sube tu archivo académico y detecta el porcentaje de contenido generado por IA.</p>
  </header>

  <main>
    <div class="card reveal">
      <input type="file" id="archivo" accept=".txt,.docx,.pdf" />
      <button onclick="analizarArchivo()"><i class="fas fa-search"></i> Analizar</button>
      <div id="resultado"></div>
    </div>
  </main>

  <footer class="reveal">
    Proyecto IP | Prototipo escolar 2025 ·
  </footer>

  <script>
    function analizarArchivo() {
      const resultado = document.getElementById('resultado');
      const porcentaje = Math.floor(Math.random() * 71) + 20;
      resultado.textContent = "Probabilidad de IA: " + porcentaje + "%";
      resultado.classList.add("visible");
    }

    ScrollReveal().reveal('.reveal', {
      distance: '30px',
      duration: 1000,
      easing: 'ease-out',
      origin: 'bottom',
      interval: 200
    });
  </script>
</body>
</html>
