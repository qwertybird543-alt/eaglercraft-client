<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Eaglercraft Modern Client</title>
  <style>
    body {
      margin: 0;
      background: #0e0e11;
      color: white;
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }

    h1 {
      margin-bottom: 10px;
    }

    iframe {
      width: 90vw;
      height: 80vh;
      border: none;
      border-radius: 12px;
      box-shadow: 0 0 30px rgba(0,0,0,0.6);
    }

    .controls {
      margin-bottom: 10px;
    }

    input {
      padding: 6px;
      border-radius: 6px;
      border: none;
    }

    button {
      padding: 6px 10px;
      border-radius: 6px;
      border: none;
      cursor: pointer;
      background: #3b82f6;
      color: white;
    }

    button:hover {
      background: #2563eb;
    }
  </style>
</head>
<body>

<h1>Eaglercraft Modern Client</h1>

<div class="controls">
  <input id="packUrl" placeholder="Paste texture pack URL (zip)" size="40">
  <button onclick="loadClient()">Launch</button>
</div>

<iframe id="gameFrame"></iframe>

<script>
  function loadClient() {
    const pack = document.getElementById('packUrl').value;

    // Base Eaglercraft client URL (public mirror)
    let url = "https://eaglercraft.v1_8_8.html";

    // Inject texture pack via query param (custom loader support needed)
    if (pack) {
      url += "?texturepack=" + encodeURIComponent(pack);
    }

    document.getElementById('gameFrame').src = url;
  }
</script>

</body>
</html>
