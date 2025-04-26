<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>I'm Sorry</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      background: url('https://images.unsplash.com/photo-1558008258-631b5bd3647d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') no-repeat center center/cover;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-family: 'Poppins', sans-serif;
      text-align: center;
      overflow: hidden;
    }

    h1 {
      color: #fff;
      text-shadow: 2px 2px 5px #000;
      margin-bottom: 40px;
      padding: 0 20px;
      font-size: 6vw;
      max-width: 90%;
    }

    .buttons {
      position: relative;
      display: flex;
      flex-direction: row;
      gap: 20px;
      z-index: 10;
    }

    button {
      font-size: 5vw;
      padding: 12px 24px;
      min-width: 150px;
      max-width: 250px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 6px rgba(0,0,0,0.3);
    }

    #yes {
      background-color: #6ab04c;
      color: white;
    }

    #no {
      background-color: #eb4d4b;
      color: white;
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

    let scale = 1; // starting scale for "Yes" button

    function growYesButton() {
      scale += 0.5; // Increase the scale more dramatically
      yesBtn.style.transform = `scale(${scale})`;

      if (scale >= 8) { // if the Yes button is too big
        noBtn.style.display = 'none'; // Hide No button
      }
    }

    noBtn.addEventListener('click', growYesButton);

    yesBtn.addEventListener('click', () => {
      document.body.innerHTML = `
        <h1 style="color:white; text-shadow:2px 2px 5px #000; padding: 20px; font-size: 5vw;">
          Thank you for forgiving me.<br><br>
          I promise I'll be better.<br><br>
          I love you so much.
        </h1>
      `;
    });
  </script>

</body>
</html>
