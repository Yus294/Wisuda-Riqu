<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Rumah Tahfizh Riyadhul Qur'an</title>

    <style>
        /* Atur box-sizing untuk semua elemen */
        * {
            box-sizing: border-box;
        }

        /* Styling untuk body halaman */
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

        /* Styling untuk header */
        header {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-top: 30px;
        }

        /* Styling untuk gambar logo di header */
        header img {
            max-width: 120px;
            height: auto;
        }

        /* Styling untuk judul utama (h1) */
        h1 {
            margin-top: 15px;
            margin-bottom: 20px;
            color: #2e7d32;
            text-align: center;
            font-size: 1.8rem;
            padding: 0 20px;
        }

        /* Styling untuk formulir */
        form {
            background-color: #ffffff;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            margin-bottom: 40px;
            width: 100%;
            max-width: 800px;
        }

        /* Styling untuk label formulir */
        label {
            display: block;
            margin-top: 15px;
            font-weight: bold;
            color: #444;
            text-align: center;
        }

        label small {
            display: block;
            text-align: center;
            margin-top: 5px;
            color: #777;
            font-weight: normal;
        }

        /* Styling untuk input teks, textarea, dan select */
        input[type="text"],
        textarea,
        select {
            width: 100%;
            padding: 12px;
            margin-top: 6px;
            border: 1px solid #ccc;
            border-radius: 8px;
            font-size: 1rem;
            text-align: center;
        }

        input::placeholder,
        textarea::placeholder,
        select::placeholder {
            text-align: center;
            color: #999;
        }

        textarea {
            resize: vertical;
        }

        /* Styling untuk tombol submit */
        button[type="submit"] {
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

        button[type="submit"]:hover {
            background-color: #388e3c;
        }

        /* Media Queries untuk responsivitas */
        @media screen and (max-width: 600px) {
            h1 {
                font-size: 1.5rem;
            }
            form
