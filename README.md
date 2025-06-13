<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rumah Tahfizh Riyadhul Qur'an</title>

    <style>
        /* Atur box-sizing untuk semua elemen agar padding dan border tidak menambah ukuran elemen */
        *, *::before, *::after {
            box-sizing: border-box;
        }

        /* Styling untuk body halaman */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; /* Font utama yang bersih */
            background: linear-gradient(to bottom right, #e8f5e9, #ffffff); /* Gradien latar belakang lembut */
            margin: 0; /* Hapus margin default browser */
            padding: 0; /* Hapus padding default browser */
            display: flex; /* Menggunakan flexbox untuk tata letak halaman utama */
            flex-direction: column; /* Elemen ditumpuk secara vertikal */
            align-items: center; /* Pusatkan elemen anak secara horizontal */
            min-height: 100vh; /* Pastikan halaman setidaknya setinggi viewport */
            color: #333; /* Warna teks default yang lebih gelap */
        }

        /* Styling untuk header */
        header {
            display: flex; /* Flexbox untuk menata elemen di dalam header */
            flex-direction: column; /* Elemen ditumpuk vertikal */
            align-items: center; /* Pusatkan secara horizontal */
            margin-top: 30px; /* Jarak dari atas halaman */
            padding: 0 15px; /* Padding samping untuk responsivitas */
            text-align: center; /* Pastikan teks di header terpusat */
        }

        /* Styling untuk gambar logo di header */
        header img {
            max-width: 120px; /* Batasi lebar gambar */
            height: auto; /* Jaga rasio aspek */
            border-radius: 50%; /* Membuat gambar menjadi lingkaran */
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); /* Bayangan lembut */
        }

        /* Styling untuk kontainer nama dan creator */
        .header-info {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-top: 15px; /* Jarak dari logo */
        }

        .header-title {
            display: flex;
            align-items: center;
            gap: 10px; /* Jarak antara ikon dan teks */
            color: #2e7d32; /* Warna hijau tua */
            font-size: 1.25rem; /* Ukuran font lebih besar */
            font-weight: bold;
        }

        .header-creator {
            font-style: italic;
            color: #555;
            margin-top: 5px; /* Jarak dari judul utama */
            font-size: 0.9rem;
        }

        /* Styling untuk judul utama (h1) */
        h1 {
            margin-top: 25px; /* Jarak dari info header */
            margin-bottom: 30px; /* Jarak dari formulir */
            color: #1b5e20; /* Warna hijau yang lebih gelap untuk penekanan */
            text-align: center;
            font-size: 2rem; /* Ukuran font lebih besar untuk judul utama */
            line-height: 1.3; /* Jarak antar baris */
        }

        /* Styling untuk formulir */
        form {
            background-color: #ffffff; /* Latar belakang putih */
            padding: 30px; /* Padding yang lebih merata */
            border-radius: 15px; /* Sudut membulat */
            box-shadow: 0 6px 25px rgba(0, 0, 0, 0.15); /* Bayangan yang lebih menonjol */
            margin-bottom: 50px; /* Jarak dari bawah halaman */
            width: 95%; /* Lebih fleksibel di layar kecil */
            max-width: 700px; /* Lebar maksimum yang lebih fokus */
        }

        /* Styling untuk grup input agar lebih rapi */
        .form-group {
            margin-bottom: 20px; /* Jarak antar grup input */
        }

        /* Styling untuk label formulir */
        label {
            display: block; /* Menjadikan label sebagai blok elemen */
            margin-bottom: 8px; /* Jarak dari input */
            font-weight: bold;
            color: #444;
            text-align: left; /* Label rata kiri */
            font-size: 1.05rem;
        }

        /* Styling untuk teks kecil di dalam label */
        label small {
            display: block;
            text-align: left; /* Teks kecil juga rata kiri */
            margin-top: 5px;
            color: #777;
            font-weight: normal;
            font-size: 0.85rem;
        }

        /* Styling untuk input teks, textarea, dan select */
        input[type="text"],
        textarea,
        select {
            width: 100%; /* Lebar penuh */
            padding: 12px 15px; /* Padding di dalam input */
            border: 1px solid #ddd; /* Border abu-abu terang */
            border-radius: 8px; /* Sudut membulat */
            font-size: 1rem;
            color: #333; /* Warna teks input */
            transition: border-color 0.3s ease, box-shadow 0.3s ease; /* Transisi halus saat fokus */
        }

        /* Efek fokus untuk input */
        input[type="text"]:focus,
        textarea:focus,
        select:focus {
            outline: none; /* Hapus outline default browser */
            border-color: #4CAF50; /* Warna border hijau saat fokus */
            box-shadow: 0 0 0 3px rgba(76, 175, 80, 0.2); /* Bayangan fokus lembut */
        }

        /* Styling untuk placeholder text */
        input::placeholder,
        textarea::placeholder {
            color: #999;
            font-style: italic; /* Placeholder sedikit miring */
        }

        /* Styling khusus untuk textarea agar bisa di-resize vertikal */
        textarea {
            resize: vertical;
            min-height: 80px; /* Tinggi minimum textarea */
            max-height: 200px; /* Tinggi maksimum textarea */
        }

        /* Styling untuk tombol submit */
        button[type="submit"] {
            margin-top: 30px; /* Jarak dari input terakhir */
            padding: 14px 25px; /* Padding lebih besar */
            background-color: #4CAF50; /* Warna latar belakang hijau standar */
            color: white; /* Warna teks putih */
            font-size: 1.1rem; /* Ukuran font lebih besar */
            font-weight: bold;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.2s ease; /* Transisi untuk warna dan skala */
            width: 100%;
            display: block; /* Pastikan tombol menjadi blok */
        }

        /* Efek hover dan active untuk tombol */
        button[type="submit"]:hover {
            background-color: #45a049; /* Warna hijau lebih gelap saat di-hover */
            transform: translateY(-2px); /* Efek sedikit terangkat */
        }

        button[type="submit"]:active {
            transform: translateY(0); /* Kembali ke posisi semula saat diklik */
        }

        /* Media Queries untuk responsivitas pada layar kecil (maks 768px dan 480px) */
        @media screen and (max-width: 768px) {
            h1 {
                font-size: 1.8rem;
            }
            form {
                padding: 25px;
            }
        }

        @media screen and (max-width: 480px) {
            h1 {
                font-size: 1.5rem;
                margin-top: 20px;
                margin-bottom: 25px;
            }
            header img {
                max-width: 100px;
            }
            .header-title {
                font-size: 1.1rem;
            }
            form {
                padding: 20px;
            }
            label {
                font-size: 1rem;
            }
            input[type="text"],
            textarea,
            select,
            button[type="submit"] {
                font-size: 0.95rem;
                padding: 10px 12px;
            }
        }

        /* --- CSS untuk Modal Pop-up --- */
        .modal {
            display: none; /* Tersembunyi secara default */
            position: fixed; /* Tetap di layar */
            z-index: 1000; /* Paling atas dari semua elemen */
            left: 0;
            top: 0;
            width: 100%; /* Lebar penuh */
            height: 100%; /* Tinggi penuh */
            background-color: rgba(0,0,0,0.6); /* Background hitam transparan */
            justify-content: center; /* Pusatkan secara horizontal */
            align-items: center; /* Pusatkan secara vertikal */
            opacity: 0; /* Untuk animasi fade-in */
            transition: opacity 0.3s ease-in-out; /* Transisi opacity */
        }

        .modal.show {
            opacity: 1;
            display: flex; /* Tampilkan sebagai flexbox saat kelas 'show' ditambahkan */
        }

        .modal-content {
            background-color: #fefefe;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.3); /* Bayangan lebih kuat */
            width: 90%;
            max-width: 450px;
            text-align: center;
            position: relative;
            transform: translateY(-20px); /* Mulai sedikit di atas */
            transition: transform 0.3s ease-out; /* Transisi untuk efek slide */
        }

        .modal.show .modal-content {
            transform: translateY(0); /* Geser ke posisi normal saat tampil */
        }

        .close-button {
            color: #888; /* Warna abu-abu yang lebih lembut */
            font-size: 30px;
            font-weight: bold;
            position: absolute;
            top: 10px;
            right: 15px;
            cursor: pointer;
            transition: color 0.2s ease;
        }

        .close-button:hover,
        .close-button:focus {
            color: #555;
            text-decoration: none;
        }

        /* Gaya tambahan untuk pesan sukses/gagal */
        .success-message {
            color: #2e7d32; /* Warna hijau dari header */
            font-weight: bold;
            font-size: 1.25rem; /* Ukuran font lebih besar */
            margin-bottom: 20px;
        }

        .error-message {
            color: #d32f2f; /* Warna merah yang lebih standar */
            font-weight: bold;
            font-size: 1.25rem;
            margin-bottom: 20px;
        }

        .modal-content p {
            margin: 0; /* Hapus margin default p */
        }

        .modal-content button {
            margin-top: 25px; /* Margin atas untuk tombol OK */
            background-color: #4CAF50;
            color: white;
            padding: 12px 25px; /* Padding lebih besar */
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1.05rem;
            transition: background-color 0.3s ease;
        }

        .modal-content button:hover {
            background-color: #45a049;
        }
    </style>

    <script type="text/javascript" src="https://cdn.emailjs.com/sdk/2.6.4/email.min.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" integrity="sha512-SnH5WK+bZxgPHs44uWIX+LLJAJ9/2PkPKZ5QiAj6Ta86w+fsb2TkcmfRyVX3pBnMFcV7oQPJkl9QevSCWr3W6A==" crossorigin="anonymous" referrerpolicy="no-referrer" />
</head>
<body>
    <header>
        <img src="Lambang Riqu.jfif" alt="Logo Rumah Tahfizh Riyadhul Qur'an">

        <div class="header-info">
            <div class="header-title">
                <i class="fas fa-pen-nib"></i>
                <span>Riyadhul Qur'an</span>
            </div>
            <small class="header-creator">Creator: Yusuf Abdullah</small>
        </div>

        <h1>Selamat Datang di Rumah Tahfizh Riyadhul Qur'an</h1>
    </header>

    <form id="formSantri">
        <input type="hidden" name="subject" value="Data Santri Baru">

        <div class="form-group">
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
        </div>

        <div class="form-group">
            <label for="pencapaian">Sebutkan Pencapaian Terakhir Santri:
                <small>Contoh: Tilawah-Al-Baqarah:150 / Tahfizh-Al-Baqarah:150</small>
            </label>
            <textarea id="pencapaian" name="pencapaian_santri" rows="4" placeholder="Tulis pencapaian di sini..." required></textarea>
        </div>

        <div class="form-group">
            <label for="jumlahHafalan">Jumlah Hafalan (Juz):</label>
            <input type="text" id="jumlahHafalan" name="jumlah_hafalan" placeholder="Contoh: 5 Juz" required>
        </div>

        <button type="submit" id="submitButton">Simpan Data</button>
    </form>

    <div id="myModal" class="modal">
        <div class="modal-content">
            <span class="close-button" aria-label="Tutup">&times;</span>
            <p id="modalMessage"></p>
            <button id="modalOkButton">OK</button>
        </div>
    </div>

    <audio autoplay>
        <source src="https://upload.wikimedia.org/wikipedia/commons/5/5c/Selamat_Datang_di_Rumah_Tahfizh_Riyadhul_Quran.ogg" type="audio/ogg">
        Browser Anda tidak mendukung audio.
    </audio>

    <script type="text/javascript">
        // Inisialisasi EmailJS
        (function() {
            // **Ini adalah Public Key Anda yang sudah saya pasang:**
            emailjs.init("BIXZsfN3M4WhyeMAv");
        })();

        // Dapatkan referensi elemen DOM menggunakan const untuk nilai yang tidak akan berubah
        const formSantri = document.getElementById("formSantri");
        const submitButton = document.getElementById("submitButton");
        const modal = document.getElementById("myModal");
        const modalMessage = document.getElementById("modalMessage");
        const closeButton = document.querySelector(".close-button");
        const modalOkButton = document.getElementById("modalOkButton");

        // Fungsi untuk menampilkan modal dengan pesan dan status (sukses/gagal)
        function showModal(message, isSuccess) {
            modalMessage.textContent = message;
            modalMessage.classList.remove('success-message', 'error-message');

            if (isSuccess) {
                modalMessage.classList.add('success-message');
            } else {
                modalMessage.classList.add('error-message');
            }

            modal.style.display = 'flex';
            setTimeout(() => {
                modal.classList.add('show');
            }, 10); // Memberi sedikit jeda untuk memastikan transisi CSS bekerja
        }

        // Fungsi untuk menyembunyikan modal
        function hideModal() {
            modal.classList.remove('show');
            modal.addEventListener('transitionend', function handler() {
                if (!modal.classList.contains('show')) {
                    modal.style.display = 'none';
                }
                modal.removeEventListener('transitionend', handler);
            });
        }

        // Tambahkan event listeners untuk menutup modal
        closeButton.addEventListener('click', hideModal);
        modalOkButton.addEventListener('click', hideModal);

        // Tutup modal jika pengguna mengklik di area gelap di luar konten modal
        window.addEventListener('click', function(event) {
            if (event.target === modal) {
                hideModal();
            }
        });

        // Tangkap event submit formulir
        formSantri.addEventListener("submit", async function(event) {
            event.preventDefault(); // Mencegah pengiriman formulir default

            // Nonaktifkan tombol submit dan tambahkan teks loading
            submitButton.disabled = true;
            submitButton.textContent = "Mengirim...";

            try {
                // Kirim formulir menggunakan EmailJS dengan ID Layanan dan Template Anda
                const response = await emailjs.sendForm("service_5l5ovxe", "template_q1igllh", this);

                console.log('SUCCESS!', response.status, response.text);
                showModal("Data santri berhasil disimpan!", true);
                formSantri.reset(); // Reset formulir setelah sukses

            } catch (error) {
                console.error('FAILED...', error);
                let errorMessage = "Gagal menyimpan data. Silakan coba lagi.";
                if (error.text) {
                    errorMessage += ` Detail: ${error.text}`;
                } else if (error.message) {
                    errorMessage += ` Detail: ${error.message}`;
                } else {
                    errorMessage += " Periksa koneksi internet Anda.";
                }
                showModal(errorMessage, false);
            } finally {
                // Selalu aktifkan kembali tombol submit setelah proses selesai
                submitButton.disabled = false;
                submitButton.textContent = "Simpan Data";
            }
        });
    </script>
</body>
</html>
