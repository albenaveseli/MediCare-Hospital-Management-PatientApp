<div align="center">

<img src="assets/images/common.jpg" width="90" style="border-radius: 20px;" />

# 🏥 MediCare
### Hospital Management & Patient App

[![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactnative.dev/)
[![Expo](https://img.shields.io/badge/Expo-000020?style=for-the-badge&logo=expo&logoColor=white)](https://expo.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com/)

**Platformë mobile për menaxhimin e plotë të marrëdhënies pacient–doktor**

*Programimi për Pajisje Mobile — Version 1.0*

</div>

---

## 👥 Anëtarët e Grupit

| # | Emri |
|---|------|
| 1 | Albena Veseli |
| 2 | Amela Syla |
| 3 | Anita Cacaj |
| 4 | Ardit Hyseni |
| 5 | Dua Gashi |
| 6 | Erzana Beqaj |

---

## 📋 Përshkrim i Projektit

**MediCare** është një aplikacion mobil për menaxhimin e plotë të marrëdhënies **pacient–doktor** dhe shërbimeve spitalore. Aplikacioni ofron një përvojë të thjeshtë, të sigurt dhe efikase për dy role kryesore:

| Roli | Funksionalitetet |
|------|-----------------|
| 🙋 **Pacient** | Rezervim terminësh, akses në dokumente mjekësore, kujtesa për medikamente, gjetje spitalesh, SOS |
| 👨‍⚕️ **Doktor** | Menaxhim orari/termineve, monitorim pacientësh, analiza dhe raporte mbi aktivitetin |

> 🎯 **Objektivi kryesor:** Reduktimi i pritjeve, rritja e organizimit dhe komunikimi më i shpejtë e i sigurt ndërmjet palëve.

---

## ✦ Funksionalitetet Kryesore

<table>
<tr>
<td width="50%">

### 🔐 1. Authentication & Roles
- Sign Up / Login për **Pacient**
- Login për **Doktor**
- Menaxhim rolesh dhe drejtim automatik sipas rolit

### 📊 2. Personalized Dashboard
- **Pacient:** listë doktorësh + terminet e ardhshme
- **Doktor:** terminet e planifikuara + historiku i pacientëve

### 📅 3. Appointment Booking & Management
- Rezervim termini me datë/orë
- Fusha: `createdAt` `date` `patientId` `doctorId` `reason` `status` `notes` `time`
- Doktori: **Approve / Cancel / Reschedule**
- Njoftime për çdo ndryshim statusi

### 🔔 4. Push Notifications & Reminders
- Kujtesa automatike për medikamente sipas orarit

</td>
<td width="50%">

### 🗺️ 5. GPS & Hospital Finder
- Kërkim lejesh GPS
- Marrja e koordinatave
- Lidhje me Google Maps

### 📈 6. Analytics — Doctor Dashboard
- Numri i pacientëve
- Terminet e përfunduara / të anuluara
- Filtrim kohor

### 🚨 7. Emergency / SOS
- Dërgim alarmi urgjent
- Komunikim i drejtpërdrejtë me organet kompetente

### 💊 8. E-Recipe (Receta Elektronike)
- Doktori lëshon recetë pas konsultës
- Ruhet në profilin e pacientit
- E përdorshme në farmaci

</td>
</tr>
</table>

---

## 🔄 Use Cases — Rrjedhat Kryesore

<details>
<summary><b>🟢 Sign Up — Regjistrim i Ri</b> <code>Pacient</code></summary>
<br>

**Trigger:** "Sign Up" në Welcome Screen

1. Përdoruesi zgjedh **Sign Up**
2. Fut Email, Password, Confirm Password
3. Sistemi verifikon fushat dhe krijon llogarinë *(Firebase Auth)*
4. Ridrejtim te **Onboarding**

**⚠️ Alternativa:**
- Email ekziston → `"Email already in use"`
- Password i dobët / mismatch → mesazh gabimi

</details>

<details>
<summary><b>🔵 Login — Hyrje në Sistem</b> <code>Pacient / Doktor</code></summary>
<br>

1. Fut Email & Password → **Login**
2. Autentikim në Firebase
3. Merr profilin → Home / Dashboard sipas rolit

**⚠️ Alternativa:**
- Credentials gabim → `"Invalid email or password"`
- Forgot Password → dërgohet email reset

</details>

<details>
<summary><b>🟢 Onboarding</b> <code>Pacient i Ri</code></summary>
<br>

1. Vendos datën e lindjes, gjininë dhe të dhëna të tjera
2. Konfirmon → **Home**

</details>

<details>
<summary><b>🟢 Book Appointment — Rezervim Termini</b> <code>Pacient</code></summary>
<br>

1. Zgjedh datë dhe orë
2. Shton opsionalisht arsye / koment
3. Klikon **Confirm**
4. Ruhet termini në Firestore me status fillestar
5. Pacienti merr njoftim konfirmimi
6. Doktori e sheh terminin në **My Appointments**

**⚠️ Alternativa:** ora e zënë → gabim me sugjerim orash të lira

</details>

<details>
<summary><b>🔵 Appointment Management</b> <code>Doktor</code></summary>
<br>

1. Hap listën e termineve
2. Zgjedh terminin dhe sheh detajet
3. Veprim: **Approve / Cancel / Reschedule**
4. Pacienti sheh ndryshimin e statusit **në kohë reale**

</details>

<details>
<summary><b>🟢 Medication Reminder</b> <code>Pacient</code></summary>
<br>

1. Pacienti shton ilaçin dhe orarin
2. Ruhet në profilin e tij
3. Push notification dërgohet automatikisht në kohën e caktuar

</details>

<details>
<summary><b>🔵 E-Recipe — Receta Elektronike</b> <code>Doktor</code></summary>
<br>

1. Doktori krijon recetën pas konsultës
2. Ruhet automatikisht në profilin e pacientit
3. Pacienti e paraqet në farmaci

</details>

<details>
<summary><b>🟡 GPS & Hospital Finder</b> <code>Pacient</code></summary>
<br>

1. Kërkohen lejet e GPS
2. Merren koordinatat aktuale
3. Mundësohet lidhja me Google Maps

</details>

<details>
<summary><b>🔵 Analytics</b> <code>Doktor</code></summary>
<br>

1. Shfaq statistika të detajuara
2. Filtrim kohor sipas periudhës

</details>

---

## 🏗️ Arkitektura Teknike

```
MediCare
├── 📱 Frontend (React Native + Expo)
│   ├── Screen-based Router (navigim sipas rolit)
│   ├── UI Components — Pacient
│   └── UI Components — Doktor
│
└── ☁️ Backend (Firebase)
    ├── Firebase Authentication   → Login, Sign Up, Role-based Access
    ├── Firestore Database        → Profil, Termine, Receta, Historik
    ├── Firebase Storage          → Dokumente, Foto, Raporte
    └── Notifications & Location → Push/Local Notif, GPS, Hospital Finder
```

### 🗄️ Firestore — Struktura e Terminit

```json
{
  "createdAt":   "Timestamp",
  "date":        "YYYY-MM-DD",
  "time":        "HH:MM",
  "patientId":   "string",
  "patientName": "string",
  "doctorId":    "string",
  "doctorName":  "string",
  "reason":      "string",
  "status":      "pending | approved | cancelled",
  "notes":       "string"
}
```

---

## ⚡ Instalimi dhe Ekzekutimi

### Kërkesat

- ![Node.js](https://img.shields.io/badge/Node.js-LTS-green?logo=node.js&logoColor=white)
- ![Expo CLI](https://img.shields.io/badge/Expo_CLI-latest-black?logo=expo)
- *(Opsionale)* Android Studio Emulator / iOS Simulator

### Hapat

```bash
# 1. Instalo dependencies
npm install

# 2. Starto projektin
expo start
```

> Skano QR kodin me **Expo Go** ose hap emulatorin sipas platformës.

---

## 📱 Application Flow — Doctor Side

Rrjedha logjike e përdorimit të aplikacionit për **Doktorin**, nga hyrja në sistem deri te menaxhimi i pacientëve dhe shërbimeve.

### 🔐 Authentication & Entry

<div align="center">
  <img src="assets/images/common.jpg" width="200" />
  <img src="assets/images/common6.png" width="200" />
  <img src="assets/images/common7.png" width="200" />
  <img src="assets/images/common8.png" width="200" />
</div>

---

### 🏠 Doctor Dashboard & Overview

<div align="center">
  <img src="assets/images/doctor1.png" width="180" />
  <img src="assets/images/doctor2.png" width="180" />
  <img src="assets/images/doctor3.png" width="180" />
  <img src="assets/images/doctor4.png" width="180" />
  <img src="assets/images/doctor5.png" width="180" />
  <img src="assets/images/doctor6.png" width="180" />
</div>

---

### 📅 Appointments Management

<div align="center">
  <img src="assets/images/doctor7.png" width="180" />
  <img src="assets/images/doctor10.png" width="180" />
  <img src="assets/images/doctor11.png" width="180" />
  <img src="assets/images/doctor12.png" width="180" />
  <img src="assets/images/doctor13.png" width="180" />
  <img src="assets/images/doctor14.png" width="180" />
  <img src="assets/images/doctor15.png" width="180" />
  <img src="assets/images/doctor16.png" width="180" />
</div>

---

### 👤 Profile & Logout

<div align="center">
  <img src="assets/images/doctor8.png" width="180" />
  <img src="assets/images/doctor9.png" width="180" />
</div>

---

## 📱 Application Flow — Patient Side

Rrjedha e plotë e përdorimit për **Pacientin**, nga regjistrimi deri te kujdesi shëndetësor dhe njoftimet.

### 🔐 Authentication & Onboarding

<div align="center">
  <img src="assets/images/common.jpg" width="200" />
  <img src="assets/images/common2.png" width="200" />
  <img src="assets/images/common3.png" width="200" />
  <img src="assets/images/common4.png" width="200" />
  <img src="assets/images/common5.png" width="200" />
  <img src="assets/images/common6.png" width="200" />
  <img src="assets/images/common7.png" width="200" />
  <img src="assets/images/common8.png" width="200" />
</div>

---

### 🏠 Home & Doctor Discovery

<div align="center">
  <img src="assets/images/pacient1.png" width="180" />
  <img src="assets/images/pacient2.png" width="180" />
  <img src="assets/images/pacient3.png" width="180" />
  <img src="assets/images/pacient5.png" width="180" />
  <img src="assets/images/pacient6.png" width="180" />
  <img src="assets/images/pacient7.png" width="180" />
  <img src="assets/images/pacient8.png" width="180" />
  <img src="assets/images/pacient9.png" width="180" />
</div>

---

### 📅 Appointment Booking Flow

<div align="center">
  <img src="assets/images/pacient4.png" width="180" />
  <img src="assets/images/pacient16.png" width="180" />
  <img src="assets/images/pacient21.png" width="180" />
  <img src="assets/images/pacient22.png" width="180" />
  <img src="assets/images/pacient23.png" width="180" />
  <img src="assets/images/pacient24.png" width="180" />
  <img src="assets/images/pacient25.png" width="180" />
  <img src="assets/images/pacient26.png" width="180" />
  <img src="assets/images/pacient27.png" width="180" />
  <img src="assets/images/pacient28.png" width="180" />
  <img src="assets/images/pacient29.png" width="180" />
</div>

---

### 🗂️ Medical Records

<div align="center">
  <img src="assets/images/pacient15.png" width="180" />
  <img src="assets/images/pacient10.png" width="180" />
  <img src="assets/images/pacient20.png" width="180" />
</div>

---

### 🔔 Notifications, Reminders & SOS, GPS

<div align="center">
  <img src="assets/images/pacient11.png" width="180" />
  <img src="assets/images/pacient17.png" width="180" />
  <img src="assets/images/pacient14.png" width="180" />
  <img src="assets/images/pacient12.png" width="180" />
  <img src="assets/images/pacient18.png" width="180" />
  <img src="assets/images/pacient19.png" width="180" />
</div>

---

### 👤 Profile & Logout

<div align="center">
  <img src="assets/images/pacient30.png" width="180" />
  <img src="assets/images/pacient31.png" width="180" />
  <img src="assets/images/pacient32.jpg" width="180" />
</div>

---

<div align="center">

**MediCare v1.0** &nbsp;·&nbsp; Programimi për Pajisje Mobile &nbsp;·&nbsp; React Native + Expo + Firebase

</div>
