<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Halo Interaktif</title>
    <style>
        :root {
            --bg: #f5f5f5;
            --text: #222;
            --accent: #007BFF;
        }

        [data-theme="dark"] {
            --bg: #1c1c1c;
            --text: #f5f5f5;
            --accent: #00aaff;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            font-family: 'Segoe UI', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            transition: background 0.3s, color 0.3s;
        }

        .box {
            text-align: center;
            padding: 30px;
            background: rgba(255,255,255,0.1);
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            backdrop-filter: blur(10px);
        }

        input {
            padding: 10px;
            border-radius: 8px;
            border: 1px solid var(--accent);
            width: 70%;
            font-size: 16px;
            margin-bottom: 10px;
        }

        button {
            padding: 10px 20px;
            margin: 5px;
            font-size: 16px;
            background-color: var(--accent);
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
        }

        button:hover {
            opacity: 0.9;
        }

        .greeting {
            margin-top: 20px;
            font-size: 20px;
            opacity: 0;
            animation: fadeIn 1s forwards;
        }

        @keyframes fadeIn {
            to { opacity: 1; }
        }
    </style>
</head>
<body data-theme="light">
    <div class="box">
        <h2>Masukkan Namamu</h2>
        <input type="text" id="nama" placeholder="Contoh: Raka" />
        <br>
        <button onclick="sapa()">Sapa Saya</button>
        <button onclick="toggleTheme()">Ganti Tema</button>
        <div id="hasil" class="greeting"></div>
    </div>

    <script>
        function sapa() {
            const nama = document.getElementById('nama').value.trim();
            const hasil = document.getElementById('hasil');
            if (nama) {
                hasil.textContent = `Halo, ${nama}! Senang bertemu denganmu.`;
                hasil.style.animation = "fadeIn 1s forwards";
            } else {
                hasil.textContent = 'Tolong isi namamu dulu!';
                hasil.style.animation = "fadeIn 1s forwards";
            }
        }

        function toggleTheme() {
            const body = document.body;
            const current = body.getAttribute("data-theme");
            body.setAttribute("data-theme", current === "dark" ? "light" : "dark");
        }
    </script>
</body>
</html>
