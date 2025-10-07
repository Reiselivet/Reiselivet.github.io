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
  background: transparent; /* Gjennomsiktig */
}

nav a {
  color: #0A1F44; /* Blå tekst */
  text-decoration: none;
  font-weight: 600;
  padding: 0;
  border-radius: 0;
  background: transparent;
  transition: none; /* Ingen hover-effekt */
}

/* Header-bilde */
.header-box {
    max-width: 900px;
    height: 400px;
    margin: 80px auto 50px auto; /* plass til meny */
    border-radius: 20px;
    overflow: hidden;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    position: relative;
    transition: transform 0.3s;
}
.header-box:hover {
    transform: translateY(-5px);
}
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
<body>

<!-- Navigasjonsmeny -->
<nav>
  <a href="https://reiselivet.github.io/">Hjem</a>
  <a href="https://reiselivet.github.io/Report.html">Report</a>
  <a href="https://reiselivet.github.io/Abonnement.html">Abonnement</a>
</nav>

<!-- Header-bilde -->
<div class="header-box">
    <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=1470&q=80" alt="Yacht">
    <div class="overlay-text">Reiselivet</div>
</div>

<!-- Boks seksjon -->
<section id="info-bokser">
    <div class="boxes">
        <div class="box">
            <h3>Kundeservice</h3>
            <p>Vi legger stor vekt på profesjonell kundebehandling. Våre ansatte er alltid tilgjengelige, høflige og klar til å sikre at reisen blir en uforglemmelig opplevelse.</p>
        </div>
        <div class="box">
            <h3>Pris ved utreise</h3>
            <p>15.500 kr per person. Tillegg på 10.000 kr per hode for ekstra tjenester. Vi gir full oversikt før reisen starter.</p>
        </div>
        <div class="box">
            <h3>Reisen</h3>
            <p>Vi seiler til Mallorca med yacht, og fokuserer på komfort, sikkerhet og uforglemmelige opplevelser underveis. Nyt solen, sjøen og eksklusive aktiviteter!</p>
        </div>
    </div>
</section>

<!-- Ansattliste -->
<section id="ansatte">
    <h2 class="section-title">Vårt team</h2>
    <div class="staff-cards">
        <div class="staff-card">
            <h3>Jonathan Pettersen</h3>
            <p>Eier</p>
        </div>
        <div class="staff-card">
            <h3>Vidar Holte</h3>
            <p>Lærling</p>
        </div>
        <div class="staff-card">
            <h3>Patrick Ryen</h3>
            <p>Lærling</p>
        </div>
        <div class="staff-card">
            <h3>Patrik Svensson</h3>
            <p>Lærling</p>
        </div>
    </div>
</section>

<!-- Footer -->
<footer>
    <p>Kontakt oss: <a href="mailto:kontakt@reiseliv.no">kontakt@reiseliv.no</a></p>
    <p><a href="#">Facebook</a> | <a href="#">Instagram</a> | <a href="#">LinkedIn</a></p>
    <p>&copy; 2025 Reiselivet. Alle rettigheter reservert.</p>
</footer>

</body>
</html>
