<!DOCTYPE html>
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
      background: transparent;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-family: 'Poppins', sans-serif;
      text-align: center;
      overflow: hidden;
    }

    .background {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: url('https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260') no-repeat center center/cover;
      opacity: 0;
      animation: fadeIn 2s forwards;
      z-index: -1;
    }

    @keyframes fadeIn {
      to {
        opacity: 1;
      }
    }

    h1 {
      color: #fff;
      margin-bottom: 40px;
      padding: 0 20px;
      font-size: 5vw;
      max-width: 90%;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.7);
    }

    .buttons {
      position: relative;
      display: flex;
      gap: 20px;
    }

    button {
      font-size: 5vw;
      padding: 12px 24px;
      min-width: 100px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s ease;
      box-shadow: 0 4px 6px rgba(0,0,0,0.2);
      z-index: 1;
    }

    #yes {
      background-color: #27ae60;
      color: #fff;
    }

    #no {
      background-color: #e74c3c;
      color: #fff;
    }

    .thank-you {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 20px;
      color: #fff;
    }

    .cute-animal {
      width: 200px;
      height: 200px;
      background: url('https://cdn.pixabay.com/photo/2017/01/31/21/22/bear-2022131_1280.png') no-repeat center center/contain;
      animation: float 3s ease-in-out infinite;
      margin-bottom: 30px;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-20px); }
    }

    .tulip {
      width: 100px;
      height: 100px;
      background: url('https://cdn.pixabay.com/photo/2017/01/31/21/22/tulip-2022130_1280.png') no-repeat center center/contain;
      animation: fadeInUp 2s ease forwards;
      opacity: 0;
      margin-top: 20px;
    }

    @keyframes fadeInUp {
      0% {
        transform: translateY(50px);
        opacity: 0;
      }
      100% {
        transform: translateY(0);
        opacity: 1;
      }
    }

    .thank-message {
      font-size: 6vw;
      margin-top: 20px;
      text-shadow: 2px 2px 6px rgba(0,0,0,0.8);
      background: linear-gradient(45deg, #ff9a9e, #fad0c4, #fbc2eb, #a1c4fd);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: textFade 3s ease-in-out forwards;
    }

    @keyframes textFade {
      from { opacity: 0; }
      to { opacity: 1; }
    }
  </style>
</head>
<body>

  <div class="background" id="background"></div>

  <h1>Will you forgive me?</h1>

  <div class="buttons">
    <button id="yes">Yes</button>
    <button id="no">No</button>
  </div>

  <script>
    const noBtn = document.getElementById('no');
    const yesBtn = document.getElementById('yes');
    const background = document.getElementById('background');

    let yesBtnSize = 5; // initial font size in vw

    function growYesButton() {
      yesBtnSize += 2;
      yesBtn.style.fontSize = `${yesBtnSize}vw`;
      yesBtn.style.padding = `${12 + yesBtnSize}px ${24 + yesBtnSize}px`;

      if (yesBtnSize >= 30) {
        noBtn.style.display = 'none';
      }
    }

    noBtn.addEventListener('click', growYesButton);

    yesBtn.addEventListener('click', () => {
      // Change background to tulip garden
      background.style.backgroundImage = "url('https://images.unsplash.com/photo-1612369473565-63cbec9cf15e?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260')";
      
      document.body.innerHTML = `
        <div class="background" style="background: url('https://images.unsplash.com/photo-1612369473565-63cbec9cf15e?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260') no-repeat center center/cover; position:fixed; top:0; left:0; width:100%; height:100%; z-index:-1;"></div>
        <div class="thank-you">
          <div class="cute-animal"></div>
          <div class="tulip"></div>
          <div class="thank-message">
            Thank you for forgiving me.<br>
            Here's a tulip for you 🌷, my precious sunshine.<br>
            I love you more than words can ever say.
          </div>
        </div>
      `;
    });
  </script>

</body>
</html>
