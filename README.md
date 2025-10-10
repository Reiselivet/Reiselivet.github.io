<html lang="no">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Reiselivet</title>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&family=Poppins:wght@400;500;600&display=swap" rel="stylesheet">
<style>
body {
  font-family: 'Roboto', sans-serif;
  color: #0A1F44;
  margin: 0;
  background: linear-gradient(135deg, #f9f9f9 0%, #e8ebef 100%);
  overflow: hidden;
}

body.blurred #content {
  filter: blur(10px);
  pointer-events: none;
  user-select: none;
}

/* === LOGO I VENSTRE HJØRNE === */
.logo {
  position: fixed;
  top: 10px;
  left: 15px;
  z-index: 10000;
}
.logo img {
  height: 55px;
  width: auto;
  border-radius: 10px;
  transition: transform 0.3s ease;
}
.logo img:hover {
  transform: scale(1.05);
}

/* === Navigasjonsmeny === */
nav {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 40px;
  z-index: 10;
  padding: 15px 0;
  background: transparent;
}

nav a {
  color: #87CEFA;
  text-decoration: none;
  font-weight: 600;
  font-size: 18px;
  transition: 0.3s;
}

nav a:hover {
  color: #fff;
}

/* Resten av CSS er uendret ... */
</style>
</head>
<body class="blurred">

<!-- === LOGOEN === -->
<div class="logo">
  <a href="https://reiselivet.github.io/">
    <img src="https://gyazo.com/78c7c978455675e1ccd20f040331d08f/raw" alt="Reiselivet logo">
  </a>
</div>

<!-- LOGIN OVERLAY -->
<div id="login-overlay">
  <div id="login-box">
    <h2>Logg inn</h2>
    <input type="password" id="password-input" placeholder="Skriv passord">
    <button id="login-btn">Logg inn</button>
    <div id="login-error">Feil passord. Prøv igjen.</div>
  </div>
</div>

<!-- INNHOLD -->
<div id="content">
  <nav>
    <a href="https://reiselivet.github.io/">Hjem</a>
    <a href="https://reiselivet.github.io/Report.html">Report</a>
    <a href="https://reiselivet.github.io/Abonnement.html">Abonnement</a>
  </nav>

  <div class="header-box">
    <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=1470&q=80" alt="Yacht">
    <div class="overlay-text">Reiselivet</div>
  </div>

  <!-- resten av HTML-en er uendret -->
</div>

<script>
document.getElementById('login-btn').addEventListener('click', () => {
  const pass = document.getElementById('password-input').value.trim();
  const correctPass = 'reiselivet2182';
  const error = document.getElementById('login-error');
  
  if (pass === correctPass) {
    document.getElementById('login-overlay').style.display = 'none';
    document.body.classList.remove('blurred');
    document.body.style.overflow = 'auto';
  } else {
    error.style.display = 'block';
  }
});

document.addEventListener('contextmenu', e => e.preventDefault());
document.onkeydown = function(e) {
  if (e.key === "F12" || 
      (e.ctrlKey && e.shiftKey && (e.key === "I" || e.key === "J")) || 
      (e.ctrlKey && e.key === "U")) {
    e.preventDefault();
    return false;
  }
};
</script>
</body>
</html>
