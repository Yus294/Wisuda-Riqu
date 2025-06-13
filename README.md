# Wisuda-Riqu
<html>
  <head>
    <title>Hello, World!</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
      <h1 class="title">Hello World! </h1>
      <p id="currentTime"></p>
      <script src="script.js"></script>
  </body>
</html><!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rumah Tahfizh Riyadhul Qur'an</title>
  <style>
    * {
      box-sizing: border-box;
    }
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(to bottom right, #e8f5e9, #ffffff);
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
    }
    header {
      text-align: center;
      margin-top: 30px;
    }
    header img {
      max-width: 120px;
      height: auto;
    }
    h1 {
      margin-top: 15px;
      margin-bottom: 20px;
      color: #2e7d32;
      text-align: center;
      font-size: 1.8rem;
      padding: 0 20px;
    }
    form {
      background-color: #ffffff;
      padding: 25px;
      border-radius: 15px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
      width: 90%;
      max-width: 500px;
      margin-bottom: 40px;
    }
    label {
      display: block;
      margin-top: 15px;
      font-weight: bold;
      color: #444;
    }
    input[type="text"], textarea, select { /* Added select to styling */
      width: 100%;
      padding: 12px;
      margin-top: 6px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 1rem;
    }
    textarea {
      resize: vertical;
    }
    button {
      margin-top: 25px;
      padding: 12px 25px;
      background-color: #43a047;
      color: white;
      font-size: 1rem;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background-color 0.3s ease;
      width: 100%;
    }
    button:hover {
      background-color: #388e3c;
    }
    @media screen and (max-width: 600px) {
      h1 {
        font-size: 1.5rem;
      }
      form {
        padding: 20px;
      }
    }
  </style>
  <script src="https://cdn.emailjs.com/dist/email.min.js"></script>
  <script>
    (function(){
      emailjs.init("4uIOwIvzW_BCIzayT");
    })();
  </script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
</head>
<body>
  <header>
    <img src="Lambang Riqu.jfif" alt="Logo Rumah Tahfizh Riyadhul Qur'an">

    <div style="display: flex; flex-direction: column; align-items: center; margin-top: 10px;">
      <div style="display: flex; align-items: center; gap: 10px;">
        <i class="fas fa-pen-nib" style="font-size: 1.5rem; color: #2e7d32;"></i>
        <span style="font-size: 1.2rem; font-weight: bold; color: #2e7d32;">Riyadhul Qur'an</span>
      </div>
      <small style="font-style: italic; color: #555; margin-top: 4px;">Creator: Yusuf Abdullah</small>
    </div>

    <h1>Selamat Datang di Rumah Tahfizh Riyadhul Qur'an</h1>
  </header>

  <form id="formSantri">
    <input type="hidden" name="subject" value="Data Santri Baru">

    <label for="nama">Pilih Nama Santri:</label>
    <select id="nama" name="nama_santri" required>
      <option value="">-- Pilih Santri --</option>
      <option value="Giansi Abiyu Musyaffa Bin Sugianto">Giansi Abiyu Musyaffa Bin Sugianto</option>
      <option value="Dihya Khalifa Bin Miftah">Dihya Khalifa Bin Miftah</option>
      <option value="Ghaizan Faeyza Alamsyah Bin Yuta Alamsyah">Ghaizan Faeyza Alamsyah Bin Yuta Alamsyah</option>
      <option value="Muhammad Izzat Adi Zulfadhli Bin Arif Adi Waskito">Muhammad Izzat Adi Zulfadhli Bin Arif Adi Waskito</option>
      <option value="Muhammad Arkaan Haritztsany Salesko Bin Gunawan Ismail Salesko">Muhammad Arkaan Haritztsany Salesko Bin Gunawan Ismail Salesko</option>
      <option value="Kahfi Muhammad Zain Bin Aang Abu Azhar">Kahfi Muhammad Zain Bin Aang Abu Azhar</option>
      <option value="Tsalitsa Rizki Zhafira Halni Binti Roni Rosmansyah">Tsalitsa Rizki Zhafira Halni Binti Roni Rosmansyah</option>
      <option value="Hafshah Binti Yadi Supriyadi">Hafshah Binti Yadi Supriyadi</option>
      <option value="Bella Putri Almahyra Binti Bayu Suci Widayat">Bella Putri Almahyra Binti Bayu Suci Widayat</option>
      <option value="Fatimah Az-Zahra Binti Andi Sulaeman">Fatimah Az-Zahra Binti Andi Sulaeman</option>
      <option value="Queen Nabilah Huriyah Manyasya Binti Dwi Agus Setyana">Queen Nabilah Huriyah Manyasya Binti Dwi Agus Setyana</option>
      <option value="Khairana Adibah Dafirni Binti Muhammad Asep Firmansyah">Khairana Adibah Dafirni Binti Muhammad Asep Firmansyah</option>
      <option value="Atikah Athaya Refi Kaylaningsih Binti Renggo Pitono">Atikah Athaya Refi Kaylaningsih Binti Renggo Pitono</option>
      <option value="Triya Khaira Asyfa Binti Widodo">Triya Khaira Asyfa Binti Widodo</option>
      <option value="Naura Fauzhara Putri Binti Abdul Rohman">Naura Fauzhara Putri Binti Abdul Rohman</option>
    </select>

    <label for="pencapaian">Sebutkan Pencapaian Terakhir Santri:<br>
      <small>Contoh: Tilawah Al-Baqarah : 150 / Tahfizh Al-Baqarah : 150</small>
    </label>
    <textarea id="pencapaian" name="pencapaian_santri" rows="4" placeholder="Tulis pencapaian di sini..." required></textarea>

    <label for="jumlahHafalan">Jumlah Hafalan (Juz):</label>
    <input type="text" id="jumlahHafalan" name="jumlah_hafalan" placeholder="Contoh: 5 Juz" required>

    <button type="submit">Simpan Data</button>
  </form>

  <audio autoplay>
    <source src="https://upload.wikimedia.org/wikipedia/commons/5/5c/Selamat_Datang_di_Rumah_Tahfizh_Riyadhul_Quran.ogg" type="audio/ogg">
    Browser Anda tidak mendukung audio.
  </audio>

  <script>
    document.getElementById("formSantri").addEventListener("submit", function(event) {
      event.preventDefault();

      emailjs.sendForm("service_5l5ovxe", "template_q1igllh", this)
        .then(function(response) {
          alert("Permintaan Anda sukses!");
          document.getElementById("formSantri").reset();
        }, function(error) {
          alert("Gagal mengirim. Silakan periksa koneksi atau ID EmailJS Anda.");
        });
    });
  </script>
</body>
</html>
