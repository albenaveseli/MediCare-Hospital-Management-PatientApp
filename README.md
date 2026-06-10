<!DOCTYPE html>
<html lang="sq">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>MediCare – README</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg: #0d1117;
      --surface: #161b22;
      --surface2: #1c2230;
      --border: #21262d;
      --accent: #2dd4bf;
      --accent-dim: rgba(45,212,191,0.12);
      --accent2: #818cf8;
      --accent2-dim: rgba(129,140,248,0.1);
      --red: #f87171;
      --red-dim: rgba(248,113,113,0.1);
      --green: #34d399;
      --green-dim: rgba(52,211,153,0.1);
      --yellow: #fbbf24;
      --text: #e6edf3;
      --text-muted: #7d8590;
      --text-dim: #4d5566;
      --radius: 10px;
      --radius-sm: 6px;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Inter', sans-serif;
      font-size: 15px;
      line-height: 1.7;
      min-height: 100vh;
    }

    /* HEADER */
    .header {
      background: linear-gradient(135deg, #0d1117 0%, #0f1c2e 60%, #0d1117 100%);
      border-bottom: 1px solid var(--border);
      padding: 64px 0 56px;
      position: relative;
      overflow: hidden;
    }

    .header::before {
      content: '';
      position: absolute;
      top: -80px; left: -80px;
      width: 400px; height: 400px;
      background: radial-gradient(circle, rgba(45,212,191,0.07) 0%, transparent 70%);
      pointer-events: none;
    }
    .header::after {
      content: '';
      position: absolute;
      bottom: -60px; right: -60px;
      width: 360px; height: 360px;
      background: radial-gradient(circle, rgba(129,140,248,0.07) 0%, transparent 70%);
      pointer-events: none;
    }

    .header-inner {
      max-width: 900px;
      margin: 0 auto;
      padding: 0 32px;
      position: relative;
      z-index: 1;
    }

    .badge-row {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
      margin-bottom: 24px;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 4px 12px;
      border-radius: 20px;
      font-size: 12px;
      font-weight: 500;
      letter-spacing: 0.3px;
    }
    .badge-teal  { background: var(--accent-dim); color: var(--accent); border: 1px solid rgba(45,212,191,0.25); }
    .badge-indigo{ background: var(--accent2-dim); color: var(--accent2); border: 1px solid rgba(129,140,248,0.25); }
    .badge-yellow{ background: rgba(251,191,36,0.1); color: var(--yellow); border: 1px solid rgba(251,191,36,0.25); }

    .header h1 {
      font-size: 48px;
      font-weight: 700;
      letter-spacing: -1.5px;
      line-height: 1.1;
      margin-bottom: 16px;
    }

    .header h1 span.accent { color: var(--accent); }

    .header .subtitle {
      color: var(--text-muted);
      font-size: 17px;
      font-weight: 400;
      max-width: 560px;
      margin-bottom: 36px;
    }

    .meta-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 12px;
      max-width: 600px;
    }

    .meta-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 14px 16px;
    }
    .meta-card .label {
      font-size: 11px;
      font-weight: 600;
      letter-spacing: 0.8px;
      text-transform: uppercase;
      color: var(--text-dim);
      margin-bottom: 4px;
    }
    .meta-card .value {
      font-size: 14px;
      font-weight: 500;
      color: var(--text);
    }

    /* LAYOUT */
    .container {
      max-width: 900px;
      margin: 0 auto;
      padding: 0 32px 80px;
    }

    /* SECTION */
    .section {
      margin-top: 56px;
    }

    .section-header {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 24px;
      padding-bottom: 16px;
      border-bottom: 1px solid var(--border);
    }

    .section-icon {
      width: 36px; height: 36px;
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      font-size: 17px;
      flex-shrink: 0;
    }
    .icon-teal   { background: var(--accent-dim); }
    .icon-indigo { background: var(--accent2-dim); }
    .icon-red    { background: var(--red-dim); }
    .icon-green  { background: var(--green-dim); }
    .icon-yellow { background: rgba(251,191,36,0.1); }

    .section-header h2 {
      font-size: 20px;
      font-weight: 600;
      letter-spacing: -0.4px;
    }

    /* TEAM GRID */
    .team-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 12px;
    }

    .team-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 16px 18px;
      display: flex;
      align-items: center;
      gap: 12px;
      transition: border-color 0.2s;
    }
    .team-card:hover { border-color: rgba(45,212,191,0.3); }

    .avatar {
      width: 36px; height: 36px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      display: flex; align-items: center; justify-content: center;
      font-size: 13px;
      font-weight: 700;
      color: #0d1117;
      flex-shrink: 0;
    }

    .team-name { font-size: 14px; font-weight: 500; }

    /* OVERVIEW */
    .overview-box {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 28px 32px;
      line-height: 1.8;
    }
    .overview-box p { color: var(--text-muted); margin-bottom: 12px; }
    .overview-box p:last-child { margin-bottom: 0; }
    .overview-box strong { color: var(--text); font-weight: 600; }

    .objective-chip {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: var(--accent-dim);
      border: 1px solid rgba(45,212,191,0.2);
      border-radius: 8px;
      padding: 10px 16px;
      color: var(--accent);
      font-size: 14px;
      font-weight: 500;
      margin-top: 16px;
    }

    /* FEATURE GRID */
    .feature-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 14px;
    }

    .feature-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 20px;
      transition: border-color 0.2s, transform 0.15s;
    }
    .feature-card:hover { border-color: rgba(45,212,191,0.25); transform: translateY(-2px); }

    .feature-num {
      font-family: 'JetBrains Mono', monospace;
      font-size: 11px;
      font-weight: 500;
      color: var(--accent);
      margin-bottom: 10px;
      opacity: 0.7;
    }

    .feature-title {
      font-size: 15px;
      font-weight: 600;
      margin-bottom: 8px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .feature-desc {
      font-size: 13px;
      color: var(--text-muted);
      line-height: 1.6;
    }

    .feature-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 12px;
    }

    .tag {
      font-size: 11px;
      font-weight: 500;
      padding: 2px 8px;
      border-radius: 4px;
      font-family: 'JetBrains Mono', monospace;
    }
    .tag-teal   { background: var(--accent-dim); color: var(--accent); }
    .tag-indigo { background: var(--accent2-dim); color: var(--accent2); }
    .tag-red    { background: var(--red-dim); color: var(--red); }
    .tag-green  { background: var(--green-dim); color: var(--green); }

    /* USE CASES */
    .usecase-list {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    .usecase-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      overflow: hidden;
    }

    .usecase-header {
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 16px 20px;
      cursor: pointer;
      user-select: none;
    }
    .usecase-header:hover { background: rgba(255,255,255,0.02); }

    .usecase-dot {
      width: 8px; height: 8px;
      border-radius: 50%;
      background: var(--accent);
      flex-shrink: 0;
    }

    .usecase-title {
      font-size: 15px;
      font-weight: 600;
      flex: 1;
    }

    .usecase-actor {
      font-size: 12px;
      padding: 2px 10px;
      border-radius: 4px;
      font-weight: 500;
    }
    .actor-patient { background: var(--green-dim); color: var(--green); }
    .actor-doctor  { background: var(--accent2-dim); color: var(--accent2); }
    .actor-both    { background: var(--accent-dim); color: var(--accent); }

    .usecase-body {
      padding: 0 20px 20px 42px;
      font-size: 13.5px;
      color: var(--text-muted);
    }

    .usecase-body ol {
      padding-left: 18px;
      margin-bottom: 10px;
    }
    .usecase-body ol li { margin-bottom: 4px; }

    .alt-label {
      font-size: 12px;
      font-weight: 600;
      color: var(--red);
      text-transform: uppercase;
      letter-spacing: 0.5px;
      margin-top: 10px;
      margin-bottom: 6px;
    }

    .alt-item {
      display: flex;
      align-items: flex-start;
      gap: 8px;
      font-size: 13px;
      color: var(--text-muted);
      margin-bottom: 4px;
    }
    .alt-item::before { content: '→'; color: var(--red); font-size: 12px; margin-top: 2px; flex-shrink: 0; }

    /* ARCHITECTURE */
    .arch-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 14px;
    }
    @media (max-width: 600px) { .arch-grid { grid-template-columns: 1fr; } }

    .arch-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 22px;
    }

    .arch-card h3 {
      font-size: 14px;
      font-weight: 600;
      margin-bottom: 14px;
      display: flex;
      align-items: center;
      gap: 8px;
      color: var(--accent);
    }

    .arch-item {
      display: flex;
      flex-direction: column;
      gap: 4px;
      padding: 10px 0;
      border-bottom: 1px solid var(--border);
    }
    .arch-item:last-child { border-bottom: none; padding-bottom: 0; }

    .arch-item-name {
      font-family: 'JetBrains Mono', monospace;
      font-size: 13px;
      font-weight: 500;
      color: var(--text);
    }

    .arch-item-desc {
      font-size: 12.5px;
      color: var(--text-muted);
    }

    /* CODE BLOCK */
    .code-block {
      background: var(--surface2);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      overflow: hidden;
      margin-top: 16px;
    }

    .code-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px 16px;
      border-bottom: 1px solid var(--border);
      background: var(--surface);
    }

    .code-title {
      font-family: 'JetBrains Mono', monospace;
      font-size: 12px;
      color: var(--text-muted);
    }

    .dots { display: flex; gap: 6px; }
    .dot { width: 10px; height: 10px; border-radius: 50%; }
    .dot-red    { background: #f87171; }
    .dot-yellow { background: #fbbf24; }
    .dot-green  { background: #34d399; }

    pre {
      padding: 20px;
      overflow-x: auto;
      font-family: 'JetBrains Mono', monospace;
      font-size: 13px;
      line-height: 1.7;
      color: var(--text-muted);
    }

    pre .cmd { color: var(--accent); }
    pre .comment { color: var(--text-dim); }

    /* INSTALL */
    .prereq-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
      gap: 10px;
      margin-bottom: 20px;
    }

    .prereq-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius-sm);
      padding: 12px 14px;
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .prereq-card .p-icon { font-size: 18px; }
    .prereq-card .p-name { font-size: 13px; font-weight: 600; }
    .prereq-card .p-note { font-size: 11px; color: var(--text-dim); }

    /* DIVIDER */
    .divider {
      height: 1px;
      background: var(--border);
      margin: 48px 0;
    }

    /* FOOTER */
    .footer {
      border-top: 1px solid var(--border);
      padding: 32px;
      text-align: center;
      color: var(--text-dim);
      font-size: 13px;
      max-width: 900px;
      margin: 0 auto;
    }

    .footer strong { color: var(--accent); }
  </style>
</head>
<body>

<!-- HEADER -->
<div class="header">
  <div class="header-inner">
    <div class="badge-row">
      <span class="badge badge-teal">⚕ v1.0</span>
      <span class="badge badge-indigo">React Native + Expo</span>
      <span class="badge badge-yellow">Firebase</span>
      <span class="badge badge-teal">Programimi për Pajisje Mobile</span>
    </div>

    <h1>Medi<span class="accent">Care</span></h1>
    <p class="subtitle">Hospital Management & Patient App — një platformë mobile për menaxhimin e plotë të marrëdhënies pacient–doktor.</p>

    <div class="meta-grid">
      <div class="meta-card">
        <div class="label">Platform</div>
        <div class="value">iOS & Android</div>
      </div>
      <div class="meta-card">
        <div class="label">Frontend</div>
        <div class="value">React Native / Expo</div>
      </div>
      <div class="meta-card">
        <div class="label">Backend</div>
        <div class="value">Firebase Suite</div>
      </div>
      <div class="meta-card">
        <div class="label">Version</div>
        <div class="value">1.0 — Stable</div>
      </div>
    </div>
  </div>
</div>

<!-- CONTENT -->
<div class="container">

  <!-- TEAM -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon icon-indigo">👥</div>
      <h2>Anëtarët e Grupit</h2>
    </div>
    <div class="team-grid">
      <div class="team-card"><div class="avatar">AV</div><span class="team-name">Albena Veseli</span></div>
      <div class="team-card"><div class="avatar">AS</div><span class="team-name">Amela Syla</span></div>
      <div class="team-card"><div class="avatar">AC</div><span class="team-name">Anita Cacaj</span></div>
      <div class="team-card"><div class="avatar">AH</div><span class="team-name">Ardit Hyseni</span></div>
      <div class="team-card"><div class="avatar">DG</div><span class="team-name">Dua Gashi</span></div>
      <div class="team-card"><div class="avatar">EB</div><span class="team-name">Erzana Beqaj</span></div>
    </div>
  </div>

  <!-- OVERVIEW -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon icon-teal">📋</div>
      <h2>Përshkrim i Projektit</h2>
    </div>
    <div class="overview-box">
      <p><strong>MediCare</strong> është një aplikacion mobil për menaxhimin e plotë të marrëdhënies <strong>pacient–doktor</strong> dhe shërbimeve spitalore.</p>
      <p>Aplikacioni ofron një përvojë të thjeshtë, të sigurt dhe efikase për dy role kryesore:</p>
      <p>
        <strong>Pacientët</strong> — rezervim terminësh, akses në dokumente mjekësore, kujtesa për medikamente, gjetje spitalesh, SOS.<br/>
        <strong>Doktorët</strong> — menaxhim orari/termineve, monitorim pacientësh, analiza dhe raporte mbi aktivitetin.
      </p>
      <div class="objective-chip">🎯 Reduktimi i pritjeve, rritja e organizimit dhe komunikimi i sigurt ndërmjet palëve.</div>
    </div>
  </div>

  <!-- FEATURES -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon icon-teal">✦</div>
      <h2>Funksionalitetet Kryesore</h2>
    </div>
    <div class="feature-grid">

      <div class="feature-card">
        <div class="feature-num">01</div>
        <div class="feature-title">🔐 Authentication & Roles</div>
        <div class="feature-desc">Sign Up / Login për pacient dhe doktor. Menaxhim rolesh dhe drejtim automatik në ekranet përkatëse.</div>
        <div class="feature-tags">
          <span class="tag tag-teal">Firebase Auth</span>
          <span class="tag tag-indigo">Role-based</span>
        </div>
      </div>

      <div class="feature-card">
        <div class="feature-num">02</div>
        <div class="feature-title">📊 Dashboard i Personalizuar</div>
        <div class="feature-desc">Pamje e ndryshme sipas rolit. Pacient: lista e doktorëve + terminet. Doktor: terminet + historiku i pacientëve.</div>
        <div class="feature-tags">
          <span class="tag tag-green">Pacient</span>
          <span class="tag tag-indigo">Doktor</span>
        </div>
      </div>

      <div class="feature-card">
        <div class="feature-num">03</div>
        <div class="feature-title">📅 Menaxhim Terminësh</div>
        <div class="feature-desc">Rezervim me datë/orë, statuse në kohë reale. Doktori mund të Approve / Cancel / Reschedule.</div>
        <div class="feature-tags">
          <span class="tag tag-teal">Firestore</span>
          <span class="tag tag-red">Real-time</span>
        </div>
      </div>

      <div class="feature-card">
        <div class="feature-num">04</div>
        <div class="feature-title">🔔 Push Notifications</div>
        <div class="feature-desc">Kujtesa automatike për medikamente sipas orarit të caktuar nga pacienti.</div>
        <div class="feature-tags">
          <span class="tag tag-teal">Local Notif</span>
        </div>
      </div>

      <div class="feature-card">
        <div class="feature-num">05</div>
        <div class="feature-title">🗺 GPS & Hospital Finder</div>
        <div class="feature-desc">Kërkim lejesh GPS, marrja e koordinatave dhe lidhja me Google Maps për spitalet afër.</div>
        <div class="feature-tags">
          <span class="tag tag-green">GPS</span>
          <span class="tag tag-indigo">Google Maps</span>
        </div>
      </div>

      <div class="feature-card">
        <div class="feature-num">06</div>
        <div class="feature-title">📈 Analytics (Doktor)</div>
        <div class="feature-desc">Statistika mbi numrin e pacientëve, terminet e përfunduara dhe të anuluara. Filtrim kohor.</div>
        <div class="feature-tags">
          <span class="tag tag-indigo">Doctor only</span>
        </div>
      </div>

      <div class="feature-card">
        <div class="feature-num">07</div>
        <div class="feature-title">🚨 Emergency / SOS</div>
        <div class="feature-desc">Dërgim alarmi urgjent dhe komunikim i drejtpërdrejtë me organet kompetente.</div>
        <div class="feature-tags">
          <span class="tag tag-red">Urgjencë</span>
        </div>
      </div>

      <div class="feature-card">
        <div class="feature-num">08</div>
        <div class="feature-title">💊 Receta Elektronike</div>
        <div class="feature-desc">Doktori lëshon recetë pas konsultës. Ruhet në profilin e pacientit dhe përdoret në farmaci.</div>
        <div class="feature-tags">
          <span class="tag tag-green">E-Recipe</span>
          <span class="tag tag-teal">Firestore</span>
        </div>
      </div>

    </div>
  </div>

  <!-- USE CASES -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon icon-indigo">🔄</div>
      <h2>Use Cases – Rrjedhat Kryesore</h2>
    </div>
    <div class="usecase-list">

      <div class="usecase-card">
        <div class="usecase-header">
          <div class="usecase-dot"></div>
          <div class="usecase-title">Sign Up — Regjistrim i Ri</div>
          <span class="usecase-actor actor-patient">Pacient</span>
        </div>
        <div class="usecase-body">
          <ol>
            <li>Përdoruesi zgjedh "Sign Up"</li>
            <li>Fut Email, Password, Confirm Password</li>
            <li>Sistemi verifikon fushat dhe krijon llogarinë (Firebase Auth)</li>
            <li>Ridrejtim te Onboarding</li>
          </ol>
          <div class="alt-label">Alternativa</div>
          <div class="alt-item">Email ekziston → "Email already in use"</div>
          <div class="alt-item">Password i dobët / mismatch → mesazh gabimi</div>
        </div>
      </div>

      <div class="usecase-card">
        <div class="usecase-header">
          <div class="usecase-dot"></div>
          <div class="usecase-title">Login — Hyrje në Sistem</div>
          <span class="usecase-actor actor-both">Pacient / Doktor</span>
        </div>
        <div class="usecase-body">
          <ol>
            <li>Fut Email & Password → Login</li>
            <li>Autentikim në Firebase</li>
            <li>Merr profilin → Home / Dashboard sipas rolit</li>
          </ol>
          <div class="alt-label">Alternativa</div>
          <div class="alt-item">Credentials gabim → "Invalid email or password"</div>
          <div class="alt-item">Forgot Password → dërgohet email reset</div>
        </div>
      </div>

      <div class="usecase-card">
        <div class="usecase-header">
          <div class="usecase-dot"></div>
          <div class="usecase-title">Book Appointment — Rezervim Termini</div>
          <span class="usecase-actor actor-patient">Pacient</span>
        </div>
        <div class="usecase-body">
          <ol>
            <li>Zgjedh datë dhe orë</li>
            <li>Shton opsionalisht arsye / koment</li>
            <li>Konfirmon rezervimin</li>
            <li>Ruhet termini në Firestore me status fillestar</li>
            <li>Pacienti merr njoftim konfirmimi</li>
            <li>Doktori e sheh terminin në "My Appointments"</li>
          </ol>
          <div class="alt-label">Alternativa</div>
          <div class="alt-item">Ora e zënë → gabim me sugjerim orash të lira</div>
        </div>
      </div>

      <div class="usecase-card">
        <div class="usecase-header">
          <div class="usecase-dot"></div>
          <div class="usecase-title">Appointment Management</div>
          <span class="usecase-actor actor-doctor">Doktor</span>
        </div>
        <div class="usecase-body">
          <ol>
            <li>Hap listën e termineve</li>
            <li>Zgjedh terminin dhe sheh detajet</li>
            <li>Veprim: Approve / Cancel / Reschedule</li>
            <li>Pacienti sheh ndryshimin e statusit në kohë reale</li>
          </ol>
        </div>
      </div>

      <div class="usecase-card">
        <div class="usecase-header">
          <div class="usecase-dot"></div>
          <div class="usecase-title">Medication Reminder</div>
          <span class="usecase-actor actor-patient">Pacient</span>
        </div>
        <div class="usecase-body">
          <ol>
            <li>Pacienti shton ilaçin dhe orarin</li>
            <li>Ruhet në profilin e tij</li>
            <li>Push notification dërgohet automatikisht në kohën e caktuar</li>
          </ol>
        </div>
      </div>

      <div class="usecase-card">
        <div class="usecase-header">
          <div class="usecase-dot"></div>
          <div class="usecase-title">E-Recipe — Receta Elektronike</div>
          <span class="usecase-actor actor-doctor">Doktor</span>
        </div>
        <div class="usecase-body">
          <ol>
            <li>Doktori krijon recetën pas konsultës</li>
            <li>Ruhet automatikisht në profilin e pacientit</li>
            <li>Pacienti e paraqet në farmaci</li>
          </ol>
        </div>
      </div>

    </div>
  </div>

  <!-- ARCHITECTURE -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon icon-yellow">🏗</div>
      <h2>Arkitektura Teknike</h2>
    </div>
    <div class="arch-grid">

      <div class="arch-card">
        <h3>📱 Frontend — Mobile</h3>
        <div class="arch-item">
          <span class="arch-item-name">React Native</span>
          <span class="arch-item-desc">Framework kryesor cross-platform</span>
        </div>
        <div class="arch-item">
          <span class="arch-item-name">Expo</span>
          <span class="arch-item-desc">Build tools, dev server, OTA updates</span>
        </div>
        <div class="arch-item">
          <span class="arch-item-name">Screen-based Router</span>
          <span class="arch-item-desc">Navigim i strukturuar sipas rolit</span>
        </div>
        <div class="arch-item">
          <span class="arch-item-name">Role UI Components</span>
          <span class="arch-item-desc">Komponentë të ndara: Pacient / Doktor</span>
        </div>
      </div>

      <div class="arch-card">
        <h3>☁ Backend — Firebase</h3>
        <div class="arch-item">
          <span class="arch-item-name">Firebase Auth</span>
          <span class="arch-item-desc">Login, Sign Up, role-based access</span>
        </div>
        <div class="arch-item">
          <span class="arch-item-name">Firestore</span>
          <span class="arch-item-desc">Profil, termine, receta, historik</span>
        </div>
        <div class="arch-item">
          <span class="arch-item-name">Firebase Storage</span>
          <span class="arch-item-desc">Dokumente mjekësore, foto, raporte</span>
        </div>
        <div class="arch-item">
          <span class="arch-item-name">Push / Local Notif</span>
          <span class="arch-item-desc">Kujtesa medikamentesh dhe termine</span>
        </div>
      </div>

    </div>
  </div>

  <!-- INSTALLATION -->
  <div class="section">
    <div class="section-header">
      <div class="section-icon icon-green">⚡</div>
      <h2>Instalimi dhe Ekzekutimi</h2>
    </div>

    <div class="prereq-grid">
      <div class="prereq-card">
        <span class="p-icon">🟢</span>
        <div>
          <div class="p-name">Node.js</div>
          <div class="p-note">LTS rekomandohet</div>
        </div>
      </div>
      <div class="prereq-card">
        <span class="p-icon">📦</span>
        <div>
          <div class="p-name">Expo CLI</div>
          <div class="p-note">Global install</div>
        </div>
      </div>
      <div class="prereq-card">
        <span class="p-icon">🤖</span>
        <div>
          <div class="p-name">Android Studio</div>
          <div class="p-note">Opsionale — Emulator</div>
        </div>
      </div>
      <div class="prereq-card">
        <span class="p-icon">🍎</span>
        <div>
          <div class="p-name">iOS Simulator</div>
          <div class="p-note">Opsionale — macOS</div>
        </div>
      </div>
    </div>

    <div class="code-block">
      <div class="code-header">
        <div class="dots">
          <div class="dot dot-red"></div>
          <div class="dot dot-yellow"></div>
          <div class="dot dot-green"></div>
        </div>
        <span class="code-title">terminal</span>
      </div>
      <pre><span class="comment"># 1. Instalo dependencies</span>
<span class="cmd">npm install</span>

<span class="comment"># 2. Starto projektin</span>
<span class="cmd">expo start</span>

<span class="comment"># Skano QR kodin me Expo Go ose hap emulatorin</span></pre>
    </div>
  </div>

  <div class="divider"></div>

  <!-- FIRESTORE SCHEMA NOTE -->
  <div class="section" style="margin-top: 0;">
    <div class="section-header">
      <div class="section-icon icon-teal">🗄</div>
      <h2>Struktura e të Dhënave — Appointments</h2>
    </div>
    <div class="code-block">
      <div class="code-header">
        <div class="dots">
          <div class="dot dot-red"></div>
          <div class="dot dot-yellow"></div>
          <div class="dot dot-green"></div>
        </div>
        <span class="code-title">Firestore — appointments/{id}</span>
      </div>
      <pre>{
  <span class="cmd">createdAt</span>: Timestamp,
  <span class="cmd">date</span>:      "YYYY-MM-DD",
  <span class="cmd">time</span>:      "HH:MM",
  <span class="cmd">patientId</span>: string,
  <span class="cmd">patientName</span>: string,
  <span class="cmd">doctorId</span>:  string,
  <span class="cmd">doctorName</span>: string,
  <span class="cmd">reason</span>:    string,
  <span class="cmd">status</span>:    "pending" | "approved" | "cancelled",
  <span class="cmd">notes</span>:     string
}</pre>
    </div>
  </div>

</div>

<!-- FOOTER -->
<div class="footer">
  <strong>MediCare v1.0</strong> — Programimi për Pajisje Mobile &nbsp;·&nbsp; React Native + Expo + Firebase &nbsp;·&nbsp; 2024
</div>

</body>
</html>
