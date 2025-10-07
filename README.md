<!DOCTYPE html>
<html lang="no">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Reiselivet</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
<style>
body {
  font-family: 'Poppins', sans-serif;
  color: #0A1F44;
  margin: 0;
  background: linear-gradient(135deg, #f9f9f9 0%, #e8ebef 100%);
  margin-top: 90px;
}

/* --- Premium transparent meny --- */
nav {
  position: fixed;
  top: 0;
  width: 100%;
  background: rgba(255,255,255,0.2);
  backdrop-filter: blur(10px);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.7em 2em;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  z-index: 100;
}
nav .logo img {
  height: 55px;
  border-radius: 10px;
}
nav ul {
  list-style: none;
  display: flex;
  gap: 2em;
  margin: 0;
  padding: 0;
}
nav ul li a {
  text-decoration: none;
  color: #fff;
  font-weight: 600;
  font-size: 1.1em;
  transition: color 0.3s, transform 0.3s;
}
nav ul li a:hover {
  color: #D4AF37;
  transform: translateY(-2px);
}

/* --- Hovedinnhold --- */
.header-box {
  max-width: 900px;
  height: 400px;
  margin: 50px auto;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  position: relative;
}
.header-box img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.overlay-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: #fff;
  font-size: 3rem;
  font-weight: 700;
  text-shadow: 2px 2px 10px rgba(0,0,0,0.7);
}
section { max-width: 1100px; margin: 0 auto; padding: 60px 20px; text-align: center; }
footer { background: #0A1F44; color: #fff; text-align: center; padding: 30px; }
</style>
</head>
<body>

<nav>
  <div class="logo">
    <a href="https://reiselivet.github.io">
      <img src="ChatGPT Image 7. okt. 2025, 01_09_14-2.png" alt="Logo">
    </a>
  </div>
  <ul>
    <li><a href="https://reiselivet.github.io">Hjem</a></li>
    <li><a href="https://reiselivet.github.io/Report.html">Raport</a></li>
    <li><a href="https://reiselivet.github.io/Abonnement.html">Abonnement</a></li>
  </ul>
</nav>

<div class="header-box">
  <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=1470&q=80" alt="">
  <div class="overlay-text">Reiselivet</div>
</div>

<section>
  <h2>Velkommen til Reiselivet</h2>
  <p>Eksklusive reiser, solfylte opplevelser og uforglemmelige minner.</p>
</section>

<footer>
  &copy; 2025 Reiselivet. Alle rettigheter reservert.
</footer>
</body>
</html>
