
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Давай познакомимся</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      background: url('https://i.pinimg.com/originals/ba/48/b5/ba48b59ebadf8f0ff6c9c59d210c4ae4.jpg') no-repeat center center fixed;
      background-size: cover;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      font-family: 'Arial', sans-serif;
      color: white;
      text-align: center;
      padding: 20px;
    }

    .overlay {
      background: rgba(0, 0, 0, 0.6);
      border-radius: 20px;
      padding: 30px 20px;
      animation: fadeIn 1s ease-in-out;
      max-width: 90%;
    }

    h1 {
      font-size: 2rem;
      margin-bottom: 30px;
      animation: slideDown 0.6s ease-out;
    }

    .buttons {
      display: flex;
      flex-direction: column;
      gap: 15px;
    }

    button {
      padding: 15px 25px;
      font-size: 1.1rem;
      background-color: #fff;
      color: #000;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      transition: 0.3s ease;
    }

    button:hover {
      background-color: #eaeaea;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes slideDown {
      from { transform: translateY(-20px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }
  </style>
</head>
<body>
  <div class="overlay">
    <h1 id="question">Тебе уже есть 18?</h1>
    <div class="buttons">
      <button id="yesBtn">Да</button>
      <button id="noBtn">Нет</button>
    </div>
  </div>

  <script>
    const redirectUrl = "https://yourdomain.com/offer"; // Замените на свою ссылку

    const lang = navigator.language.startsWith('ru') ? 'ru' : 'en';
    const texts = {
      ru: {
        question: "Тебе уже есть 18?",
        yes: "Да",
        no: "Нет"
      },
      en: {
        question: "Are you 18 or older?",
        yes: "Yes",
        no: "No"
      }
    };

    document.getElementById('question').textContent = texts[lang].question;
    document.getElementById('yesBtn').textContent = texts[lang].yes;
    document.getElementById('noBtn').textContent = texts[lang].no;

    // Открытие во внешнем браузере
    document.getElementById('yesBtn').addEventListener('click', () => {
      const a = document.createElement('a');
      a.href = redirectUrl;
      a.target = "_blank";
      a.rel = "noopener noreferrer";
      document.body.appendChild(a);
      a.click();
      setTimeout(() => {
        window.open(redirectUrl, "_blank");
      }, 500);
    });

    document.getElementById('noBtn').addEventListener('click', () => {
      alert(lang === 'ru' ? 'Доступ ограничен' : 'Access denied');
    });
  </script>
</body>
</html>
