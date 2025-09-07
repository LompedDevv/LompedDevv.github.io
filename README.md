<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Portfólio - LompedDevv</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #6a11cb, #2575fc);
      color: white;
      text-align: center;
    }

    header {
      padding: 20px;
      background: rgba(0,0,0,0.3);
      border-radius: 0 0 20px 20px;
    }

    nav button {
      background: rgba(255,255,255,0.1);
      border: none;
      padding: 12px 20px;
      margin: 5px;
      border-radius: 12px;
      color: white;
      font-size: 16px;
      cursor: pointer;
      transition: 0.3s;
    }

    nav button:hover {
      background: rgba(255,255,255,0.3);
      transform: scale(1.05);
    }

    .tab {
      display: none;
      padding: 20px;
      animation: fade 0.6s;
    }

    .tab.active {
      display: block;
    }

    .card {
      background: rgba(0,0,0,0.4);
      margin: 20px auto;
      padding: 20px;
      border-radius: 20px;
      max-width: 800px;
      transition: transform 0.3s;
    }

    .card:hover {
      transform: scale(1.03);
    }

    img {
      max-width: 100%;
      border-radius: 15px;
    }

    @keyframes fade {
      from {opacity: 0;}
      to {opacity: 1;}
    }
  </style>
</head>
<body>

<header>
  <h1>💻 LompedDevv</h1>
  <p>Developer de Roblox Studio | 🚀 1B+ Visitas Contribuídas</p>
  <nav>
    <button onclick="showTab('descricao')">Descrição</button>
    <button onclick="showTab('perfis')">Perfis</button>
    <button onclick="showTab('trabalhos')">Locais já trabalhados</button>
  </nav>
</header>

<section id="descricao" class="tab active">
  <div class="card">
    <h2>🌟 Sobre mim</h2>
    <p>Sou LompedDevv, um Developer de Roblox Studio com mais de 1 bilhão de visitas contribuídas.</p>
  </div>
</section>

<section id="perfis" class="tab">
  <div class="card">
    <h2>📫 Contatos</h2>
    <p>💬 Discord: <strong>lompedd</strong></p>
    <p>🎮 Roblox: <a href="https://www.roblox.com/users/0000000/profile" style="color:yellow;">LompedDevv</a></p>
  </div>
</section>

<section id="trabalhos" class="tab">
  <div class="card">
    <h2>🐾 Pet Simulator X</h2>
    <img src="Roblox-Pet-Simulator-99-Codigos-de-itens-gratis-Outubro-2024-1-696x348.jpg">
  </div>

  <div class="card">
    <h2>🎾 Tennis: Zero</h2>
    <img src="kgnH66mnZETAzXKtX3z4yD.jpg">
  </div>

  <div class="card">
    <h2>⚽ Soccer: Zero (In Dev)</h2>
    <img src="hq720 (1).jpg">
  </div>

  <div class="card">
    <h2>🔥 Mugen</h2>
    <p>Imagem em breve...</p>
  </div>
</section>

<script>
function showTab(tabId) {
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.getElementById(tabId).classList.add('active');
}
</script>

</body>
</html>

