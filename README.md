<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine?</title>
    <style>
        /* General Page Styling */
        body {
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #ffc0cb; /* Pink background */
            font-family: 'Arial', sans-serif;
            overflow: hidden; /* Prevents scrollbars from floating hearts */
        }

        /* The Main Card Container */
        .container {
            text-align: center;
            z-index: 10;
            background: rgba(255, 255, 255, 0.9); /* Slightly more opaque for the image */
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            max-width: 90%;
            width: 400px; /* Fixed width to keep the image size nice */
        }

        h1 {
            color: #d32f2f;
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        /* Buttons */
        .btn-group {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            flex-wrap: wrap; 
            min-height: 80px;
        }

        button {
            padding: 15px 30px;
            font-size: 1.2rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.2s, background-color 0.2s;
        }

        #yes-btn {
            background-color: #4CAF50; /* Green */
            color: white;
            font-weight: bold;
        }

        #yes-btn:hover {
            background-color: #45a049;
            transform: scale(1.05);
        }

        #no-btn {
            background-color: #f44336; /* Red */
            color: white;
            font-weight: bold;
        }

        /* GIF Styling */
        .gif-container img {
            max-width: 100%;
            height: auto;
            border-radius: 15px;
            margin-top: 15px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        /* Classes to toggle visibility */
        .hidden {
            display: none;
        }

        /* Floating Hearts Animation Background */
        .heart {
            position: absolute;
            bottom: -50px;
            color: #ff4081;
            font-size: 24px;
            animation: floatUp 5s linear infinite;
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

    <div id="hearts-container"></div>

    <div class="container" id="question-page">
        <h1>May I be your Valentine? 🌹</h1>
        <div class="btn-group">
            <button id="yes-btn">Yes</button>
            <button id="no-btn">No</button>
        </div>
    </div>

    <div class="container hidden" id="thank-you-page">
        <h1>Thank you! 💖</h1>
        <p style="font-size: 1.2rem; color: #d32f2f;">I'm so happy! 🥰</p>
        
        <div class="gif-container">
            <img src="https://media0.giphy.com/media/v1.Y2lkPTZjMDliOTUycWp5NGR3aTQ0aDF0Mm82cXUzOWJvY2I5MGV5YnlnZ3E1dWtzb3gzMCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/KztT2c4u8mYYUiMKdJ/source.gif" alt="Cute Valentine GIF">
        </div>
    </div>

    <script>
        // Select elements
        const yesBtn = document.getElementById('yes-btn');
        const noBtn = document.getElementById('no-btn');
        const questionPage = document.getElementById('question-page');
        const thankYouPage = document.getElementById('thank-you-page');
        
        let currentScale = 1;

        // Logic for the 'No' button
        noBtn.addEventListener('click', () => {
            currentScale -= 0.2; // Decrease size
            noBtn.style.transform = `scale(${currentScale})`;

            if (currentScale < 0.2) {
               noBtn.style.display = 'none';
            }
        });

        // Logic for the 'Yes' button
        yesBtn.addEventListener('click', () => {
            questionPage.classList.add('hidden');
            thankYouPage.classList.remove('hidden');
            createManyHearts();
        });

        // Floating hearts logic
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤'; 
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 2 + 3 + 's'; 
            document.body.appendChild(heart);
            setTimeout(() => { heart.remove(); }, 5000);
        }

        setInterval(createHeart, 300);

        function createManyHearts() {
            for(let i=0; i<30; i++) {
                setTimeout(createHeart, i * 50);
            }
        }
    </script>

</body>
</html>
