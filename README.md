<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Be My Valentine?</title>
  <style>
      /*General Page Styling*/
      body {
        margin: 0;
        padding: 0;
        heigth: 100vh;
        display: flex;
        justify-content: center;
        alingn-items: center;
        background-color: #ffc0cb;
        font-family: 'Arial', sans-serif;
        overflow: hidden;
      }

      .container {
        text-align: center;
        z-index: 10;
        background: rgba(255, 255, 255, 0.8);
        padding: 40px;
        border-radius: 20px;
        box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        max-width: 90%;
      }

      h1 {
          color: #d32f2f;
          font-size: 2.5rem;
          margin-bottom: 30px;
      }
      .btn-group {
          display: flex;
          justify-content: center;
          align-items: center;
          gap: 20px;
          flex-wrap: wrap;
          min-height: 100px;
      }

      button {
          padding: 15px 30px;
          front-size: 1.2rem;
          border: none;
          border-radius: 50px;
          cursor: pointer;
          transition: transform 0.2s, background-color 0.2s;
      }

      #yes-btn {
          background-color: #4CAF50;
          color: white;
          font-weight: bold;
      }

      #yes-btn:hover {
          background-color: #45a049;
          transform: scale(1.05);
      }

      #no-btn {
          background-color: #f44336;
          color: white;
          font-weight: bold;
      }

      .hiden {
          display: none;
      }

      .heart {
          position: absolute;
          bottom: -50px;
          color: #ff4081;
          font-size: 20px;
          animation: floatingUp 5s linear infinite;
          opacity: 0.8;
          z-index: 1;
      }

      @keyframes floatUp {
          0% {
              transform: translateY(0) scale(1);
              opacity: 0.8;
          }
          100% {
              transform: translateY(-110vh) scale(1.5);
              opacity: 0;
          }
      }
  </style>
</head>
<body>

  <div id="hearts-container"></div>div>

  <div class="container" id="question-page">
      <h1>May I be your Valentine? 🌹</h1>
      <div class="btn-group">
          <button id="yes-btn">Yes</button>
          <button id="no-btn">No</button>
      </div>
  </div>

  <div class="container hidden" id="thank-you-page">
      <h1>YIPIEEEE!!!! 💗</h1>
      <p style="font-size: 1.5rem; color: #d32f2f;">THANK YOUU!!!! 🥰</p>
      <div style="font-size: 5rem; margin-top: 20px;">💙</div>
  </div>

  <script>

      const yesBtn = document.getElementById('yes-btn');
      const noBtn = document.getElementById('no-btn');
      const questionPage = document.getElementById('question-page');
      const thankYouPage = document.getElementById('thank-you-page');

      let currentScale = 1;

      noBtn.addEventListener('click', () => {
          currentScale -= 0.2;

          noBtn.style.transform = `scale(${currentScale})`;

          if (currentScale < 0.2) {
              noBtn.style.display = 'none';
          }
      });

      yesBtn.addEventListener('click', () => {

          questionPage.classList.add('hidden');

          thankYouPage.classList.remove('hidden');

          createManyHearts();
      });

      function createHearts() {
          const heart = document.createElement('div');
          heart.classList.add('heart');
          heart.innerHTML = '🩷';

          heart.style.left = Math.random() * 100 + 'vw';
          heart.style.animationDuration = Math.random() * 4 + 5 + 's';

          document.body.appendChild(heart);

          setTimeout(() => {
              heart.remove();
          }, 5000);
      }

      setInterval(createHeart, 300);

      function createManyHearts() {
          for(let i=0; i<30; i++) {
              setTimeout(createHeart, i * 50);
          }
      }
  </script)
    
</body)
    </html>
  

      
      
