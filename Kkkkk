<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>CRITICAL SYSTEM ALERT</title>
<style>
html,body{
  margin:0;padding:0;height:100%;
  background:#000;color:#ff2b2b;
  font-family:Consolas,"Courier New",monospace;
  overflow:hidden;
}
#screen{
  text-align:center;
  padding-top:7vh;
}
h1{
  font-size:52px;
  text-shadow:0 0 35px red;
  animation:glitch 0.18s infinite;
}
#log{
  margin-top:25px;
  font-size:18px;
  height:180px;
}
.cursor::after{
  content:"█";
  animation:blink 0.8s infinite;
}
@keyframes blink{50%{opacity:0}}
@keyframes glitch{
  0%{transform:translate(0)}
  20%{transform:translate(-3px,3px)}
  40%{transform:translate(3px,-3px)}
  60%{transform:translate(-2px,2px)}
  80%{transform:translate(2px,-2px)}
  100%{transform:translate(0)}
}
.shake{
  animation:shake 0.15s infinite;
}
@keyframes shake{
  0%{transform:translate(0)}
  50%{transform:translate(3px,3px)}
  100%{transform:translate(0)}
}
.flash{
  animation:flash 0.3s infinite;
}
@keyframes flash{
  0%{background:#000}
  50%{background:#300}
  100%{background:#000}
}
.bar{
  width:60%;
  height:18px;
  border:1px solid red;
  margin:30px auto;
}
.fill{
  height:100%;
  width:0%;
  background:red;
  transition:width 0.6s;
}
.small{
  color:#777;
  font-size:12px;
}
</style>
</head>

<body>
<div id="screen">
  <h1>⚠ CRITICAL SYSTEM BREACH ⚠</h1>
  <div id="log" class="cursor"></div>

  <div class="bar">
    <div class="fill" id="fill"></div>
  </div>

  <div class="small">Security Monitor v5.9</div>
</div>

<script>
const lines = [
  "Initializing deep scan...",
  "Kernel access check...",
  "Unauthorized process detected",
  "Reading active memory blocks",
  "Analyzing connected interfaces",
  "External signal detected",
  "Security escalation in progress",
  "!!! WARNING !!!",
  "User activity detected",
  "FORCING CONNECTION SHUTDOWN"
];

let log = document.getElementById("log");
let fill = document.getElementById("fill");
let i = 0;

function typeLine(text, cb){
  let j=0;
  let line="";
  const t=setInterval(()=>{
    line+=text[j];
    log.innerHTML = line;
    j++;
    if(j>=text.length){
      clearInterval(t);
      setTimeout(cb,600);
    }
  },40);
}

function next(){
  if(i<lines.length){
    typeLine(lines[i],()=>{
      fill.style.width = Math.min((i+1)*10,100)+"%";
      if(i===4){
        document.body.classList.add("shake");
        if(navigator.vibrate) navigator.vibrate([200,100,200]);
      }
      if(i===7){
        document.body.classList.add("flash");
      }
      i++;
      next();
    });
  }else{
    end();
  }
}

function end(){
  document.body.classList.remove("shake");
  document.body.classList.remove("flash");
  document.body.innerHTML = `
    <div id="screen">
      <h1 style="color:white;text-shadow:0 0 40px red;">CONNECTION TERMINATED</h1>
      <p>Session forcefully closed.</p>
      <p style="color:#aaa">Do not repeat this action.</p>
      <p class="small">(Visual simulation only)</p>
    </div>
  `;
}

setTimeout(next,800);

// طلب ملء الشاشة لزيادة الرعب (اختياري)
document.body.addEventListener("click",()=>{
  if(document.documentElement.requestFullscreen){
    document.documentElement.requestFullscreen().catch(()=>{});
  }
},{once:true});
</script>
</body>
</html>
