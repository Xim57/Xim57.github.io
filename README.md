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

</head>
<body>

    <div id="hearts-container"></div>

    <div class="container" id="question-page">
        <h1>ARE YOU GONNA PLAY TODAY? 🧐</h1>
        <div class="btn-group">
            <button id="yes-btn">Yes</button>
            <button id="no-btn">No</button>
        </div>
    </div>

    <div class="container hidden" id="thank-you-page">
        <h1>YIPPIEEEE! 🥳</h1>
        <p style="font-size: 1.2rem; color: #d32f2f;">LET ME KNOW WHEN U ON 😼</p>
        
        <div class="gif-container">
            <img src="https://media.tenor.com/AU6-SVlvHxIAAAAM/tatatattatatatatatattat.gif" alt="Cat Shooting GIF">
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

    
    </script>

</body>
</html>
