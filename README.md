
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Welcome</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
      color: white;
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    .overlay {
      position: absolute;
      inset: 0;
      background-color: rgba(0, 0, 0, 0.5);
      z-index: 1;
    }

    .content {
      position: relative;
      z-index: 2;
      background: rgba(0, 0, 0, 0.6);
      padding: 30px 20px;
      border-radius: 20px;
      max-width: 90%;
      animation: fadeIn 1s ease-in-out;
    }

    h1 {
      font-size: 2rem;
      margin-bottom: 30px;
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
  </style>
</head>
<body>
  <div class="overlay"></div>
  <div class="content">
    <h1 id="question">Тебе уже есть 18?</h1>
    <div class="buttons">
      <button id="yesBtn">Да</button>
      <button id="noBtn">Нет</button>
    </div>
  </div>

  <script>
    const backgrounds = [
      "https://imgur.com/a/2hNXF86",
      "https://ibb.co/C3Z2v1kh",
      "https://ibb.co/XZZkC09K",
      "https://ibb.co/hFykSd6H",
      "https://ibb.co/hJJDXzFr"
    ];

    // Установка случайного фона
    document.body.style.backgroundImage = `url('${backgrounds[Math.floor(Math.random() * backgrounds.length)]}')`;

    // Определение языка
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

    const redirectUrl = "https://artemsaas.github.io/instatest"; // Замените на вашу ссылку

    document.getElementById('yesBtn').addEventListener('click', () => {
      const a = document.createElement('a');
      a.href = redirectUrl;
      a.target = "_blank";
      a.rel = "noopener noreferrer";
      document.body.appendChild(a);
      a.click();
    });

    document.getElementById('noBtn').addEventListener('click', () => {
      alert(lang === 'ru' ? 'Доступ ограничен' : 'Access denied');
    });
  </script>
</body>
</html>
