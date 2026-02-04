# 🚩 CTF Web Exploit Challenge - Level Medium

## Deskripsi
Selamat datang di SecureShop! Sebuah toko online yang "aman"... atau mungkin tidak? 🤔

Misimu adalah menemukan FLAG yang tersembunyi di dalam sistem!

## Cara Menjalankan

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Jalankan Server
```bash
python server.py
```

### 3. Buka Browser
Akses: http://localhost:5000

---

## 🎯 Objective
Temukan flag dengan format: `FLAG{...}`

## 💡 Hints (Buka jika stuck!)

<details>
<summary>Hint 1 - Umum</summary>
Eksplorasi semua halaman dan fitur yang ada. Perhatikan URL dan parameter.
</details>

<details>
<summary>Hint 2 - Vulnerability Type</summary>
Website ini memiliki kerentanan SQL Injection.
</details>

<details>
<summary>Hint 3 - Attack Vector</summary>
Halaman search (/search) sangat rentan. Coba masukkan karakter khusus seperti tanda kutip (').
</details>

<details>
<summary>Hint 4 - Enumeration</summary>
Gunakan UNION-based SQL Injection untuk menggabungkan hasil dari tabel lain. Pertama, cari tahu jumlah kolom dengan ORDER BY atau UNION SELECT 1,2,3,4.
</details>

<details>
<summary>Hint 5 - Finding Tables</summary>
Kunjungi /api/debug?info=tables untuk melihat nama-nama tabel yang ada.
</details>

<details>
<summary>Hint 6 - Final Payload</summary>
Gunakan payload seperti:
```
' UNION SELECT 1, flag, 3, 4 FROM admin_secrets--
```
</details>

---

## 🛡️ Vulnerabilities (Untuk Pembelajaran)

1. **SQL Injection** di halaman login dan search
2. **IDOR** (Insecure Direct Object Reference) di halaman profile
3. **Information Disclosure** di endpoint /api/debug
4. **Weak Session Management**

## 📚 Learning Resources
- [OWASP SQL Injection](https://owasp.org/www-community/attacks/SQL_Injection)
- [PortSwigger SQL Injection Labs](https://portswigger.net/web-security/sql-injection)
- [HackTheBox](https://www.hackthebox.com/)

---

**⚠️ Disclaimer:** 
Challenge ini dibuat untuk tujuan edukasi. Jangan gunakan teknik ini pada sistem yang tidak kamu miliki izin untuk di-test!

Good luck, hacker! 🎩
