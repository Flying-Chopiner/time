<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Countdown Timer</title>
    <style>
        body, html {
            height: 100%;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: Arial, sans-serif;
        }

        #countdown {
            text-align: center;
        }

        #timer {
            font-size: 2rem;
            margin: 20px 0;
        }

        button {
            padding: 10px 20px;
            font-size: 1rem;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="countdown">
        <h1>Countdown Timer</h1>
        <div id="timer">00:00:00</div>
        <button id="startButton">Start</button>
    </div>

    <script>
        document.getElementById('startButton').addEventListener('click', function() {
            var duration = 60 * 50; // Duration in seconds
            var countdownElement = document.getElementById('timer');
            var interval = setInterval(function() {
                var minutes = parseInt(duration / 60, 10);
                var seconds = parseInt(duration % 60, 10);

                minutes = minutes < 10 ? "0" + minutes : minutes;
                seconds = seconds < 10 ? "0" + seconds : seconds;

                countdownElement.textContent = minutes + ":" + seconds;

                if (--duration < 0) {
                    clearInterval(interval);
                    alert('Countdown finished!');
                }
            }, 1000);
        });
    </script>
</body>
</html>
