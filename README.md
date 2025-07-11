# **Summer Practice 2025 – Smart Office Attendance System**

Acest proiect realizat în cadrul **practicii de vară 2025** integrează două componente principale:

- Un sistem de pontaj bazat pe **Raspberry Pi**, dotat cu **cameră web**, aplicație web în **Flask**, afișaj și fișier JSON pentru stocarea locală a datelor  
- Un mecanism de autentificare pe bază de **cod QR** și **PIN unic** pentru fiecare angajat  

Ambele componente fac parte dintr-un sistem inteligent de gestionare a prezenței într-o clădire de birouri.

---

## **Partea 1 – Sistem de pontaj cu QR și PIN**

Am creat o aplicație web în **Python** folosind **Flask**, care rulează local pe un **Raspberry Pi**. Acesta este conectat la o **cameră web**, care permite scanarea codurilor QR direct din interfața browserului. Sistemul funcționează astfel:

1. Utilizatorul selectează tipul acțiunii: **check-in**, **check-out** sau **pauză de masă**  
2. Se solicită introducerea **PIN-ului unic**  
3. Utilizatorul scanează un **cod QR** (care conține ID-ul angajatului)  
4. Sistemul verifică dacă combinația QR + PIN este validă  
5. Dacă totul este corect:
   - Acțiunea este înregistrată într-un fișier JSON structurat pe zile
   - Utilizatorul primește un mesaj de confirmare

---

🔁 Pauza de masă poate fi înregistrată doar în intervalul **12:00–12:30**  
🔒 Sistemul nu permite **check-out** fără **check-in** anterior  
📁 Toate datele sunt salvate în fișierul **`data.json`**

---

## **Feedback vizual (în interfață)**

- ✅ **Tranzacție validă** – mesaj de succes  
- ❌ **PIN greșit / Cod QR invalid** – mesaj de eroare  
- ⚠️ **Check-out fără check-in** – avertizare  

---

## **Partea 2 – Pagină de administrare**

Am implementat o **pagină de admin** accesibilă în browser (`/admin`) unde pot fi vizualizate toate activitățile angajaților:

- Numele angajatului  
- Ora de check-in / check-out  
- Pauza de masă bifată (da/nu)  
- Informația dacă lucrează de acasă  

Această funcționalitate ajută la urmărirea centralizată a prezenței și poate fi extinsă cu funcții suplimentare precum export în Excel, generare rapoarte etc.

---

## **Practica de vară – 2025**  
**Facultatea de Automatică, Calculatoare și Electronică – Universitatea din Craiova**  
**Student:** Arbaselu Mario Ionuț  
**Profesor coordonator:** Hurezeanu Bogdan
