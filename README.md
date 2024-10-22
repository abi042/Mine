<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Do you love me?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #ffecf0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            text-align: center;
            background-color: #fff;
            padding: 50px;
            border-radius: 15px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
            position: relative;
            height: 300px;
            width: 500px;
        }
        h1 {
            color: #e91e63;
            font-size: 2.5em;
        }
        .btn {
            font-size: 1.2em;
            padding: 10px 20px;
            margin: 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        #yesBtn {
            background-color: #4caf50;
            color: white;
        }
        #noBtn {
            background-color: #f44336;
            color: white;
            position: relative;
        }
        #message {
            font-size: 1.5em;
            color: #8e44ad;
            display: none;
            margin-top: 20px;
        }
        #error {
            font-size: 1.2em;
            color: red;
            display: none;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Do you love me?</h1>
        <button class="btn" id="yesBtn">Yes</button>
        <button class="btn" id="noBtn">No</button>
        <p id="message"></p>
        <p id="error">Error</p>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');
        const yesBtn = document.getElementById('yesBtn');
        const message = document.getElementById('message');
        const error = document.getElementById('error');

        noBtn.addEventListener('click', function() {
            // Show error message
            error.style.display = 'block';

            // Move "No" button to a random position on every click
            const container = document.querySelector('.container');
            const containerWidth = container.offsetWidth;
            const containerHeight = container.offsetHeight;

            const randomX = Math.floor(Math.random() * (containerWidth - noBtn.offsetWidth));
            const randomY = Math.floor(Math.random() * (containerHeight - noBtn.offsetHeight));

            noBtn.style.position = 'absolute';
            noBtn.style.left = `${randomX}px`;
            noBtn.style.top = `${randomY}px`;
        });

        yesBtn.addEventListener('click', function() {
            // Show love message when "Yes" is clicked
            message.innerHTML = 'Congratulations, I love you too 🥰 💞';
            message.style.display = 'block';
            error.style.display = 'none';
        });
    </script>

</body>
</html>