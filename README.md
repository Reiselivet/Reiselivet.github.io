<!DOCTYPE html>
<html lang="no">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Reiselivet</title>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&family=Poppins:wght@400;500;600&display=swap" rel="stylesheet">
<style>
/* --- Felles body --- */
body {
  font-family: 'Roboto', sans-serif;
  color: #0A1F44;
  margin: 0;
  background: linear-gradient(135deg, #f9f9f9 0%, #e8ebef 100%);
}

/* --- Meny --- */
nav {
  position: sticky;
  top: 0;
  width: 100%;
  background: rgba(255,255,255,0.3);
  backdrop-filter: blur(10px);
  display: flex;
  justify-content: center;
  gap: 30px;
  padding: 15px 0;
  z-index: 100;
  font-weight: 600;
}
nav a {
  color: #0A1F44;
  text-decoration: none;
  font-size: 1.1rem;
  transition: color 0.3s;
}
nav a:hover {
  color: #D4AF37;
}

/* --- Hjem seksjon --- */
.header-box {
  max-width: 900px;
  height: 400px;
  margin: 50px auto;
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
  border-radius: 20px;
}
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
section { padding: 60px 20px; max-width: 1200px; margin: 0 auto; }
.section-title { font-size: 2.5rem; margin-bottom: 1rem; text-align: center; color: #0A1F44; }
.section-subtitle { font-size: 1.1rem; text-align: center; margin-bottom: 2rem; color: #555; }
.boxes { display: flex; flex-wrap: wrap; gap: 30px; justify-content: center; margin-bottom: 60px; }
.box { background-color: #F7F3F0; padding: 30px; border-radius: 15px; flex: 1 1 250px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); text-align: center; transition: transform 0.3s; }
.box:hover { transform: translateY(-5px); }
.box h3 { margin-bottom: 15px; color: #0A1F44; }
.box p { color: #555; line-height: 1.6; }
.staff-cards { display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; }
.staff-card { background-color: #F7F3F0; border-radius: 10px; padding: 20px; flex: 1 1 200px; box-shadow: 0 4px 10px rgba(0,0,0,0.1); text-align: center; }
.staff-card h3 { margin-bottom: 5px; color: #0A1F44; }
.staff-card p { color: #555; }
footer { background-color: #0A1F44; color: #fff; padding: 40px 20px; text-align: center; }
footer a { color: #D4AF37; margin: 0 10px; }
footer p { margin-top: 15px; font-size: 0.9rem; }
@media(max-width: 900px) {
  .boxes { flex-direction: column; }
  .header-box { height: 300px; }
  .header-box .overlay-text { font-size: 2rem; }
}

/* --- Report seksjon --- */
#report, #subscription { display: none; }
:root {
  --gold: #f1c40f;
  --green: #2ecc71;
  --blue: #3498db;
  --white-glass: rgba(255,255,255,0.75);
}
#report header { background: none; text-align: center; font-weight: 600; font-size: 1.8em; margin-top: 1em; }
.form-card { background: var(--white-glass); backdrop-filter: blur(10px); border-radius: 16px; box-shadow: 0 4px 30px rgba(0,0,0,0.1); padding: 2em; width: 100%; max-width: 700px; margin-bottom: 2em; transition: all 0.3s ease; }
.form-card:hover { transform: translateY(-2px); }
.form-card h2 { text-align: center; color: #555; font-weight: 500; margin-bottom: 1em; }
label { display: block; margin: 0.7em 0 0.3em; font-size: 0.9em; color: #333; }
input, button { width: 100%; padding: 0.8em; border: none; border-radius: 10px; font-size: 1em; }
input { background: rgba(255,255,255,0.8); border: 1px solid #ccc; }
button { background: linear-gradient(135deg, var(--gold), #f39c12); color: #000; font-weight: bold; margin-top: 1em; cursor: pointer; transition: 0.3s; }
button:hover { transform: scale(1.03); }
table { width: 100%; border-collapse: collapse; margin-top: 2em; background: rgba(255,255,255,0.85); border-radius: 16px; overflow: hidden; box-shadow: 0 4px 20px rgba(0,0,0,0.1); }
th, td { padding: 0.8em 1em; text-align: left; }
th { background: rgba(240,240,240,0.8); font-weight: 500; color: #555; }
td { border-bottom: 1px solid rgba(0,0,0,0.05); }
.status { padding: 0.5em 1em; border-radius: 8px; font-size: 0.9em; font-weight: 600; display: inline-block; cursor: pointer; text-align: center; min-width: 100px; transition: 0.3s; margin: 0.2em; box-shadow: 0 2px 6px rgba(0,0,0,0.1); }
.status.Levert { background: linear-gradient(135deg, var(--green), #27ae60); color: white; }
.status.Hentet { background: linear-gradient(135deg, var(--blue), #2980b9); color: white; }
.status["Utsatt tid"], .status.Utsatt, .status.Utsatt\ tid { background: linear-gradient(135deg, var(--gold), #e1b12c); color: black; border: 1px solid #d4ac0d; }
.modal { display: none; position: fixed; z-index: 10; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.4); justify-content: center; align-items: center; }
.modal-content { background: white; padding: 2em; border-radius: 12px; box-shadow: 0 4px 20px rgba(0,0,0,0.3); max-width: 320px; width: 90%; text-align: center; }
.modal-content h3 { margin-bottom: 1em; color: #333; }
.modal-content input { margin-bottom: 1em; }
.modal-content button { margin-top: 0.5em; }

/* --- Subscription seksjon --- */
:root {
  --bg: #1e1e1e;
  --card: #2a2a2a;
  --text: #ffffff;
  --accent: #00d0ff;
  --expired: #ff4c4c;
  --font: 'Segoe UI', sans-serif;
}
#subscription {
  color: var(--text);
  background-color: var(--bg);
  padding: 30px;
  min-height: 100vh;
}
#subscription h1, #subscription h2 { color: var(--accent); }
#subscription .container { max-width: 900px; margin: 0 auto; }
#subscription form { background-color: var(--card); padding: 20px; border-radius: 10px; margin-bottom: 30px; box-shadow: 0 0 10px rgba(0,0,0,0.4); }
#subscription label { display: block; margin-top: 15px; }
#subscription input { width: 100%; max-width: 400px; padding: 10px; border: none; border-radius: 5px; margin-top: 5px; background-color: #444; color: #fff; }
#subscription button { margin-top: 20px; padding: 12px 25px; border: none; border-radius: 5px; background-color: var(--accent); color: #000; font-weight: bold; cursor: pointer; transition: background 0.3s; }
#subscription button:hover { background-color: #00b8e0; }
#subscription table { width: 100%; border-collapse: collapse; margin-top: 10px; }
#subscription th, #subscription td { padding: 12px; border-bottom: 1px solid #444; }
#subscription th { background-color: #333; text-align: left; }
#subscription tr.expired { background-color: #3a1c1c; color: var(--expired); }
#subscription .section { background-color: var(--card); padding: 20px; border-radius: 10px; margin-bottom: 40px; box-shadow: 0 0 10px rgba(0,0,0,0.4); }

</style>
</head>
<body>

<!-- Meny -->
<nav>
  <a href="#" onclick="showSection('home')">Hjem</a>
  <a href="#" onclick="showSection('report')">Report</a>
  <a href="#" onclick="showSection('subscription')">Abonnement</a>
</nav>

<!-- Hjem -->
<div id="home">
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
              <p>15.500 kr per person...</p>
          </div>
          <div class="box">
              <h3>Reisen</h3>
              <p>Vi seiler til Mallorca med yacht...</p>
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
</div>

<!-- Report -->
<div id="report">
  <header>Reiselivet</header>
  <main>
    <div class="form-card">
      <h2>📝 Ny Rapport</h2>
      <form id="reportForm">
        <label>Navn:</label><input type="text" id="nameInput" required>
        <label>Dato:</label><input type="date" id="dateInput" required>
        <label>Hentetid:</label><input type="time" id="timeInput" required>
        <label>Antall personer:</label><input type="number" id="personsInput" min="1" required>
        <button type="submit">📦 Lagre Rapport</button>
      </form>
    </div>
    <table id="reportTable">
      <thead>
        <tr>
          <th>Navn</th><th>Dato</th><th>Oppr. tid</th><th>Ny tid</th><th>Antall</th><th>Status</th>
        </tr>
      </thead>
      <tbody></tbody>
    </table>
  </main>
  <div id="timeModal" class="modal">
    <div class="modal-content">
      <h3>Sett ny hentetid</h3>
      <input type="time" id="newTimeInput">
      <button id="saveTimeBtn">Lagre</button>
      <button id="cancelTimeBtn">Avbryt</button>
    </div>
  </div>
</div>

<!-- Subscription -->
<div id="subscription">
  <div class="container">
    <h1>Abonnementsoversikt</h1>
    <form id="subscriptionForm">
      <label>Navn:<input type="text" id="subName" required></label>
      <label>Telefon:<input type="tel" id="phone" required></label>
      <label>Startdato:<input type="date" id="start" required></label>
      <label>Utløpsdato:<input type="date" id="expiry" required></label>
      <button type="submit">Legg til abonnement</button>
    </form>

    <div class="section">
      <h2>🟢 Aktive abonnementer</h2>
      <table id="activeTable"><thead><tr><th>Navn</th><th>Telefon</th><th>Startdato</th><th>Kode</th><th>Utløpsdato</th></tr></thead><tbody></tbody></table>
    </div>

    <div class="section">
      <h2>🔴 Utløpte abonnementer</h2>
      <table id="expiredTable"><thead><tr><th>Navn</th><th>Telefon</th><th>Startdato</th><th>Kode</th><th>Utløpsdato</th></tr></thead><tbody></tbody></table>
    </div>
  </div>
</div>

<footer>
  <p>Kontakt oss: <a href="mailto:kontakt@reiseliv.no">kontakt@reiseliv.no</a></p>
  <p><a href="#">Facebook</a> | <a href="#">Instagram</a> | <a href="#">LinkedIn</a></p>
  <p>&copy; 2025 Reiselivet. Alle rettigheter reservert.</p>
</footer>

<script>
/* --- Seksjonsbytte --- */
function showSection(section) {
  document.getElementById('home').style.display = 'none';
  document.getElementById('report').style.display = 'none';
  document.getElementById('subscription').style.display = 'none';
  document.getElementById(section).style.display = 'block';
}

/* --- Report logikk --- */
const STORAGE_KEY = "reiselivet_reports_v4";
let reports = JSON.parse(localStorage.getItem(STORAGE_KEY) || "[]");
let currentIndex = null;

function saveReports() { localStorage.setItem(STORAGE_KEY, JSON.stringify(reports)); }
function renderTable() {
  const tbody = document.querySelector("#reportTable tbody");
  tbody.innerHTML = "";
  reports.forEach((r,i)=>{
    const tr=document.createElement("tr");
    tr.innerHTML=`<td>${r.name}</td><td>${r.date}</td><td>${r.originalTime}</td><td>${r.newTime||"-"}</td><td>${r.persons}</td><td><span class="status ${r.status}" onclick="cycleStatus(${i})">${r.status}</span></td>`;
    tbody.appendChild(tr);
  });
}
function cycleStatus(i){
  const order=["Levert","Hentet","Utsatt tid"];
  let current=reports[i].status;
  let next=order[(order.indexOf(current)+1)%order.length];
  reports[i].status=next;
  saveReports();
  renderTable();
  if(next==="Utsatt tid"){
    currentIndex=i;
    document.getElementById("newTimeInput").value=reports[i].newTime||reports[i].originalTime||"";
    document.getElementById("timeModal").style.display="flex";
  }
}
document.getElementById("saveTimeBtn").onclick=()=>{
  const newTime=document.getElementById("newTimeInput").value;
  if(newTime && currentIndex!==null){ reports[currentIndex].newTime=newTime; saveReports(); render
