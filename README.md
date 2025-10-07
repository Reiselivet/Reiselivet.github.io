<!DOCTYPE html>
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
  overflow: hidden; /* Hindre scrolling før login */
}

/* Blur-effekt når man ikke er logget inn */
body.blurred #content {
  filter: blur(10px);
  pointer-events: none;
  user-select: none;
}

/* === Login-overlay === */
#login-overlay {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.6);
  backdrop-filter: blur(8px);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
}

#login-box {
  background: white;
  padding: 40px;
  border-radius: 20px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.4);
  text-align: center;
  width: 300px;
}

#login-box h2 {
  margin-bottom: 20px;
  color: #0A1F44;
}

#login-box input[type="password"] {
  width: 100%;
  padding: 10px;
  font-size: 1rem;
  border-radius: 8px;
  border: 1px solid #ccc;
  outline: none;
  margin-bottom: 15px;
}

#login-box button {
  background-color: #0A1F44;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: bold;
  transition: 0.3s;
}

#login-box button:hover {
  background-color: #122b63;
}

#login-error {
  color: red;
  font-size: 0.9rem;
  display: none;
  margin-top: 10px;
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
  color: #0A1F44;
  text-decoration: none;
  font-weight: 600;
}

/* Header-bilde */
.header-box {
  max-width: 900px;
  height: 400px;
  margin: 80px auto 50px auto;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  position: relative;
  transition: transform 0.3s;
}
.header-box:hover { transform: translateY(-5px); }
.header-box img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  border-radius: 20px;
}

/* Tekst over bilde */
.header-box .overlay-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: #fff;
  font-size: 3rem;
  font-weight: 700;
  text-transform: uppercase;
  text-shadow: 2px 2px 10px rgba(0,0,0,0.7);
  text-align: center;
}

/* Seksjoner */
section { padding: 60px 20px; max-width: 1200px; margin: 0 auto; }
.section-title { font-size: 2.5rem; margin-bottom: 1rem; text-align: center; color: #0A1F44; }
.section-subtitle { font-size: 1.1rem; text-align: center; margin-bottom: 2rem; color: #555; }

/* Bokser */
.boxes { display: flex; flex-wrap: wrap; gap: 30px; justify-content: center; margin-bottom: 60px; }
.box { background-color: #F7F3F0; padding: 30px; border-radius: 15px; flex: 1 1 250px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); text-align: center; transition: transform 0.3s; }
.box:hover { transform: translateY(-5px); }
.box h3 { margin-bottom: 15px; color: #0A1F44; }
.box p { color: #555; line-height: 1.6; }

/* Ansattkort */
.staff-cards { display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; }
.staff-card { background-color: #F7F3F0; border-radius: 10px; padding: 20px; flex: 1 1 200px; box-shadow: 0 4px 10px rgba(0,0,0,0.1); text-align: center; }
.staff-card h3 { margin-bottom: 5px; color: #0A1F44; }
.staff-card p { color: #555; }

/* Footer */
footer { background-color: #0A1F44; color: #fff; padding: 40px 20px; text-align: center; }
footer a { color: #D4AF37; margin: 0 10px; }
footer p { margin-top: 15px; font-size: 0.9rem; }

/* Responsivt */
@media(max-width: 900px) {
  nav { gap: 15px; }
  nav a { font-size: 0.9rem; }
  .boxes { flex-direction: column; }
  .header-box { height: 300px; margin-top: 70px; }
  .header-box .overlay-text { font-size: 2rem; }
}
</style>
</head>
<body class="blurred">

<!-- LOGIN OVERLAY -->
<div id="login-overlay">
  <div id="login-box">
    <h2>Logg inn</h2>
    <input type="password" id="password-input" placeholder="Skriv passord">
    <button id="login-btn">Logg inn</button>
    <div id="login-error">Feil passord. Prøv igjen.</div>
  </div>
</div>

<!-- Innhold -->
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

  <section id="info-bokser">
      <div class="boxes">
          <div class="box">
              <h3>Kundeservice</h3>
              <p>Vi legger stor vekt på profesjonell kundebehandling...</p>
          </div>
          <div class="box">
              <h3>Pris ved utreise</h3>
              <p>15.500 kr per person. Tillegg på 10.000 kr per hode...</p>
          </div>
          <div class="box">
              <h3>Reisen</h3>
              <p>Vi seiler til Mallorca med yacht, og fokuserer på komfort...</p>
          </div>
      </div>
  </section>

  <section id="ansatte">
      <h2 class="section-title">Vårt team</h2>
      <div class="staff-cards">
          <div class="staff-card"><h3>Jonathan Pettersen</h3><p>Eier</p></div>
          <div class="staff-card"><h3>Vidar Holte</h3><p>Lærling</p></div>
          <div class="staff-card"><h3>Patrick Ryen</h3><p>Lærling</p></div>
          <div class="staff-card"><h3>Patrik Svensson</h3><p>Lærling</p></div>
      </div>
  </section>

  <footer>
      <p>Kontakt oss: <a href="mailto:kontakt@reiseliv.no">kontakt@reiseliv.no</a></p>
      <p><a href="#">Facebook</a> | <a href="#">Instagram</a> | <a href="#">LinkedIn</a></p>
      <p>&copy; 2025 Reiselivet. Alle rettigheter reservert.</p>
  </footer>
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

// Forby F12 og høyreklikk
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
