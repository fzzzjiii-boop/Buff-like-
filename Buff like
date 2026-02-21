<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Buff Like FF</title>
<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #0b0b0b;
  color: #00ffd5;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.container {
  width: 320px;
  background: #111;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 0 15px #00ffd5;
  text-align: center;
}

h2 {
  margin-bottom: 20px;
}

input {
  width: 100%;
  padding: 10px;
  margin: 8px 0;
  border-radius: 8px;
  border: none;
  outline: none;
}

button {
  width: 100%;
  padding: 12px;
  margin-top: 10px;
  background: #00ffd5;
  color: #000;
  border: none;
  border-radius: 8px;
  font-weight: bold;
  cursor: pointer;
}

.error {
  color: red;
  font-size: 13px;
}

/* Popup */
.popup {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.8);
  display: none;
  justify-content: center;
  align-items: center;
}

.popup-box {
  background: #111;
  padding: 20px;
  border-radius: 10px;
  width: 300px;
  position: relative;
  box-shadow: 0 0 15px #00ffd5;
}

.close {
  position: absolute;
  right: 10px;
  top: 5px;
  color: red;
  cursor: pointer;
  font-size: 18px;
}

/* Trang buff */
#buffPage {
  display: none;
}

.code {
  color: lime;
  font-size: 13px;
  text-align: left;
  margin-top: 10px;
}
</style>
</head>

<body>

<!-- Trang 1 -->
<div class="container" id="page1">
  <h2>Buff Like FF</h2>

  <input type="text" id="gameId" placeholder="Nhập ID game">
  <div class="error" id="idError"></div>

  <input type="text" id="likeAmount" placeholder="Nhập số like">
  <div class="error" id="likeError"></div>

  <button onclick="startBuff()">Bắt đầu buff like</button>
</div>

<!-- Popup kiểm tra ID -->
<div class="popup" id="popup">
  <div class="popup-box">
    <div class="close" onclick="closePopup()">✖</div>
    <p>Hãy kiểm tra lại ID game</p>
    <button onclick="confirmId()">Không có vấn đề gì về ID game</button>
  </div>
</div>

<!-- Trang 2 -->
<div class="container" id="buffPage">
  <h2 id="buffTitle"></h2>
  <p>Đang tiến hành buff like...</p>

  <div class="code">
    Connecting server...<br>
    Bypassing system...<br>
    Inject like data...<br>
    Processing...
  </div>

  <h3 id="countdown">100</h3>
  <p id="doneText"></p>
</div>

<script>
let savedId = "";
let count = 100;
let timer;

function startBuff() {
  let id = document.getElementById("gameId").value.trim();
  let like = document.getElementById("likeAmount").value.trim();
  let idError = document.getElementById("idError");
  let likeError = document.getElementById("likeError");

  idError.innerText = "";
  likeError.innerText = "";

  if (!/^[0-9]+$/.test(id) || id.length < 8 || id.length > 13) {
    idError.innerText = "ID game không hợp lệ";
    return;
  }

  if (!/^[0-9]+$/.test(like)) {
    likeError.innerText = "Số like phải là số";
    return;
  }

  savedId = id;
  document.getElementById("popup").style.display = "flex";
}

function closePopup() {
  document.getElementById("popup").style.display = "none";
}

function confirmId() {
  document.getElementById("popup").style.display = "none";
  document.getElementById("page1").style.display = "none";
  document.getElementById("buffPage").style.display = "block";
  document.getElementById("buffTitle").innerText =
    "ID " + savedId + " đang buff like";

  startCountdown();
}

function startCountdown() {
  timer = setInterval(() => {
    document.getElementById("countdown").innerText = count;
    count--;

    if (count < 1) {
      clearInterval(timer);
      document.getElementById("doneText").innerText =
        "Đã buff like thành công, hãy vào game";
    }
  }, 2000);
}
</script>

</body>
</html>
