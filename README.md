<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Guess the Number Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f5f5f5;
      padding: 50px;
    }
    h1 {
      color: #333;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
      margin: 10px;
    }
    #message {
      margin-top: 20px;
      font-size: 18px;
      color: #007700;
    }
  </style>
</head>
<body>

  <h1>Guess the Number!</h1>
  <p>I'm thinking of a number between 1 and 100.</p>
  <input type="number" id="guess" placeholder="Enter your guess" min="1" max="100">
  <button onclick="checkGuess()">Submit Guess</button>
  <p id="message"></p>

  <script>
    const secretNumber = Math.floor(Math.random() * 100) + 1;
    let attempts = 0;

    function checkGuess() {
      const userGuess = parseInt(document.getElementById('guess').value);
      attempts++;

      const message = document.getElementById('message');

      if (isNaN(userGuess) || userGuess < 1 || userGuess > 100) {
        message.textContent = "Please enter a number between 1 and 100.";
        message.style.color = "red";
      } else if (userGuess < secretNumber) {
        message.textContent = "Too low! Try again.";
        message.style.color = "#aa0000";
      } else if (userGuess > secretNumber) {
        message.textContent = "Too high! Try again.";
        message.style.color = "#aa0000";
      } else {
        message.textContent = `🎉 Congratulations! You guessed it in ${attempts} tries.`;
        message.style.color = "green";
      }
    }
  </script>

</body>
</html>
