# valentine
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Be My Valentine 💖</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0;
      color: #333;
    }

    .card {
      background: white;
      padding: 30px;
      border-radius: 15px;
      text-align: center;
      width: 320px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
      position: relative;
    }

    h1 {
      margin-bottom: 15px;
    }

    input {
      padding: 10px;
      width: 80%;
      border-radius: 8px;
      border: 1px solid #ccc;
      margin-bottom: 15px;
    }

    button {
      padding: 10px 18px;
      border: none;
      border-radius: 20px;
      cursor: pointer;
      font-size: 16px;
      transition: 0.2s;
    }

    #submitAnswer {
      background: #ff5e78;
      color: white;
    }

    #yesBtn {
      background: #4CAF50;
      color: white;
      margin-right: 10px;
    }

    #noBtn {
      background: #ff4d4d;
      color: white;
      position: absolute;
    }

    .hidden {
      display: none;
    }

    .message {
      margin-top: 15px;
      font-size: 14px;
      color: #ff4d6d;
    }
  </style>
</head>
<body>

  <!-- Question Screen -->
  <div class="card" id="questionCard">
    <h1>Before we begin… 💌</h1>
    <p>What is the name I love calling you the most?</p>
    <input type="text" id="answer" placeholder="Your answer here 🥰">
    <br>
    <button id="submitAnswer">Submit</button>
    <div class="message" id="errorMsg"></div>
  </div>

  <!-- Valentine Screen -->
  <div class="card hidden" id="valentineCard">
    <h1>Will you be my Valentine? 💖</h1>
    <br>
    <button id="yesBtn">YES 💘</button>
    <button id="noBtn">NO 💔</button>
    <div class="message" id="noMsg"></div>
  </div>

  <!-- Final Screen -->
  <div class="card hidden" id="finalCard">
    <h1>YAYYYYY 💞</h1>
    <p>You just made me the happiest person ever 🥹💖</p>
    <p>Happy Valentine’s Day, Rani 🌹</p>
  </div>

<script>
  const submitAnswer = document.getElementById("submitAnswer");
  const answerInput = document.getElementById("answer");
  const errorMsg = document.getElementById("errorMsg");

  const questionCard = document.getElementById("questionCard");
  const valentineCard = document.getElementById("valentineCard");
  const finalCard = document.getElementById("finalCard");

  const noBtn = document.getElementById("noBtn");
  const yesBtn = document.getElementById("yesBtn");
  const noMsg = document.getElementById("noMsg");

  submitAnswer.onclick = () => {
    if (answerInput.value.trim().toLowerCase() === "rani") {
      questionCard.classList.add("hidden");
      valentineCard.classList.remove("hidden");
    } else {
      errorMsg.textContent = "Hmm… that’s not it 😜 Try again!";
    }
  };

  const messages = [
    "Heyyy that button is broken 😏",
    "Wrong choice babe 💕",
    "Come on, you know you want to 😘",
    "That NO is getting tired, try YES 😌",
    "My heart says YES 🥺💖"
  ];

  noBtn.onmouseover = () => {
    const card = valentineCard.getBoundingClientRect();

    const x = Math.random() * (card.width - 80);
    const y = Math.random() * (card.height - 40);

    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";

    noMsg.textContent = messages[Math.floor(Math.random() * messages.length)];
  };

  yesBtn.onclick = () => {
    valentineCard.classList.add("hidden");
    finalCard.classList.remove("hidden");
  };
</script>

</body>
</html>
