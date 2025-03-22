<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Xả Stress</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: #cce7ff;
            font-family: Arial, sans-serif;
        }
        .explosion {
            position: absolute;
            font-size: 20px;
            font-weight: bold;
            color: red;
            animation: explode 1s ease-out;
        }
        @keyframes explode {
            0% { transform: scale(0); opacity: 1; }
            100% { transform: scale(2); opacity: 0; }
        }
    </style>
</head>
<body onclick="createExplosion(event)">
    <script>
        const subjects = ["Toán", "Văn", "Hóa", "Lý", "Sinh", "Sử", "Địa", "Anh", "Tin học"];
        
        function createExplosion(event) {
            const explosion = document.createElement("div");
            explosion.className = "explosion";
            explosion.innerText = subjects[Math.floor(Math.random() * subjects.length)];
            explosion.style.left = `${event.clientX}px`;
            explosion.style.top = `${event.clientY}px`;
            document.body.appendChild(explosion);
            
            setTimeout(() => explosion.remove(), 1000);
        }
    </script>
</body>
</html>
