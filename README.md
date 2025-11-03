<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Exam Clock | MSA</title>

<link href="https://fonts.googleapis.com/css2?
family=Poppins:wght@300;400;600;700&
family=Share+Tech+Mono&
family=Chakra+Petch:wght@700&
family=Orbitron:wght@700&
family=Rajdhani:wght@700&
family=Roboto+Mono:wght@700&
display=swap" rel="stylesheet">

<style>
html, body {
  margin:0;
  height:100%;
  font-family: 'Poppins', sans-serif;
  background:#f1f2e1;
}
body {
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  height:100%;
}

/* Setup Screen */
#setupScreen {
  display:flex;
  flex-direction:column;
  width:100%;
  max-width:1000px;
  background:#fff;
  padding:20px;
  box-sizing:border-box;
  border-radius:12px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.15);
}

#setupScreen h1 {
  text-align:center;
  font-size:2em;
  margin-bottom:20px;
  color: #00a29f;
}

.fields-row {
  display:flex;
  gap:10px;
  margin-bottom:15px;
}

.exam-col {
  flex:1;
  background:#e0e0e0;
  padding:10px;
  border-radius:8px;
  display:flex;
  flex-direction:column;
  gap:5px;
}

.exam-col label {
  font-size:0.9em;
  font-weight:600;
}

.exam-col input, .exam-col select {
  padding:6px 8px;
  font-size:1em;
  border-radius:5px;
  border:1px solid #ccc;
}

.buttons-row {
  display:flex;
  align-items:center;
  gap:10px;
}

.buttons-row button {
  padding:8px 12px;
  font-size:1em;
  border:none;
  border-radius:6px;
  background:#00a29f;
  color:#fff;
  cursor:pointer;
}

.buttons-row label {
  font-size:0.9em;
  display:flex;
  align-items:center;
  gap:5px;
}

/* Display Screen */
#displayScreen {
  display:none;
  flex:1;
  flex-direction:column;
  width:100%;
  height:100%;
  cursor:pointer;
}

/* Header */
.header { 
  flex:3; 
  display:flex; 
  width:100%;
}
.header-left { 
  flex:46%; 
  display:flex; 
  flex-direction:column; 
  justify-content:space-between; 
  padding:5px; 
  background:#f1f2e1;
}






.header-left div {
  display: flex;
  align-items: center;
  justify-content: center;
  color: #00a29f;
  font-weight: bold;
}

#line1, #line3 {
  font-size: 1.2vw; /* normal size */
}

#line2, #line4 {
  font-size: 1vw; /* larger size */
}

#line4 {
  font-size: 1vw; /* larger size */
  text-align: center; /* ensure multi-line is centered */
  line-height: 1.2em; /* optional, to make lines closer together */
}





.header-left {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: #00a29f;
  font-weight: bold;
}

.header-line.small {
  font-size: 1.2vw; /* smaller text */
}

.header-line.large {
  font-size: 3vw; /* larger text */
  line-height: 0.7em; /* tighter line spacing for consecutive large lines */
  text-align: center;
}
















.header-left-top, .header-left-bottom { 
  flex:1; display:flex; align-items:center; justify-content:center; font-weight:bold; font-size:1.5vw;
}
.header-middle { flex:2%; }
.header-right { 
  flex:52%; 
  display:flex; 
  justify-content:center; 
  align-items:center; 
  font-family: 'Prompt', sans-serif; 
  font-weight:bold; 
  font-size:13vw;
  color: #000;
  margin-right:0px;
}

/* Middle section cards */
.middle { 
  flex:7; 
  display:flex; justify-content:center; 
  margin-top:10px; 
  padding:5px;
  box-sizing:border-box;
}
.card {
  margin:15px;
  background:#ffffff;
  display:flex;
  flex-direction:column;
  border-radius:15px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.15);
  overflow:hidden;
}
.card-top { 
  flex:70%; 
  display:flex; 
  justify-content:center; 
  align-items:center; 
  font-size:3.7vw; 
  font-weight:bold; 
  text-align:center; 
  padding:5px; 
}
.card-bottom { 
  flex:30%; display:flex; 
}
.bottom-left, .bottom-right { 
  flex:1; display:flex; flex-direction:column; align-items:center; justify-content:center; font-size:4vw; font-weight:bold; 
}
.bottom-left span, .bottom-right span { 
  font-size:0.5em; font-weight:normal; margin-bottom:0px; 
}

#setupFooter {
  width: 100%;
  text-align: center;
  font-size: 0.9em;
  color: #e5dcdc; /* lighter grey */
  font-family: 'Poppins', sans-serif;
  margin-top: 15px;
  padding: 5px 0;
}

#setupFooter .email {
  color: #888888; /* slightly darker grey for the email */
  font-weight: 500;
}








/* Responsive */
@media(max-width:900px){
  .header-left-top, .header-left-bottom { font-size:3vw; }
  .header-right { font-size:6vw; }
  .card-top { font-size:4vw; }
  .bottom-left, .bottom-right { font-size:3vw; }
  .bottom-left span, .bottom-right span { font-size:2vw; }
}
</style>
</head>
<body>

<!-- Setup Screen -->
<div id="setupScreen">
  <h1>Exam Clock Setup</h1>

  <div class="fields-row">
    <div class="exam-col">
      <label>Exam 1</label>
      <input type="text" class="exam-title" value="Paper 1" tabindex="1">
      <label>Start Time</label>
      <input type="time" class="exam-start">
      <label>Duration</label>
      <div style="display:flex; gap:5px;">
        <select class="exam-duration-hour"></select>
        <select class="exam-duration-min"></select>
      </div>
    </div>
    <div class="exam-col">
      <label>Exam 2</label>
      <input type="text" class="exam-title" value=""  tabindex="2">
      <label>Start Time</label>
      <input type="time" class="exam-start">
      <label>Duration</label>
      <div style="display:flex; gap:5px;">
        <select class="exam-duration-hour"></select>
        <select class="exam-duration-min"></select>
      </div>
    </div>
    <div class="exam-col">
      <label>Exam 3</label>
      <input type="text" class="exam-title" value=""  tabindex="3">
      <label>Start Time</label>
      <input type="time" class="exam-start">
      <label>Duration</label>
      <div style="display:flex; gap:5px;">
        <select class="exam-duration-hour"></select>
        <select class="exam-duration-min"></select>
      </div>
    </div>
    <div class="exam-col">
      <label>Exam 4</label>
      <input type="text" class="exam-title" value=""  tabindex="4">
      <label>Start Time</label>
      <input type="time" class="exam-start">
      <label>Duration</label>
      <div style="display:flex; gap:5px;">
        <select class="exam-duration-hour"></select>
        <select class="exam-duration-min"></select>
      </div>
    </div>
  </div>

  <div class="buttons-row">
    <button id="nowBtn">Insert Current Time</button>
    <button id="startBtn">Start</button>
    <label><input type="checkbox" id="manualDurationToggle"> Manual Duration</label>
  </div>


<div id="setupFooter">
  &copy; 2025 Alperton Community School
  <br>
  Contact <span class="email">m.sattar@alperton.brent.sch.uk</span> for technical queries.
</div>


</div>

<!-- Display Screen -->
<div id="displayScreen" onclick="backToSetup()">
  <div class="header">
<div class="header-left">
  <div class="header-line small">CENTRE NUMBER:</div>
  <div class="header-line large">12302</div>
  <div class="header-line small" style="margin-top:2.2em;">CENTRE NAME:</div>
  <div class="header-line large" style="margin-top:0.2em;">ALPERTON</div>
  <div class="header-line large" style="margin-top:0.2em;">COMMUNITY SCHOOL</div>
</div>


    <div class="header-middle"></div>
    <div class="header-right" id="mainClock">0:00:00</div>
  </div>
  <div class="middle" id="examGrid">
    <!-- Cards will appear here -->
  </div>
</div>

<script>
// Populate duration dropdowns
function populateDropdowns() {
  document.querySelectorAll('.exam-duration-hour').forEach(sel=>{
    sel.innerHTML = '';
    for(let i=0;i<=5;i++) sel.add(new Option(i,i));
    sel.value = 1; // default 1 hour
  });
  document.querySelectorAll('.exam-duration-min').forEach(sel=>{
    sel.innerHTML = '';
    for(let i=0;i<60;i+=5) sel.add(new Option(i,i));
    sel.value = 30; // default 30 minutes
  });
}
populateDropdowns();

// Insert current time
document.getElementById('nowBtn').addEventListener('click', ()=>{
  const now = new Date();
  now.setSeconds(0,0);
  now.setMinutes(now.getMinutes() + 1);
  const hh = String(now.getHours()).padStart(2,'0');
  const mm = String(now.getMinutes()).padStart(2,'0');
  document.querySelectorAll('.exam-start').forEach(inp=> inp.value=`${hh}:${mm}`);
});

// Manual duration toggle
document.getElementById('manualDurationToggle').addEventListener('change', function() {
  const checked = this.checked;
  document.querySelectorAll('.exam-col').forEach(col=>{
    const hourSel = col.querySelector('.exam-duration-hour');
    const minSel = col.querySelector('.exam-duration-min');

    if(checked) {
      const hourInput = document.createElement('input');
      hourInput.type='number'; hourInput.min='0'; hourInput.max='5'; hourInput.value=hourSel.value; hourInput.className='exam-duration-hour';
      const minInput = document.createElement('input');
      minInput.type='number'; minInput.min='0'; minInput.max='55'; minInput.step='5'; minInput.value=minSel.value; minInput.className='exam-duration-min';
      hourSel.replaceWith(hourInput);
      minSel.replaceWith(minInput);
    } else {
      const hourInput = col.querySelector('.exam-duration-hour');
      const minInput = col.querySelector('.exam-duration-min');
      const newHourSel = document.createElement('select'); newHourSel.className='exam-duration-hour';
      for(let i=0;i<=5;i++) newHourSel.add(new Option(i,i)); newHourSel.value=hourInput.value;
      const newMinSel = document.createElement('select'); newMinSel.className='exam-duration-min';
      for(let i=0;i<60;i+=5) newMinSel.add(new Option(i,i)); newMinSel.value=minInput.value;
      hourInput.replaceWith(newHourSel);
      minInput.replaceWith(newMinSel);
    }
  });
});

// Clock
function pad(n){return n<10?'0'+n:n;}
function updateClock(){
  const now=new Date();
  let hours=now.getHours()%12;
  if(hours===0) hours=12;
  const minutes=pad(now.getMinutes());
  const seconds=pad(now.getSeconds());
  document.getElementById('mainClock').textContent=hours+':'+minutes+':'+seconds;
}
setInterval(updateClock,1000);
updateClock();

// Build exam cards with colors and fixed widths
function buildExamGrid(){
  const titles = Array.from(document.querySelectorAll('.exam-title')).map(e=>e.value.trim());
  const starts = Array.from(document.querySelectorAll('.exam-start')).map(e=>e.value);
  const hours = Array.from(document.querySelectorAll('.exam-duration-hour')).map(e=>parseInt(e.value)||0);
  const mins = Array.from(document.querySelectorAll('.exam-duration-min')).map(e=>parseInt(e.value)||0);
  const exams=[];
  const colors = ['#009fe0', '#fa5947', '#7862ce', '#ef5bb3']; // Dark Blue, Green, Red, Yellow

  for(let i=0;i<4;i++){
    if(titles[i]){
      const startParts = starts[i] ? starts[i].split(':').map(Number) : [0,0];
      const startDate = new Date();
      startDate.setHours(startParts[0], startParts[1], 0, 0);
      const durationMs = (hours[i]*60 + mins[i])*60000;
      const finish = new Date(startDate.getTime() + durationMs);
      exams.push({
        title: titles[i],
        start: (startDate.getHours()%12||12)+":"+pad(startDate.getMinutes()),
        finish: (finish.getHours()%12||12)+":"+pad(finish.getMinutes())
      });
    }
  }

  const examGrid = document.getElementById('examGrid');
  examGrid.innerHTML="";
  examGrid.style.justifyContent = 'center'; // always center

  exams.forEach((ex, idx)=>{
    const card = document.createElement('div');
    card.className='card';
    // Set width based on number of cards
    let w = '25%';
    if(exams.length===3) w='30%';
    if(exams.length===2) w='35%';
    if(exams.length===1) w='40%';
    card.style.width = w;

    card.innerHTML=`
      <div class="card-top" style="color:${colors[idx]};">${ex.title}</div>
      <div class="card-bottom">
        <div class="bottom-left" style="color:${colors[idx]};"><span>START</span>${ex.start}</div>
        <div class="bottom-right" style="color:${colors[idx]};"><span>FINISH</span>${ex.finish}</div>
      </div>
    `;
    examGrid.appendChild(card);
  });
}

// Button handlers
document.getElementById('startBtn').addEventListener('click', ()=>{
  buildExamGrid();
  document.getElementById('setupScreen').style.display='none';
  document.getElementById('displayScreen').style.display='flex';
  // Fullscreen
  if(document.documentElement.requestFullscreen){
    document.documentElement.requestFullscreen();
  }
});

// Back to setup
function backToSetup(){
  document.getElementById('displayScreen').style.display='none';
  document.getElementById('setupScreen').style.display='flex';
  if(document.exitFullscreen){
    document.exitFullscreen();
  }
}
</script>

</body>
</html>
