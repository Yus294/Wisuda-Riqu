
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rumah Tahfizh Riyadhul Qur'an</title>

    <style>
        /* Atur box-sizing untuk semua elemen */
        * {
            box-sizing: border-box;
        }

        /* Styling untuk body halaman */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; /* Font utama */
            background: linear-gradient(to bottom right, #e8f5e9, #ffffff); /* Gradien latar belakang */
            margin: 0; /* Tanpa margin di sekitar body */
            padding: 0; /* Tanpa padding di sekitar body */
            display: flex; /* Menggunakan flexbox untuk tata letak */
            flex-direction: column; /* Elemen ditumpuk secara vertikal */
            align-items: center; /* Pusatkan elemen secara horizontal */
            min-height: 100vh; /* Tinggi minimum halaman setinggi viewport */
        }

        /* Styling untuk header */
        header {
            display: flex; /* Menggunakan flexbox untuk tata letak */
            flex-direction: column; /* Elemen ditumpuk secara vertikal */
            align-items: center; /* Pusatkan semua elemen secara horizontal */
            margin-top: 30px; /* Margin atas */
        }

        /* Styling untuk gambar logo di header */
        header img {
            max-width: 120px; /* Lebar maksimum gambar */
            height: auto; /* Tinggi otomatis menjaga rasio aspek */
        }

        /* Styling untuk judul utama (h1) */
        h1 {
            margin-top: 15px; /* Margin atas */
            margin-bottom: 20px; /* Margin bawah */
            color: #2e7d32; /* Warna teks hijau tua */
            text-align: center; /* Pusatkan teks */
            font-size: 1.8rem; /* Ukuran font relatif */
            padding: 0 20px; /* Padding samping */
        }

        /* Styling untuk formulir */
        form {
            background-color: #ffffff; /* Latar belakang putih */
            padding: 25px; /* Padding di dalam formulir */
            border-radius: 15px; /* Sudut membulat */
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1); /* Bayangan lembut */
            margin-bottom: 40px; /* Margin bawah */
            width: 100%; /* Agar formulir mengambil lebar penuh yang tersedia */
            max-width: 800px; /* Menambahkan max-width yang lebih besar agar tidak terlalu melebar pada layar sangat lebar, namun tetap fleksibel */
        }

        /* Styling untuk label formulir */
        label {
            display: block; /* Menjadikan label sebagai blok elemen */
            margin-top: 15px; /* Margin atas */
            font-weight: bold; /* Teks tebal */
            color: #444; /* Warna teks abu-abu tua */
            text-align: center; /* Teks label rata tengah */
        }

        /* Styling untuk teks kecil di dalam label (seperti contoh) */
        label small {
            display: block; /* Penting untuk membuatnya menjadi elemen blok agar text-align bekerja */
            text-align: center; /* Pusatkan teks kecil */
            margin-top: 5px; /* Sedikit margin atas untuk pemisah visual */
            color: #777; /* Warna teks sedikit lebih terang */
            font-weight: normal; /* Kembali ke ketebalan normal */
        }

        /* Styling untuk input teks, textarea, dan select */
        input[type="text"],
        textarea,
        select {
            width: 100%; /* Lebar penuh dari parent (formulir) */
            padding: 12px; /* Padding di dalam input */
            margin-top: 6px; /* Margin atas */
            border: 1px solid #ccc; /* Border abu-abu tipis */
            border-radius: 8px; /* Sudut membulat */
            font-size: 1rem; /* Ukuran font relatif */
            text-align: center; /* Teks input dan select rata tengah */
        }

        /* Styling untuk placeholder text di semua input dan textarea */
        input::placeholder,
        textarea::placeholder,
        select::placeholder {
            text-align: center; /* Pusatkan teks placeholder */
            color: #999; /* Warna abu-abu yang lebih terang untuk placeholder */
        }

        /* Styling khusus untuk textarea agar bisa di-resize vertikal */
        textarea {
            resize: vertical;
        }

        /* Styling untuk tombol submit */
        button[type="submit"] { /* Gunakan selector type untuk lebih spesifik */
            margin-top: 25px; /* Margin atas */
            padding: 12px 25px; /* Padding di dalam tombol */
            background-color: #43a047; /* Warna latar belakang hijau */
            color: white; /* Warna teks putih */
            font-size: 1rem; /* Ukuran font relatif */
            border: none; /* Tanpa border */
            border-radius: 8px; /* Sudut membulat */
            cursor: pointer; /* Kursor berubah menjadi pointer saat di-hover */
            transition: background-color 0.3s ease; /* Transisi halus saat hover */
            width: 100%; /* Lebar penuh */
        }

        /* Efek hover untuk tombol */
        button[type="submit"]:hover {
            background-color: #388e3c; /* Warna latar belakang hijau lebih gelap saat di-hover */
        }

        /* Media Queries untuk responsivitas pada layar kecil (maks 600px) */
        @media screen and (max-width: 600px) {
            h1 {
                font-size: 1.5rem; /* Ukuran font lebih kecil untuk judul */
            }
            form {
                padding: 20px; /* Padding formulir lebih kecil */
            }
        }

        /* --- CSS untuk Modal Pop-up --- */
        .modal {
            display: none; /* Tersembunyi secara default */
            position: fixed; /* Tetap di layar */
            z-index: 1000; /* Paling atas, pastikan di atas elemen lain */
            left: 0;
            top: 0;
            width: 100%; /* Lebar penuh */
            height: 100%; /* Tinggi penuh */
            background-color: rgba(0,0,0,0.6); /* Background hitam transparan lebih gelap */
            justify-content: center; /* Pusatkan secara horizontal */
            align-items: center; /* Pusatkan secara vertikal */
            /* Animasi fade-in */
            opacity: 0;
            transition: opacity 0.3s ease-in-out;
        }

        .modal.show {
            opacity: 1;
            display: flex; /* Aktifkan flex saat tampil */
        }

        .modal-content {
            background-color: #fefefe;
            padding: 30px; /* Padding lebih besar */
            border-radius: 10px; /* Sedikit lebih bulat */
            box-shadow: 0 5px 15px rgba(0,0,0,0.3); /* Bayangan lebih jelas */
            width: 90%; /* Lebih lebar di mobile */
            max-width: 450px; /* Lebar maksimum */
            text-align: center;
            position: relative;
            transform: translateY(-20px); /* Mulai sedikit di atas */
            transition: transform 0.3s ease-out;
        }

        .modal.show .modal-content {
            transform: translateY(0); /* Geser ke posisi normal saat tampil */
        }


        .close-button {
            color: #aaa;
            font-size: 30px; /* Ukuran lebih besar */
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
            font-size: 1.2rem;
            margin-bottom: 15px; /* Tambah margin */
        }

        .error-message {
            color: #d32f2f; /* Warna merah yang lebih standar */
            font-weight: bold;
            font-size: 1.2rem;
            margin-bottom: 15px; /* Tambah margin */
        }

        .modal-content p {
            margin: 0; /* Hapus margin default p */
        }

        .modal-content button {
            margin-top: 20px; /* Margin atas untuk tombol OK */
            background-color: #4CAF50; /* Warna hijau standar */
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            transition: background-color 0.3s ease;
        }

        .modal-content button:hover {
            background-color: #45a049;
        }
    </style>

    <script src="https://cdn.emailjs.com/sdk/2.6.4/email.min.js"></script>
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
            <small>Contoh: Tilawah-Al-Baqarah:150 / Tahfizh-Al-Baqarah:150</small>
        </label>
        <textarea id="pencapaian" name="pencapaian_santri" rows="4" placeholder="Tulis pencapaian di sini..." required></textarea>

        <label for="jumlahHafalan">Jumlah Hafalan (Juz):</label>
        <input type="text" id="jumlahHafalan" name="jumlah_hafalan" placeholder="Contoh: 5 Juz" required>

        <button type="submit">Simpan Data</button>
    </form>

    <div id="myModal" class="modal">
        <div class="modal-content">
            <span class="close-button">&times;</span>
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
            // Ganti "4uIOwIvzW_BCIzayT" dengan User ID EmailJS Anda yang sebenarnya
            emailjs.init("4uIOwIvzW_BCIzayT");
        })();

        // Dapatkan elemen modal
        const modal = document.getElementById("myModal");
        const modalMessage = document.getElementById("modalMessage");
        const closeButton = document.getElementsByClassName("close-button")[0];
        const modalOkButton = document.getElementById("modalOkButton");

        // Fungsi untuk menampilkan modal dengan pesan tertentu
        function showModal(message, isSuccess) {
            modalMessage.textContent = message;
            modalMessage.classList.remove('success-message', 'error-message'); // Hapus kelas sebelumnya
            if (isSuccess) {
                modalMessage.classList.add('success-message');
            } else {
                modalMessage.classList.add('error-message');
            }
            modal.classList.add('show'); // Tambahkan kelas 'show' untuk menampilkan modal dan animasinya
        }

        // Fungsi untuk menyembunyikan modal
        function hideModal() {
            modal.classList.remove('show'); // Hapus kelas 'show' untuk menyembunyikan modal dan animasinya
            // Setelah transisi selesai, atur display ke 'none' agar tidak mengganggu interaksi lain
            modal.addEventListener('transitionend', function() {
                if (!modal.classList.contains('show')) {
                    modal.style.display = 'none';
                }
            }, { once: true }); // Hanya jalankan event listener sekali
            // Pastikan display diatur ke 'flex' sebelum menambahkan 'show' kembali
            if (modal.classList.contains('show')) {
                modal.style.display = 'flex';
            }
        }

        // Event listener untuk tombol (x) dan tombol OK
        closeButton.onclick = hideModal;
        modalOkButton.onclick = hideModal;

        // Event listener untuk klik di luar konten modal
        window.onclick = function(event) {
            if (event.target == modal) {
                hideModal();
            }
        };

        // Tangkap event submit formulir
        document.getElementById("formSantri").addEventListener("submit", function(event) {
            event.preventDefault(); // Mencegah pengiriman formulir default

            emailjs.sendForm("service_5l5ovxe", "template_q1igllh", this)
                .then(function(response) {
                    showModal("Data santri berhasil disimpan!", true); // Pesan sukses yang lebih spesifik
                    document.getElementById("formSantri").reset();
                }, function(error) {
                    // console.error("EmailJS Error:", error); // Untuk debugging: lihat error di console
                    showModal("Gagal menyimpan data. Silakan coba lagi atau periksa koneksi internet Anda.", false); // Pesan error yang lebih umum
                });
        });
    </script>
</body>
</html>
