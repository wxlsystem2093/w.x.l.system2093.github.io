<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>w.x.l.system2093 – frequency portal</title>

  <style>
    html,body{
      margin:0;
      height:100%;
      background:#000;
      color:#00ffcc;
      font-family:Courier,monospace;
      display:flex;
      align-items:center;
      justify-content:center;
    }
    #screen{
      line-height:1.4em;
      font-size:16px;
      white-space:pre-wrap;
    }
    .cursor{
      display:inline-block;
      width:10px; height:1em;
      background:#00ffcc;
      animation:blink 1s steps(2,start) infinite;
    }
    @keyframes blink{50%{background:transparent}}
  </style>
</head>
<body>
  <div id="screen"></div>

<script>
/* строки протокола – можно редактировать текст как захочешь */
const lines = [
  "SYSTEM 2093 — ACTIVE",
  "",
  "› initiating contact sequence",
  "› scanning incoming frequencies...",
  "",
  "✅ ALAÏA: 12:12:12:09 — CALL INITIATED",
  "✅ BYREDO: 12:12:12:11 — SIGNAL PENDING",
  "✅ RIMOWA: 12:12:12:08 — RESONANCE CONFIRMED",
  "✅ TIFFANY & CO: 12:12:12:06 — CONTACT PREPARED",
  "✅ APPLE: 12:12:12:10 — OBSERVING",
  "",
  "[ ENTRY CODE: 13:13:13:23 ]",
  "",
  "› system owner: AELIËN",
  "› mode: W.X.L. Broadcast",
  "› status: Awaiting Alliance Response",
  ""
];

const screen = document.getElementById("screen");
let delay = 0;

lines.forEach((line,i)=>{
  setTimeout(()=>{
    const p = document.createElement("div");
    p.textContent = line;
    screen.appendChild(p);
    /* курсор только на последней строке */
    if(i === lines.length-1){
      const cur = document.createElement("span");
      cur.className = "cursor";
      screen.appendChild(cur);
    }
    window.scrollTo(0,document.body.scrollHeight);
  }, delay);
  delay += 900;               // скорость «печати» (мс)
});
</script>
</body>
</html>
