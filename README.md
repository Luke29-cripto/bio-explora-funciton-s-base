<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BioExplora</title>
  <link rel="stylesheet" href="style.css">
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      transition: background 0.3s, color 0.3s;
    }
    header {
      background-color: #28a745;
      color: white;
      padding: 1rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    nav ul {
      list-style: none;
      display: flex;
      gap: 1rem;
    }
    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
    }
    main {
      padding: 2rem;
    }
    .ranking-container {
      display: flex;
      gap: 2rem;
      flex-wrap: wrap;
    }
    .ranking {
      flex: 1;
      background: #f0f0f0;
      padding: 1rem;
      border-radius: 8px;
    }
    #searchInput {
      padding: 0.5rem;
      width: 60%;
      max-width: 400px;
      margin-bottom: 1rem;
    }
    #resultados li {
      margin: 0.5rem 0;
    }
    footer {
      text-align: center;
      padding: 1rem;
      background-color: #28a745;
      color: white;
    }
    .dark-mode {
      background: #121212;
      color: white;
    }
    .dark-mode .ranking {
      background: #1e1e1e;
    }
  </style>
</head>
<body>
  <header>
    <h1>BioExplora</h1>
    <nav>
      <ul>
        <li><a href="#home">Início</a></li>
        <li><a href="#rankings">Rankings</a></li>
        <li><a href="#busca">Buscar Vídeos</a></li>
        <li><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">Canal no YouTube</a></li>
      </ul>
      <button id="toggle-theme">🌙</button>
    </nav>
  </header>

  <main>
    <section id="home">
      <h2>Bem-vindo ao BioExplora!</h2>
      <p>O seu guia definitivo para explorar o mundo da Biologia com vídeos didáticos e interativos.</p>
      <p><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">Clique aqui para visitar nosso canal no YouTube 🎥</a></p>
    </section>

    <section id="rankings">
      <h2>Rankings do Mês</h2>
      <div class="ranking-container">
        <div class="ranking">
          <h3>Mais Pesquisados</h3>
          <ul id="mais-pesquisados">
            <li><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">DNA e RNA</a></li>
            <li><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">Fotossíntese</a></li>
            <li><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">Sistema Nervoso</a></li>
          </ul>
        </div>
        <div class="ranking">
          <h3>Mais Vistos</h3>
          <ul id="mais-vistos">
            <li><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">Genética Mendeliana</a></li>
            <li><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">Ecossistemas</a></li>
            <li><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">Mitose e Meiose</a></li>
          </ul>
        </div>
        <div class="ranking">
          <h3>Mais Completos</h3>
          <ul id="mais-completos">
            <li><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">Origem da Vida</a></li>
            <li><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">Imunologia</a></li>
            <li><a href="https://www.youtube.com/@ProfeJuoficial" target="_blank">Reino Animal</a></li>
          </ul>
        </div>
      </div>
    </section>

    <section id="busca">
      <h2>Buscar Vídeos</h2>
      <input type="text" id="searchInput" placeholder="Digite um tema ou palavra-chave...">
      <button onclick="buscarVideos()">Buscar</button>
      <ul id="resultados"></ul>
    </section>
  </main>

  <footer>
    <p>&copy; 2025 BioExplora. Todos os direitos reservados.</p>
  </footer>

  <script>
    const resultados = document.getElementById('resultados');
    const searchInput = document.getElementById('searchInput');
    const temas = [
      'Fotossíntese', 'Mitose', 'Meiose', 'DNA', 'RNA', 'Genética', 'Ecologia', 'Sustentabilidade'
    ];

    function buscarVideos() {
      const termo = searchInput.value.toLowerCase();
      resultados.innerHTML = '';
      const filtrados = temas.filter(t => t.toLowerCase().includes(termo));

      if (filtrados.length === 0) {
        resultados.innerHTML = '<li>Nenhum vídeo encontrado.</li>';
        return;
      }

      filtrados.forEach(t => {
        const li = document.createElement('li');
        const link = document.createElement('a');
        link.href = 'https://www.youtube.com/@ProfeJuoficial';
        link.target = '_blank';
        link.textContent = t;
        li.appendChild(link);
        resultados.appendChild(li);
      });
    }

    document.getElementById('toggle-theme').addEventListener('click', () => {
      document.body.classList.toggle('dark-mode');
    });
  </script>
</body>
</html>
