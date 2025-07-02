# my-omikuji-site
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<title>おみくじ</title>
<style>
  body {
    background: #f6f6f6;
    font-family: "Hiragino Kaku Gothic ProN", Meiryo, sans-serif;
    text-align: center;
    padding: 50px;
  }
  h1 {
    margin-bottom: 30px;
    font-size: 2em;
  }
  .card {
    display: inline-block;
    background: white;
    padding: 40px 20px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    min-width: 200px;
    min-height: 150px;
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.5s ease, transform 0.5s ease;
  }
  .card.show {
    opacity: 1;
    transform: translateY(0);
  }
  .result-text {
    font-size: 2em;
    margin-top: 10px;
  }
  .draw-button {
    margin-top: 30px;
    padding: 10px 30px;
    font-size: 1em;
    border: none;
    background: #e91e63;
    color: white;
    border-radius: 5px;
    cursor: pointer;
  }
  .draw-button:hover {
    background: #c2185b;
  }
</style>
</head>
<body>

<h1>恋おみくじ</h1>

<div id="card" class="card">
  <div id="result" class="result-text">結果はこちら</div>
</div>

<button class="draw-button" onclick="draw()">おみくじを引く</button>

<script>
function draw() {
  const results = ["💖 大吉 💖", "💔 大凶 💔"];
  const index = Math.floor(Math.random() * results.length);
  const resultText = results[index];

  const card = document.getElementById("card");
  const result = document.getElementById("result");

  result.textContent = resultText;
  card.classList.remove("show");
  
  // 少し遅らせてアニメーション
  setTimeout(() => {
    card.classList.add("show");
  }, 50);
}
</script>

</body>
</html>
