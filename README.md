<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Возрастное подтверждение</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      background: url('https://i.postimg.cc/K4SdWXXc/unique-3382269592165547891-48077572578.jpg') center/cover no-repeat;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      color: #fff;
      position: relative;
      overflow: hidden;
    }

    .overlay {
      position: absolute;
      inset: 0;
      background: rgba(0, 0, 0, 0.6);
      z-index: 1;
    }

    .content {
      position: relative;
      z-index: 2;
      background: rgba(0, 0, 0, 0.7);
      padding: 30px 20px;
      border-radius: 16px;
      max-width: 90%;
      animation: fadeIn 1s ease-in-out;
    }

    h1 {
      font-size: 2rem;
      margin-bottom: 20px;
    }

    a.button {
      display: inline-block;
      padding: 16px 30px;
      background-color: #fff;
      color: #000;
      border-radius: 12px;
      font-size: 1.1rem;
      font-weight: bold;
      text-decoration: none;
      transition: background-color 0.3s;
      margin-top: 20px;
    }

    a.button:hover {
      background-color: #ddd;
    }

    .note {
      margin-top: 20px;
      font-size: 0.9rem;
      color: #ccc;
      max-width: 300px;
      margin-left: auto;
      margin-right: auto;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <div class="overlay"></div>
  <div class="content">
    <h1>Тебе уже есть 18 лет?</h1>
    <a class="button" href="https://artemsaas.github.io/lendtt" target="_blank" rel="noopener noreferrer">
      Да, мне есть 18
    </a>
    <div class="note">
      ⚠️ Если ссылка открылась внутри TikTok, нажми ⋮ или "..." в правом верхнем углу и выбери<br><strong>«Открыть в браузере»</strong>
    </div>
  </div>
</body>
</html>
