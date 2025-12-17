# emoji.github.io
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Your Spirit Emoji ✨</title>

  <style>
    body {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(135deg, #fdfbfb, #ebedee);
      font-family: Arial, sans-serif;
      margin: 0;
      text-align: center;
    }

    h1 {
      font-size: 28px;
      margin-bottom: 20px;
      opacity: 0;
      animation: fadeIn 1.2s forwards;
    }

    #emoji {
      font-size: 120px;
      opacity: 0;
      animation: popIn 0.8s ease-out forwards;
      animation-delay: 1s;
    }

    @keyframes fadeIn {
      to { opacity: 1; }
    }

    @keyframes popIn {
      0% { transform: scale(0); opacity: 0; }
      70% { transform: scale(1.2); }
      100% { transform: scale(1); opacity: 1; }
    }
  </style>
</head>
<body>

  <h1>Your spirit emoji is…</h1>
  <div id="emoji"></div>

  <script>
    const emojis = [
      "😃","😆","😁","😉","😗","🤪","😏",
      "🙂‍↕️","🙂‍↔️","☹️","😭","😠",
      "🫣","🫡","🤔","🫢","🤫","🤥",
      "😮","🥱","🤮"
    ];

    const params = new URLSearchParams(window.location.search);
    const isNewScan = params.has("scan");

    let emoji = localStorage.getItem("spiritEmoji");

    if (isNewScan || !emoji) {
      emoji = emojis[Math.floor(Math.random() * emojis.length)];
      localStorage.setItem("spiritEmoji", emoji);
    }

    document.getElementById("emoji").textContent = emoji;
  </script>

</body>
</html>
