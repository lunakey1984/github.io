<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <title>我的角色作品集 & 小舖</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      background-color: #f9f9f9;
      padding: 20px;
    }
    .character-container {
      margin: 20px auto;
      cursor: pointer;
      display: inline-block;
      transition: transform 0.1s ease;
    }
    /* 點擊時的角色跳動效果 */
    .character-container:active {
      transform: scale(1.1);
    }
    .character-img {
      width: 200px;
      height: auto;
      border-radius: 50%;
    }
    .dialog-box {
      margin-top: 10px;
      padding: 10px;
      background: #ffffff;
      border: 2px solid #333;
      border-radius: 10px;
      display: inline-block;
      min-width: 200px;
    }
    .btn-shop {
      margin-top: 30px;
      padding: 12px 24px;
      background-color: #00805a; /* 7-11 綠色風格 */
      color: white;
      text-decoration: none;
      font-weight: bold;
      border-radius: 25px;
      display: inline-block;
    }
  </style>
</head>
<body>

  <h1>歡迎來到我的作品集！</h1>
  <p>點擊下方角色跟他互動吧：</p>

  <!-- 角色互動區塊 -->
  <div class="character-container" onclick="talk()">
    <img src="your-character.png" alt="角色" class="character-img">
    <br>
    <div class="dialog-box" id="dialog">點我一下！</div>
  </div>

  <br>

  <!-- 賣貨便導流按鈕 -->
  <a href="https://myship.7-11.com.tw/your_shop_link" target="_blank" class="btn-shop">
    🛍️ 前往 7-11 賣貨便選購週邊
  </a>

  <!-- 聲音檔（免費放於相同目錄） -->
  <audio id="voice" src="voice.mp3"></audio>

  <script>
    const lines = [
      "你好呀！歡迎來到我的小天地！",
      "今天也有好好休息嗎？",
      "喜歡我的週邊的話，可以去賣貨便看看喔！",
      "點擊我真的會講話喔！"
    ];

    function talk() {
      // 隨機切換台詞
      const randomLine = lines[Math.floor(Math.random() * lines.length)];
      document.getElementById("dialog").innerText = randomLine;

      // 播放角色語音
      const audio = document.getElementById("voice");
      audio.currentTime = 0; // 重置播放時間
      audio.play();
    }
  </script>

</body>
</html>
