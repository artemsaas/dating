
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Start Chatting</title>
  <style>
    body {
      margin: 0;
      background: linear-gradient(135deg, #ff416c, #ff4b2b);
      color: #fff;
      font-family: 'Arial', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      height: 100vh;
      text-align: center;
      padding: 20px;
      animation: fadeIn 1s ease-in;
    }

    h1 {
      font-size: 2.2rem;
      margin-bottom: 40px;
      animation: slideDown 0.6s ease-out;
    }

    .buttons {
      display: flex;
      gap: 20px;
      animation: fadeIn 1.2s ease-in;
    }

    button {
      background: #fff;
      color: #000;
      font-size: 1.2rem;
      padding: 15px 35px;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      transition: 0.3s ease;
    }

    button:hover {
      background: #eee;
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
  <h1 id="question">Are you 18 or older?</h1>
  <div class="buttons">
    <button id="yesBtn">Yes</button>
    <button id="noBtn">No</button>
  </div>

  <script>
    const redirectUrl = "https://yourdomain.com/offer"; // замените на свою ссылку

    const lang = navigator.language.startsWith('ru') ? 'ru' : 'en';
    const texts = {
      ru: {
        question: "Тебе уже исполнилось 18?",
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
      alert(lang === 'ru' ? 'Доступ запрещён' : 'Access denied');
    });
  </script>
</body>
</html>
