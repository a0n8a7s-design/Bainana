
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#171329">
<title>بيننا | مساحة مشتركة</title>
<style>
:root{
 --bg:#100e1d;--panel:#1b1830;--panel2:#24203c;
 --text:#f7f3ff;--muted:#aaa3c1;--pink:#ff77a8;
 --purple:#a58bff;--gold:#ffd477;--green:#73d6aa;
 --border:#37304f;--danger:#ff7777;
}
*{box-sizing:border-box}
body{
 margin:0;background:var(--bg);color:var(--text);
 font-family:Tahoma,Arial,sans-serif;line-height:1.7;
}
button,input,textarea{font:inherit}
button{cursor:pointer}
header{
 padding:20px 18px 12px;
 background:linear-gradient(135deg,#211936,#171329);
 border-bottom:1px solid var(--border);
}
.top{display:flex;justify-content:space-between;align-items:center;gap:10px}
.brand{font-size:25px;font-weight:bold;color:var(--pink)}
.brand span{color:var(--gold)}
.small{font-size:12px;color:var(--muted)}
.profile{
 margin-top:18px;padding:17px;border-radius:18px;
 background:linear-gradient(120deg,#36234a,#25203e);
 display:flex;justify-content:space-between;align-items:center;
}
.avatar{font-size:30px}
.profile h2{margin:0;font-size:18px}
.profile p{margin:3px 0;color:#d4c9e7;font-size:13px}
main{max-width:850px;margin:auto;padding:17px 14px 95px}
nav{
 position:fixed;bottom:0;left:0;right:0;z-index:5;
 display:flex;justify-content:space-around;gap:3px;
 background:#191629;border-top:1px solid var(--border);
 padding:8px 3px calc(8px + env(safe-area-inset-bottom));
}
nav button{
 background:none;border:0;color:var(--muted);
 font-size:11px;padding:5px 3px;flex:1;
}
nav button b{display:block;font-size:20px}
nav button.active{color:var(--pink)}
.page{display:none}
.page.active{display:block}
h2.section{font-size:19px;margin:22px 0 12px}
.grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:11px}
.card{
 background:var(--panel);border:1px solid var(--border);
 border-radius:17px;padding:15px;margin-bottom:11px;
}
.card h3{margin:0 0 5px;font-size:16px}
.card p{color:var(--muted);font-size:13px;margin:4px 0}
.stat{font-size:25px;font-weight:bold;color:var(--gold)}
.icon{font-size:27px;margin-bottom:5px}
.btn{
 border:0;border-radius:12px;padding:10px 15px;
 background:var(--pink);color:#251326;font-weight:bold;
}
.btn.secondary{background:var(--panel2);color:var(--text);border:1px solid var(--border)}
.btn.gold{background:var(--gold);color:#30240c}
.btn.green{background:var(--green);color:#10291e}
.btn.danger{background:var(--danger);color:#301010}
.btn:disabled{opacity:.45;cursor:not-allowed}
.full{width:100%}
input,textarea{
 width:100%;background:#100e1d;border:1px solid var(--border);
 color:var(--text);padding:12px;border-radius:11px;outline:none;
 margin:6px 0 12px;
}
textarea{resize:vertical;min-height:75px}
label{font-size:13px;color:var(--muted)}
.row{display:flex;gap:8px;align-items:center}
.row>*{min-width:0}
.row input{flex:1}
.progress{height:9px;background:#39324e;border-radius:20px;overflow:hidden;margin:10px 0}
.progress div{height:100%;background:linear-gradient(90deg,var(--pink),var(--purple));width:0}
.option{
 display:block;width:100%;text-align:right;margin:8px 0;
 padding:12px;background:var(--panel2);color:var(--text);
 border:1px solid var(--border);border-radius:12px;
}
.option:hover{border-color:var(--pink)}
.message{
 padding:10px 13px;background:var(--panel2);
 border-radius:14px;margin:9px 0;max-width:88%;
 overflow-wrap:anywhere;
}
.message .time{font-size:10px;color:var(--muted)}
.message.me{margin-right:auto;background:#493052}
#messages{height:300px;overflow-y:auto;padding:5px}
.flame{text-align:center;padding:22px}
.flame .big{font-size:65px}
.flame strong{font-size:35px;color:var(--gold);display:block}
.badge{
 display:inline-block;background:#332944;color:var(--gold);
 border:1px solid #57416a;padding:5px 9px;border-radius:30px;
 font-size:12px;margin:3px;
}
.empty{text-align:center;color:var(--muted);padding:25px}
footer{text-align:center;color:var(--muted);font-size:11px;margin:25px 0}
hr{border:0;border-top:1px solid var(--border);margin:17px 0}
@media(min-width:650px){.grid{grid-template-columns:repeat(3,minmax(0,1fr))}}
</style>
</head>
<body>
<header>
 <div class="top">
  <div>
   <div class="brand">بين<span>نا</span> ♡</div>
   <div class="small">مساحة للتعاون والمرح والتحديات</div>
  </div>
  <div class="small" id="today"></div>
 </div>
 <div class="profile">
  <div>
   <h2 id="welcome">أهلًا بكما ✨</h2>
   <p>كل يوم فرصة لصنع ذكرى جميلة</p>
  </div>
  <div class="avatar">🌙</div>
 </div>
</header>

<main>
<section id="home" class="page active">
 <h2 class="section">لوحة النشاط</h2>
 <div class="grid">
  <div class="card"><div class="icon">🔥</div><div class="stat" id="streak">0</div><p>أيام النشاط المتتالية على هذا الجهاز</p></div>
  <div class="card"><div class="icon">⭐</div><div class="stat" id="points">0</div><p>النقاط المكتسبة</p></div>
  <div class="card"><div class="icon">🎮</div><div class="stat" id="gamesCount">0</div><p>التحديات المكتملة</p></div>
  <div class="card"><div class="icon">✅</div><div class="stat" id="tasksCount">0</div><p>المهام المنجزة</p></div>
 </div>
 <h2 class="section">تحدي اليوم</h2>
 <div class="card">
  <div class="icon">💡</div>
  <h3 id="dailyTitle">تحدي اليوم</h3>
  <p id="dailyDesc"></p>
  <button class="btn full" onclick="completeDaily()">إنجاز التحدي +10 ⭐</button>
  <p id="dailyStatus"></p>
 </div>
 <h2 class="section">الوصول السريع</h2>
 <div class="grid">
  <button class="card" onclick="showPage('games')"><div class="icon">🎲</div><b>الألعاب</b><p>ابدأ تحديًا جديدًا</p></button>
  <button class="card" onclick="showPage('chat')"><div class="icon">💬</div><b>الدردشة</b><p>رسائل محفوظة محليًا</p></button>
  <button class="card" onclick="showPage('flame')"><div class="icon">🔥</div><b>الشعلة</b><p>تابع نشاطك اليومي</p></button>
  <button class="card" onclick="showPage('tasks')"><div class="icon">📝</div><b>المهام</b><p>خططوا معًا</p></button>
 </div>
</section>

<section id="games" class="page">
 <h2 class="section">الألعاب والتحديات 🎮</h2>
 <div class="grid">
  <button class="card" onclick="startQuiz()"><div class="icon">🧠</div><h3>اختبار المعرفة</h3><p>أسئلة متنوعة</p></button>
  <button class="card" onclick="startWouldYouRather()"><div class="icon">🤔</div><h3>ماذا تفضّل؟</h3><p>اختر بين خيارين</p></button>
  <button class="card" onclick="startRiddle()"><div class="icon">🔎</div><h3>لغز اليوم</h3><p>اختبر ذكاءك</p></button>
  <button class="card" onclick="startMemory()"><div class="icon">🧩</div><h3>تحدي الذاكرة</h3><p>تذكّر الرموز</p></button>
  <button class="card" onclick="startWord()"><div class="icon">🔤</div><h3>سلسلة الكلمات</h3><p>ابدأ بكلمة جديدة</p></button>
  <button class="card" onclick="startQuestion()"><div class="icon">💬</div><h3>سؤال اليوم</h3><p>سؤال للنقاش</p></button>
 </div>
 <div class="card" id="gameArea">
  <div class="empty">اختر لعبة من الأعلى لتبدأ.</div>
 </div>
</section>

<section id="flame" class="page">
 <h2 class="section">شعلة النشاط 🔥</h2>
 <div class="card flame">
  <div class="big">🔥</div>
  <strong id="flameDays">0</strong>
  <p>أيام النشاط المتتالية المسجلة على هذا الجهاز</p>
  <div class="progress"><div id="flameProgress"></div></div>
  <button class="btn gold full" onclick="recordActivity()">سجّل نشاط اليوم</button>
  <p id="flameMessage"></p>
 </div>
 <div class="card">
  <h3>كيف تعمل الشعلة؟</h3>
  <p>تزداد السلسلة عندما تسجل نشاطًا في يوم جديد. إذا مر يوم دون نشاط، تبدأ سلسلة جديدة عند العودة.</p>
  <p>هذه نسخة محلية؛ لا تتزامن تلقائيًا بين هاتفين.</p>
 </div>
</section>

<section id="chat" class="page">
 <h2 class="section">الدردشة 💬</h2>
 <div class="card">
  <p>رسائل محفوظة في هذا المتصفح فقط، وليست دردشة آنية بين جهازين.</p>
  <div id="messages"></div>
  <hr>
  <label>اسم المرسل</label>
  <input id="sender" maxlength="25" placeholder="مثلاً: الطرف الأول">
  <label>اكتب رسالتك</label>
  <div class="row">
   <input id="messageInput" maxlength="500" placeholder="اكتب رسالة...">
   <button class="btn" onclick="sendMessage()">إرسال</button>
  </div>
  <button class="btn secondary full" onclick="clearMessages()">مسح سجل الرسائل</button>
 </div>
</section>

<section id="tasks" class="page">
 <h2 class="section">المهام المشتركة 📝</h2>
 <div class="card">
  <label>أضف مهمة جديدة</label>
  <div class="row">
   <input id="taskInput" maxlength="100" placeholder="مثلاً: حل لغز اليوم">
   <button class="btn" onclick="addTask()">إضافة</button>
  </div>
 </div>
 <div id="taskList"></div>
</section>

<section id="achievements" class="page">
 <h2 class="section">الإنجازات 🏆</h2>
 <div class="card">
  <h3>مستوى النشاط</h3>
  <div class="stat" id="level">المبتدئ</div>
  <p id="levelDesc">ابدأ بجمع النقاط لفتح مستويات جديدة.</p>
  <div class="progress"><div id="levelProgress"></div></div>
 </div>
 <div class="card">
  <h3>الأوسمة</h3>
  <div id="badges"></div>
 </div>
 <div class="card">
  <h3>إدارة البيانات</h3>
  <p>يمكنك تصدير نسخة احتياطية أو استعادة بياناتك على هذا المتصفح.</p>
  <button class="btn secondary full" onclick="exportData()">تصدير نسخة احتياطية</button>
  <label>استعادة نسخة احتياطية JSON</label>
  <input type="file" id="importFile" accept=".json,application/json">
  <button class="btn secondary full" onclick="importData()">استعادة البيانات</button>
  <hr>
  <button class="btn danger full" onclick="resetApp()">إعادة ضبط التطبيق</button>
 </div>
</section>

<footer>بيننا © 2026 — مساحة رقمية للمرح والتعاون</footer>
</main>

<nav>
 <button class="active" data-page="home" onclick="showPage('home')"><b>⌂</b>الرئيسية</button>
 <button data-page="games" onclick="showPage('games')"><b>🎮</b>الألعاب</button>
 <button data-page="flame" onclick="showPage('flame')"><b>🔥</b>الشعلة</button>
 <button data-page="chat" onclick="showPage('chat')"><b>💬</b>الدردشة</button>
 <button data-page="achievements" onclick="showPage('achievements')"><b>🏆</b>الإنجازات</button>
</nav>

<script>
"use strict";

const KEY="bainana_complete_v1";
const today=()=>new Date().toLocaleDateString("en-CA");
const dateLabel=()=>new Date().toLocaleDateString("ar-IQ",{weekday:"long",day:"numeric",month:"long"});
const defaults={
 points:0,games:0,streak:0,lastActivity:"",
 dailyDate:"",dailyDone:false,
 messages:[],tasks:[],word:"",
 completed:0,answers:0
};
let data=loadData();

function loadData(){
 try{
  const saved=JSON.parse(localStorage.getItem(KEY)||"{}");
  return {...defaults,...saved};
 }catch(e){return {...defaults}}
}
function save(){
 localStorage.setItem(KEY,JSON.stringify(data));
 render();
}
function escapeHTML(s){
 return String(s).replace(/[&<>"']/g,c=>({
 "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"
 }[c]));
}
function showPage(id){
 document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"));
 document.getElementById(id).classList.add("active");
 document.querySelectorAll("nav button").forEach(b=>b.classList.toggle("active",b.dataset.page===id));
 if(id==="chat")renderMessages();
 if(id==="tasks")renderTasks();
}
function addPoints(n){
 data.points+=n;
 data.completed++;
 save();
}
function recordActivity(){
 const t=today();
 if(data.lastActivity===t){
  document.getElementById("flameMessage").textContent="لقد سجلت نشاط اليوم بالفعل! ✨";
  return;
 }
 const yesterday=new Date(Date.now()-86400000).toLocaleDateString("en-CA");
 data.streak=data.lastActivity===yesterday?data.streak+1:1;
 data.lastActivity=t;
 data.points+=5;
 document.getElementById("flameMessage").textContent="تم تسجيل نشاط اليوم بنجاح! +5 نقاط";
 save();
}
function completeDaily(){
 if(data.dailyDate===today()&&data.dailyDone){
  alert("أنجزت تحدي اليوم بالفعل!");
  return;
 }
 data.dailyDate=today();
 data.dailyDone=true;
 data.points+=10;
 data.completed++;
 save();
 alert("أحسنت! حصلت على 10 نقاط ⭐");
}
const dailyChallenges=[
 ["تحدي المعرفة","تبادلوا ثلاثة أسئلة ثقافية وحاولوا الإجابة عنها."],
 ["تحدي الكلمات","اختاروا كلمة واكتبوا خمس كلمات مرتبطة بها."],
 ["تحدي الذاكرة","تذكّروا خمسة أشياء تعلمتموها هذا الأسبوع."],
 ["تحدي الإبداع","اكتبوا فكرة لمشروع صغير يمكن تنفيذه."],
 ["تحدي التفكير","حلّوا لغزًا معًا دون الاستعانة بالإنترنت."]
];
function renderDaily(){
 const index=Math.floor(Date.now()/86400000)%dailyChallenges.length;
 document.getElementById("dailyTitle").textContent=dailyChallenges[index][0];
 document.getElementById("dailyDesc").textContent=dailyChallenges[index][1];
 document.getElementById("dailyStatus").textContent=
 data.dailyDate===today()&&data.dailyDone?"تم إنجاز تحدي اليوم ✓":"لم يُنجز بعد";
}
function startQuiz(){
 const questions=[
  ["ما عاصمة العراق؟",["بغداد","الموصل","البصرة"],0],
  ["كم عدد أيام الأسبوع؟",["خمسة","سبعة","ثمانية"],1],
  ["ما الكوكب المعروف بالكوكب الأحمر؟",["الزهرة","المريخ","المشتري"],1],
  ["ما ناتج 9 × 8؟",["72","81","64"],0],
  ["ما أكبر محيط على الأرض؟",["الأطلسي","الهندي","الهادئ"],2]
 ];
 let i=0,score=0;
 const area=document.getElementById("gameArea");
 function draw(){
  if(i>=questions.length){
   area.innerHTML=`<h3>انتهى الاختبار 🎉</h3><p>نتيجتك: ${score} من ${questions.length}</p><button class="btn" onclick="startQuiz()">إعادة اللعب</button>`;
   data.games++;data.points+=score*3+5;save();return;
  }
  const q=questions[i];
  area.innerHTML=`<p>السؤال ${i+1} من ${questions.length}</p><h3>${q[0]}</h3>`+
   q[1].map((a,j)=>`<button class="option" onclick="answerQuiz(${j})">${a}</button>`).join("");
 }
 window.answerQuiz=function(n){
  if(n===questions[i][2])score++;
  i++;draw();
 };
 draw();
}
function startWouldYouRather(){
 const pairs=[
  ["السفر إلى الماضي","السفر إلى المستقبل"],
  ["قراءة كتاب جديد","تعلم مهارة جديدة"],
  ["العيش قرب البحر","العيش قرب الجبال"],
  ["رحلة طويلة","يوم هادئ في المنزل"],
  ["العمل ضمن فريق","العمل بشكل مستقل"]
 ];
 const p=pairs[Math.floor(Math.random()*pairs.length)];
 document.getElementById("gameArea").innerHTML=
 `<h3>ماذا تفضّل؟ 🤔</h3>
 <button class="option" onclick="chooseRather(this)">${p[0]}</button>
 <button class="option" onclick="chooseRather(this)">${p[1]}</button>
 <p id="ratherResult"></p>`;
}
function chooseRather(btn){
 document.querySelectorAll("#gameArea .option").forEach(b=>b.disabled=true);
 document.getElementById("ratherResult").textContent="اختيار جميل! ناقشوا أسباب الاختيار.";
 data.games++;data.points+=5;save();
}
function startRiddle(){
 const riddles=[
  ["شيء كلما أخذت منه كبر، فما هو؟","الحفرة"],
  ["له أسنان ولا يعض، فما هو؟","المشط"],
  ["ما الشيء الذي يكتب ولا يقرأ؟","القلم"],
  ["ما الذي يسمع بلا أذن ويتكلم بلا لسان؟","الصدى"]
 ];
 const r=riddles[Math.floor(Math.random()*riddles.length)];
 document.getElementById("gameArea").innerHTML=
 `<h3>لغز 🔎</h3><p>${r[0]}</p>
 <input id="riddleAnswer" placeholder="اكتب إجابتك">
 <button class="btn full" onclick="checkRiddle('${r[1]}')">تحقق من الإجابة</button>
 <p id="riddleResult"></p>`;
}
window.checkRiddle=function(answer){
 const val=document.getElementById("riddleAnswer").value.trim();
 const result=document.getElementById("riddleResult");
 if(val===answer||val.includes(answer)){
  result.textContent="إجابة صحيحة! +8 نقاط 🎉";
  data.points+=8;data.games++;save();
 }else result.textContent="ليست الإجابة الصحيحة، حاول مرة أخرى.";
};
function startMemory(){
 const emojis=["🌙","⭐","🌸","🍀","🦋"];
 const chosen=emojis.sort(()=>Math.random()-.5).slice(0,4);
 const area=document.getElementById("gameArea");
 area.innerHTML=`<h3>تحدي الذاكرة 🧩</h3><p>احفظ هذه الرموز لمدة ثلاث ثوانٍ:</p>
 <div style="font-size:35px;text-align:center">${chosen.join(" ")}</div>
 <button class="btn full" id="hideMemory">إخفاء الرموز</button>
 <div id="memoryInput"></div>`;
 document.getElementById("hideMemory").onclick=()=>{
  area.querySelector("div").textContent="❔ ❔ ❔ ❔";
  document.getElementById("memoryInput").innerHTML=
  `<p>اكتب الرموز التي تتذكرها:</p><input id="memoryAnswer" placeholder="مثلاً 🌙 ⭐ 🌸 🍀">
  <button class="btn full" onclick="checkMemory()">تحقق</button>`;
 };
 window.checkMemory=()=>{
  const val=document.getElementById("memoryAnswer").value;
  const count=chosen.filter(x=>val.includes(x)).length;
  area.querySelector("#memoryInput").innerHTML=`<p>تذكرت ${count} من 4 رموز.</p>`;
  data.games++;data.points+=count*2;save();
 };
}
function startWord(){
 document.getElementById("gameArea").innerHTML=
 `<h3>سلسلة الكلمات 🔤</h3><p>اكتب كلمة تبدأ بآخر حرف من الكلمة السابقة.</p>
 <p>الكلمة السابقة: <b id="lastWord">${escapeHTML(data.word||"ابدأ بأي كلمة")}</b></p>
 <input id="newWord" maxlength="30" placeholder="اكتب كلمة">
 <button class="btn full" onclick="submitWord()">إرسال الكلمة</button><p id="wordResult"></p>`;
}
window.submitWord=()=>{
 const input=document.getElementById("newWord");
 const word=input.value.trim();
 if(word.length<2)return;
 if(data.word){
  const last=[...data.word].at(-1);
  if(word[0]!==last){
   document.getElementById("wordResult").textContent="ابدأ بحرف: "+last;
   return;
  }
 }
 data.word=word;
 data.points+=3;data.games++;
 save();
 document.getElementById("wordResult").textContent="ممتاز! +3 نقاط";
 startWord();
};
function startQuestion(){
 const qs=[
 "ما المهارة التي تتمنى إتقانها؟",
 "ما أجمل مكان تتمنى زيارته؟",
 "ما الكتاب الذي ترغب في قراءته؟",
 "ما فكرة المشروع التي تود تنفيذها؟",
 "ما الشيء الجديد الذي تعلمته مؤخرًا؟"
 ];
 const q=qs[Math.floor(Math.random()*qs.length)];
 document.getElementById("gameArea").innerHTML=
 `<h3>سؤال للنقاش 💬</h3><p style="font-size:18px">${q}</p>
 <button class="btn secondary" onclick="startQuestion()">سؤال آخر</button>`;
}
function sendMessage(){
 const input=document.getElementById("messageInput");
 const sender=document.getElementById("sender").value.trim()||"مستخدم";
 const body=input.value.trim();
 if(!body)return;
 data.messages.push({sender,body,time:new Date().toLocaleString("ar-IQ")});
 input.value="";save();renderMessages();
}
function renderMessages(){
 const box=document.getElementById("messages");
 box.innerHTML=data.messages.length?data.messages.map(m=>
 `<div class="message"><b>${escapeHTML(m.sender)}</b><div>${escapeHTML(m.body)}</div><div class="time">${escapeHTML(m.time)}</div></div>`
 ).join(""):`<div class="empty">لا توجد رسائل بعد.</div>`;
 box.scrollTop=box.scrollHeight;
}
function clearMessages(){
 if(confirm("هل تريد حذف جميع الرسائل؟")){
  data.messages=[];save();renderMessages();
 }
}
function addTask(){
 const input=document.getElementById("taskInput");
 const title=input.value.trim();
 if(!title)return;
 data.tasks.push({title,done:false});
 input.value="";save();renderTasks();
}
function toggleTask(i){
 data.tasks[i].done=!data.tasks[i].done;
 if(data.tasks[i].done)data.points+=3;
 save();renderTasks();
}
function deleteTask(i){
 data.tasks.splice(i,1);save();renderTasks();
}
function renderTasks(){
 document.getElementById("taskList").innerHTML=data.tasks.length?
 data.tasks.map((t,i)=>`<div class="card">
 <div class="row">
 <input type="checkbox" ${t.done?"checked":""} onchange="toggleTask(${i})" style="width:20px;margin:0">
 <div style="flex:1;${t.done?"text-decoration:line-through;color:var(--muted)":""}">${escapeHTML(t.title)}</div>
 <button class="btn danger" onclick="deleteTask(${i})">حذف</button>
 </div></div>`).join(""):`<div class="empty">لا توجد مهام. أضف أول مهمة!</div>`;
}
function renderAchievements(){
 const levels=[
  ["المبتدئ",0,49],["المستكشف",50,149],
  ["المبدع",150,299],["المتميز",300,599],["الخبير",600,Infinity]
 ];
 const current=levels.find(x=>data.points>=x[1]&&data.points<=x[2]);
 document.getElementById("level").textContent=current[0];
 document.getElementById("levelDesc").textContent="للوصول إلى المستوى التالي، واصل إنجاز التحديات.";
 const next=current[2]===Infinity?data.points:current[2]+1;
 const prev=current[1];
 const pct=current[2]===Infinity?100:Math.min(100,(data.points-prev)/(next-prev)*100);
 document.getElementById("levelProgress").style.width=pct+"%";
 const badges=[
  ["🌱","أول نشاط",data.streak>=1],
  ["🔥","ثلاثة أيام",data.streak>=3],
  ["⭐","50 نقطة",data.points>=50],
  ["🏆","100 نقطة",data.points>=100],
["🎮","خمس ألعاب",data.games>=5],
  ["✅","خمس مهام",data.tasks.filter(t=>t.done).length>=5]
 ];
 document.getElementById("badges").innerHTML=badges.map(b=>
 `<span class="badge" style="opacity:${b[2]?1:.35}">${b[0]} ${b[1]}</span>`
 ).join("");
}
function render(){
 document.getElementById("points").textContent=data.points;
 document.getElementById("streak").textContent=data.streak;
 document.getElementById("flameDays").textContent=data.streak;
 document.getElementById("gamesCount").textContent=data.games;
 document.getElementById("tasksCount").textContent=data.tasks.filter(t=>t.done).length;
 document.getElementById("flameProgress").style.width=Math.min(100,data.streak/7*100)+"%";
 renderDaily();renderAchievements();renderTasks();
}
function exportData(){
 const blob=new Blob([JSON.stringify(data,null,2)],{type:"application/json"});
 const url=URL.createObjectURL(blob);
 const a=document.createElement("a");
 a.href=url;a.download="bainana-backup.json";a.click();
 URL.revokeObjectURL(url);
}
function importData(){
 const file=document.getElementById("importFile").files[0];
 if(!file){alert("اختر ملف النسخة الاحتياطية أولًا.");return}
 const reader=new FileReader();
 reader.onload=()=>{
  try{
   const imported=JSON.parse(reader.result);
   if(!imported||typeof imported!=="object")throw Error();
   data={...defaults,...imported};save();alert("تم استعادة البيانات.");
  }catch(e){alert("الملف غير صالح.");}
 };
 reader.readAsText(file);
}
function resetApp(){
 if(!confirm("سيتم حذف جميع بيانات التطبيق من هذا الجهاز. هل أنت متأكد؟"))return;
 localStorage.removeItem(KEY);data={...defaults};save();
 alert("تمت إعادة ضبط التطبيق.");
}
document.getElementById("today").textContent=dateLabel();
render();
renderMessages();
</script>
</body>
</html>
