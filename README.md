<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Forgive Me?</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      background: linear-gradient(135deg, #f5f7fa, #c3cfe2);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-family: 'Poppins', sans-serif;
      text-align: center;
      overflow: hidden;
    }

    h1 {
      color: #333;
      margin-bottom: 40px;
      padding: 0 20px;
      font-size: 6vw;
      max-width: 90%;
      animation: fadeIn 2s ease-in-out;
    }

    .buttons {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 15px;
    }

    button {
      font-size: 5vw;
      padding: 14px 28px;
      min-width: 150px;
      max-width: 300px;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    #yes {
      background-color: #6c5ce7;
      color: #fff;
    }

    #no {
      background-color: #ffeaa7;
      color: #2d3436;
    }

    button:hover {
      transform: scale(1.1);
    }

    /* Animation */
    @keyframes fadeIn {
      0% { opacity: 0; transform: scale(0.8);}
      100% { opacity: 1; transform: scale(1);}
    }
  </style>
</head>
<body>

  <h1>Will you forgive me?</h1>

  <div class="buttons">
    <button id="yes">Yes</button>
    <button id="no">No</button>
  </div>

  <script>
    const noBtn = document.getElementById('no');
    const yesBtn = document.getElementById('yes');

    let yesBtnSize = 5; // Initial size (vw)
    let clickCount = 0;

    noBtn.addEventListener('click', () => {
      clickCount++;
      yesBtnSize += 2;
      yesBtn.style.fontSize = `${yesBtnSize}vw`;
      yesBtn.style.padding = `${14 + clickCount * 4}px ${28 + clickCount * 6}px`;

      if (yesBtnSize >= 30) {
        noBtn.style.display = 'none'; // Hide No button after a few clicks
      }
    });

    yesBtn.addEventListener('click', () => {
      document.body.innerHTML = `
        <h1 style="color:#6c5ce7; font-size:6vw; animation:fadeIn 2s ease;">
          Thank you for forgiving me.<br><br>I promise to be better.<br><br>I love you.
        </h1>
      `;
    });
  </script>

</body>
</html>
