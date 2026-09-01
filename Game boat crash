<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Crash Boat — Arungi Samudra</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@500;600;700;800&family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --deep:#0A3049;
    --mid:#125D7C;
    --shallow:#1E8AA8;
    --foam:#EAF6F3;
    --sand:#F3DFA8;
    --sunset:#F2A25C;
    --coral:#E85B4A;
    --gold:#F4C542;
    --ink:#062331;
    --cool:#63D9C4;
  }
  *{box-sizing:border-box;}
  html,body{
    margin:0; padding:0; height:100%; overflow:hidden;
    background:var(--deep);
    font-family:'Nunito',sans-serif;
    color:var(--foam);
    -webkit-tap-highlight-color:transparent;
    user-select:none;
  }
  h1,h2,h3,.display{font-family:'Baloo 2',cursive;}

  #stage{
    position:relative;
    width:100vw; height:100vh;
    overflow:hidden;
  }
  canvas{
    display:block;
    width:100%; height:100%;
    touch-action:none;
  }

  /* ---------- HUD ---------- */
  #hud{
    position:absolute; top:0; left:0; right:0;
    display:flex; justify-content:space-between; align-items:flex-start;
    padding:14px 16px;
    pointer-events:none;
    z-index:5;
  }
  .hudCol{ display:flex; flex-direction:column; gap:8px; align-items:flex-start; }
  .hudCol.right{ align-items:flex-end; }
  .pill{
    background:rgba(6,35,49,0.55);
    border:1.5px solid rgba(234,246,243,0.25);
    border-radius:14px;
    padding:8px 14px;
    backdrop-filter:blur(3px);
    pointer-events:auto;
  }
  #hearts{ display:flex; gap:4px; }
  #hearts svg{ width:22px; height:22px; }
  #money{
    font-family:'Baloo 2',cursive;
    font-size:20px; font-weight:700;
    color:var(--gold);
    display:flex; align-items:center; gap:6px;
  }
  #tempPill{
    display:flex; align-items:center; gap:8px;
    min-width:118px;
  }
  #tempIcon{ font-size:15px; flex-shrink:0; }
  #tempBarWrap{
    width:78px; height:8px; border-radius:5px;
    background:rgba(234,246,243,0.18);
    overflow:hidden;
  }
  #tempBarFill{
    height:100%; width:0%;
    background:linear-gradient(90deg,var(--shallow),var(--cool));
    transition:width .1s linear, background .2s ease;
  }
  #tempPill.overheat{ animation:overheatPulse .55s infinite; }
  @keyframes overheatPulse{
    0%,100%{ box-shadow:0 0 0 rgba(232,91,74,0); }
    50%{ box-shadow:0 0 14px rgba(232,91,74,0.85); }
  }
  #progressWrap{
    position:absolute; top:16px; left:50%; transform:translateX(-50%);
    width:min(46vw,320px);
    display:flex; flex-direction:column; align-items:center;
    pointer-events:none;
    z-index:5;
  }
  #islandLabel{ font-size:12px; letter-spacing:.3px; margin-bottom:4px; color:var(--sand); font-weight:700;}
  #progressBar{
    width:100%; height:9px; border-radius:6px;
    background:rgba(6,35,49,0.55);
    border:1.5px solid rgba(234,246,243,0.25);
    overflow:hidden;
  }
  #progressFill{
    height:100%; width:0%;
    background:linear-gradient(90deg,var(--sunset),var(--gold));
    transition:width .12s linear;
  }

  /* ---------- Touch controls ---------- */
  #touchControls{
    position:absolute; bottom:18px; left:0; right:0;
    display:none;
    justify-content:space-between;
    align-items:flex-end;
    padding:0 18px;
    z-index:6;
  }
  .stick{
    display:grid;
    grid-template-columns:56px 56px 56px;
    grid-template-rows:56px 56px 56px;
    gap:4px;
  }
  .stick button{
    grid-column:auto; grid-row:auto;
    border-radius:14px;
    border:1.5px solid rgba(234,246,243,0.3);
    background:rgba(6,35,49,0.55);
    color:var(--foam);
    font-size:20px;
    display:flex; align-items:center; justify-content:center;
    touch-action:none;
  }
  #btnUp{grid-column:2;grid-row:1;}
  #btnLeft{grid-column:1;grid-row:2;}
  #btnRight{grid-column:3;grid-row:2;}
  #btnDown{grid-column:2;grid-row:3;}

  #btnBoost{
    width:76px; height:76px;
    border-radius:50%;
    border:2px solid rgba(244,197,66,0.65);
    background:radial-gradient(circle at 35% 30%, var(--sunset), var(--coral));
    color:#fff;
    font-size:26px;
    display:flex; align-items:center; justify-content:center;
    box-shadow:0 6px 16px rgba(232,91,74,0.4);
    touch-action:none;
  }
  #btnBoost:active{ transform:scale(0.94); }

  /* ---------- Overlays ---------- */
  .overlay{
    position:absolute; inset:0;
    display:flex; align-items:center; justify-content:center;
    background:radial-gradient(circle at 50% 20%, rgba(18,93,124,0.92), rgba(6,35,49,0.97));
    z-index:20;
    padding:20px;
  }
  .hidden{ display:none !important; }
  .panel{
    width:min(92vw,460px);
    max-height:88vh;
    overflow-y:auto;
    background:var(--sand);
    color:var(--ink);
    border-radius:22px;
    padding:26px 24px 22px;
    box-shadow:0 18px 40px rgba(0,0,0,0.35);
    border:3px solid #fff3d6;
  }
  .panel h1{ font-size:30px; margin:0 0 6px; color:var(--deep); }
  .panel h2{ font-size:20px; margin:0 0 14px; color:var(--deep); }
  .panel p.sub{ margin:0 0 18px; font-size:14.5px; line-height:1.5; color:#3c4c52; }

  .btn{
    display:inline-flex; align-items:center; justify-content:center; gap:8px;
    font-family:'Baloo 2',cursive;
    font-weight:700; font-size:17px;
    padding:13px 20px;
    border-radius:14px;
    border:none;
    cursor:pointer;
    background:var(--coral);
    color:#fff;
    width:100%;
    transition:transform .08s ease;
  }
  .btn:active{ transform:scale(0.97); }
  .btn.secondary{ background:var(--mid); }
  .btn:disabled{ background:#b9b2a0; color:#736b58; cursor:not-allowed; }

  .controlsHint{
    display:flex; gap:14px; justify-content:center; margin-top:16px; flex-wrap:wrap;
    font-size:12.5px; color:#5a6a70; font-weight:700;
  }

  /* Upgrade rows */
  .upgradeRow{
    display:flex; align-items:center; gap:12px;
    background:#fff8e7; border:1.5px solid #ecd9a6;
    border-radius:14px; padding:10px 12px; margin-bottom:10px;
  }
  .upgradeRow .icon{
    width:42px; height:42px; border-radius:10px;
    display:flex; align-items:center; justify-content:center;
    font-size:20px; flex-shrink:0;
    background:var(--mid); color:#fff;
  }
  .upgradeRow .info{ flex:1; min-width:0; }
  .upgradeRow .info .name{ font-family:'Baloo 2',cursive; font-weight:700; font-size:15.5px; color:var(--deep); }
  .upgradeRow .info .lvl{ font-size:12px; color:#6b6552; }
  .upgradeRow .buy{
    font-family:'Baloo 2',cursive; font-weight:700; font-size:13.5px;
    padding:9px 12px; border-radius:10px; border:none; background:var(--sunset); color:#fff;
    white-space:nowrap;
  }
  .upgradeRow .buy:disabled{ background:#cbbf9d; color:#8a8266; }

  .islandChoices{ display:flex; flex-direction:column; gap:10px; margin-top:6px; }
  .islandCard{
    display:flex; align-items:center; gap:12px;
    background:#fff8e7; border:2px solid #ecd9a6;
    border-radius:14px; padding:12px; cursor:pointer;
    text-align:left;
  }
  .islandCard:active{ transform:scale(0.98); }
  .islandCard .tag{
    font-family:'Baloo 2',cursive; font-weight:700; font-size:22px;
  }
  .islandCard .meta{ flex:1; }
  .islandCard .meta .name{ font-family:'Baloo 2',cursive; font-weight:700; color:var(--deep); font-size:15.5px; }
  .islandCard .meta .desc{ font-size:12px; color:#6b6552; margin-top:2px; }
  .islandCard .reward{ font-size:12px; font-weight:800; color:var(--coral); white-space:nowrap; }

  .statRow{ display:flex; justify-content:space-between; font-size:14px; padding:6px 2px; border-bottom:1px dashed #dccb9b; }
  .statRow b{ color:var(--deep); }

  /* Skin picker */
  .skinRow{ display:flex; gap:10px; justify-content:center; flex-wrap:wrap; margin-top:14px; }
  .skinSwatch{
    width:42px; height:42px; border-radius:50%;
    border:3px solid transparent;
    cursor:pointer;
    box-shadow:inset 0 -7px 10px rgba(0,0,0,0.28), 0 2px 4px rgba(0,0,0,0.2);
    display:flex; align-items:center; justify-content:center;
  }
  .skinSwatch.selected{ border-color:var(--coral); transform:scale(1.08); }
  #skinLabel, #skinLabelIsland{ text-align:center; font-size:12px; font-weight:700; color:#5a6a70; margin-top:6px; }
</style>
</head>
<body>
<div id="stage">
  <canvas id="game"></canvas>

  <div id="hud">
    <div class="hudCol">
      <div class="pill" id="hearts"></div>
      <div class="pill" id="tempPill">
        <span id="tempIcon">🌡️</span>
        <div id="tempBarWrap"><div id="tempBarFill"></div></div>
      </div>
    </div>
    <div class="hudCol right">
      <div class="pill" id="money">🪙 <span id="moneyVal">0</span></div>
    </div>
  </div>

  <div id="progressWrap">
    <div id="islandLabel">Menuju pulau berikutnya</div>
    <div id="progressBar"><div id="progressFill"></div></div>
  </div>

  <div id="touchControls">
    <div class="stick">
      <button id="btnUp">▲</button>
      <button id="btnLeft">◀</button>
      <button id="btnRight">▶</button>
      <button id="btnDown">▼</button>
    </div>
    <button id="btnBoost">⚡</button>
  </div>

  <!-- START SCREEN -->
  <div class="overlay" id="startScreen">
    <div class="panel">
      <h1>⛵ Crash Boat</h1>
      <p class="sub">Kemudikan perahumu menerjang ombak, hindari karang dan bajak laut, kumpulkan koin, lalu singgahi pulau untuk upgrade <b>kapal</b>, <b>kecepatan</b>, <b>booster</b>, dan <b>pendapatan</b>. Jaga suhu mesin agar tidak overheat, dan sambut pelampung perbaikan setiap 1000m. Semakin jauh berlayar, semakin ganas lautnya.</p>
      <button class="btn" id="btnStart">🚤 Mulai Berlayar</button>
      <div class="controlsHint">
        <span>⌨️ Panah / WASD untuk bergerak</span>
        <span>⚡ Spasi untuk Boost</span>
      </div>
      <h2 style="margin-top:20px; font-size:16px;">Pilih Skin Kapal</h2>
      <div class="skinRow" id="skinRowStart"></div>
      <div id="skinLabel"></div>
    </div>
  </div>

  <!-- ISLAND SCREEN -->
  <div class="overlay hidden" id="islandScreen">
    <div class="panel">
      <h1 id="islandTitle">🏝️ Pulau Singgah</h1>
      <p class="sub" id="islandSub">Kapalmu berlabuh sejenak. Belanjakan hasil pelayaranmu sebelum melaut lagi.</p>

      <h2 style="margin-top:2px;">Toko Upgrade</h2>
      <div class="upgradeRow">
        <div class="icon">🛡️</div>
        <div class="info">
          <div class="name">Lambung Kapal</div>
          <div class="lvl" id="shipLvlText">Lvl 0 · +1 nyawa maksimum</div>
        </div>
        <button class="buy" id="buyShip">Beli</button>
      </div>
      <div class="upgradeRow">
        <div class="icon">💨</div>
        <div class="info">
          <div class="name">Kecepatan</div>
          <div class="lvl" id="speedLvlText">Lvl 0 · manuver lebih gesit</div>
        </div>
        <button class="buy" id="buySpeed">Beli</button>
      </div>
      <div class="upgradeRow">
        <div class="icon">⚡</div>
        <div class="info">
          <div class="name">Booster Mesin</div>
          <div class="lvl" id="boostLvlText">Lvl 0 · dorongan kecepatan sementara</div>
        </div>
        <button class="buy" id="buyBoost">Beli</button>
      </div>
      <div class="upgradeRow">
        <div class="icon">💰</div>
        <div class="info">
          <div class="name">Pendapatan</div>
          <div class="lvl" id="incomeLvlText">Lvl 0 · uang pasif & nilai koin</div>
        </div>
        <button class="buy" id="buyIncome">Beli</button>
      </div>

      <h2 style="margin-top:18px; font-size:16px;">Ganti Skin Kapal</h2>
      <div class="skinRow" id="skinRowIsland"></div>
      <div id="skinLabelIsland"></div>

      <h2 style="margin-top:18px;">Pilih Rute Berikutnya</h2>
      <div class="islandChoices" id="islandChoices"></div>
    </div>
  </div>

  <!-- GAME OVER SCREEN -->
  <div class="overlay hidden" id="gameOverScreen">
    <div class="panel">
      <h1>🌊 Kapal Karam!</h1>
      <p class="sub">Pelayaranmu berakhir di sini. Ini rekap perjalananmu:</p>
      <div class="statRow"><span>Jarak tempuh</span><b id="statDistance">0 m</b></div>
      <div class="statRow"><span>Pulau disinggahi</span><b id="statIslands">0</b></div>
      <div class="statRow"><span>Total uang terkumpul</span><b id="statMoney">🪙 0</b></div>
      <div style="height:16px;"></div>
      <button class="btn" id="btnRestart">🔁 Berlayar Lagi</button>
    </div>
  </div>
</div>

<script>
(function(){
  "use strict";
  const canvas = document.getElementById('game');
  const ctx = canvas.getContext('2d');
  let W, H, DPR;

  function resize(){
    DPR = Math.min(window.devicePixelRatio||1, 2);
    W = window.innerWidth; H = window.innerHeight;
    canvas.width = W*DPR; canvas.height = H*DPR;
    ctx.setTransform(DPR,0,0,DPR,0,0);
  }
  window.addEventListener('resize', resize);
  resize();

  const isTouch = matchMedia('(hover:none)').matches || 'ontouchstart' in window;
  if(isTouch) document.getElementById('touchControls').style.display='flex';

  // ---------------- Skins ----------------
  const SKINS = [
    {name:'Karang Sunset', hull:'#F2A25C', trim:'#8A4B21', stripe:'#EAF6F3'},
    {name:'Ombak Biru',    hull:'#1E8AA8', trim:'#0A3049', stripe:'#EAF6F3'},
    {name:'Api Karang',    hull:'#E85B4A', trim:'#7A2418', stripe:'#FFE8C2'},
    {name:'Emas Raja Laut',hull:'#F4C542', trim:'#8A6A12', stripe:'#0A3049'}
  ];
  let selectedSkin = 0; // persists across restarts (cosmetic preference)

  function buildSkinRow(containerId, labelId){
    const row = document.getElementById(containerId);
    row.innerHTML='';
    SKINS.forEach((s,i)=>{
      const b=document.createElement('div');
      b.className='skinSwatch'+(i===selectedSkin?' selected':'');
      b.style.background = `radial-gradient(circle at 35% 30%, ${s.stripe}, ${s.hull})`;
      b.title=s.name;
      b.onclick=()=>{ selectedSkin=i; refreshSkinRows(); };
      row.appendChild(b);
    });
    document.getElementById(labelId).textContent = SKINS[selectedSkin].name;
  }
  function refreshSkinRows(){
    buildSkinRow('skinRowStart','skinLabel');
    buildSkinRow('skinRowIsland','skinLabelIsland');
  }

  // ---------------- Game State ----------------
  const state = {
    screen:'start', // start | playing | island | gameover
    money:0,
    health:3, maxHealth:3,
    shipLevel:0, speedLevel:0, incomeLevel:0, boostLevel:0,
    distance:0, segmentTarget:900, totalDistance:0, nextRepairAt:1000,
    islandsVisited:0,
    difficulty:1,          // ramps overall danger
    scrollSpeed:150,        // px/sec base
    spawnTimer:0, coinTimer:0,
    obstacles:[], coins:[], repairs:[], particles:[], toasts:[],
    boat:{x:0,y:0,w:34,h:52,vx:0,vy:0},
    invuln:0,
    incomeTimer:0,
    engineTemp:0, overheated:false, boosting:false,
    lastT:0,
    keys:{}
  };

  function currentWeight(){ return 10 + state.shipLevel*4; }
  function boostMultiplier(){ return 1.42 + state.boostLevel*0.11; }
  function boostHeatRate(){ return Math.max(9, 28 - state.boostLevel*2.1); }
  const ENGINE_COOL_RATE = 15;

  function boatManeuverBase(){
    return Math.max(90, 210 + state.speedLevel*34 - currentWeight()*1.15);
  }
  function boatManeuver(){
    let m = boatManeuverBase();
    if(state.boosting && !state.overheated) m *= boostMultiplier();
    if(state.overheated) m *= 0.45;
    return m;
  }
  function coinMult(){ return 1 + state.incomeLevel*0.22; }
  function passiveIncome(){ return state.incomeLevel*2.4; }
  function shipCost(){ return Math.round(45*Math.pow(1.55, state.shipLevel)); }
  function speedCost(){ return Math.round(35*Math.pow(1.55, state.speedLevel)); }
  function boostCost(){ return Math.round(50*Math.pow(1.55, state.boostLevel)); }
  function incomeCost(){ return Math.round(55*Math.pow(1.55, state.incomeLevel)); }

  const ISLAND_TYPES = [
    {tag:'🌤️', name:'Perairan Tenang', desc:'Rintangan lebih jarang, hadiah standar.', diffMul:0.75, rewardMul:1.0, heatMul:0.85},
    {tag:'⛅', name:'Jalur Normal', desc:'Tantangan seimbang.', diffMul:1.0, rewardMul:1.25, heatMul:1.0},
    {tag:'🌩️', name:'Perairan Berbahaya', desc:'Badai & bajak laut ganas, koin melimpah, mesin lebih cepat panas.', diffMul:1.45, rewardMul:1.7, heatMul:1.3}
  ];
  let pendingIslandMods = {diffMul:1, rewardMul:1, heatMul:1};

  function resetBoat(){
    state.boat.x = W/2; state.boat.y = H*0.72;
  }

  function fullReset(){
    state.money=0; state.health=3; state.maxHealth=3;
    state.shipLevel=0; state.speedLevel=0; state.incomeLevel=0; state.boostLevel=0;
    state.distance=0; state.segmentTarget=900; state.totalDistance=0; state.nextRepairAt=1000;
    state.islandsVisited=0;
    state.difficulty=1; state.scrollSpeed=150;
    state.obstacles=[]; state.coins=[]; state.repairs=[]; state.particles=[]; state.toasts=[];
    state.invuln=0; state.incomeTimer=0;
    state.engineTemp=0; state.overheated=false; state.boosting=false;
    pendingIslandMods = {diffMul:1, rewardMul:1, heatMul:1};
    resetBoat();
  }

  // ---------------- Input ----------------
  window.addEventListener('keydown', e=>{
    const k=e.key.toLowerCase();
    if(['arrowup','arrowdown','arrowleft','arrowright',' '].includes(k)) e.preventDefault();
    state.keys[k]=true;
  });
  window.addEventListener('keyup', e=>{ state.keys[e.key.toLowerCase()]=false; });

  function bindHold(id, fn){
    const el=document.getElementById(id);
    let active=false;
    const on=(e)=>{ e.preventDefault(); active=true; };
    const off=(e)=>{ active=false; };
    el.addEventListener('touchstart',on); el.addEventListener('touchend',off); el.addEventListener('touchcancel',off);
    el.addEventListener('mousedown',on); el.addEventListener('mouseup',off); el.addEventListener('mouseleave',off);
    return ()=>active;
  }
  const touchUp = bindHold('btnUp');
  const touchDown = bindHold('btnDown');
  const touchLeft = bindHold('btnLeft');
  const touchRight = bindHold('btnRight');
  const touchBoost = bindHold('btnBoost');

  // ---------------- Toasts ----------------
  function showToast(text, color){
    state.toasts.push({text, color:color||'#EAF6F3', t:0, life:2.1, y:0});
  }

  // ---------------- Spawning ----------------
  function spawnObstacle(){
    const roll = Math.random();
    const margin=40;
    const x = margin + Math.random()*(W-margin*2);
    let type;
    if(roll<0.45) type='rock';
    else if(roll<0.8) type='enemy';
    else type='mine';
    state.obstacles.push({
      type, x, y:-60,
      r: type==='rock'?26: type==='mine'?20:24,
      phase: Math.random()*Math.PI*2,
      baseX:x,
      hit:false
    });
  }
  function spawnCoin(){
    const margin=30;
    state.coins.push({x:margin+Math.random()*(W-margin*2), y:-30, r:12, taken:false, bob:Math.random()*Math.PI*2});
  }
  function spawnRepairBuoy(){
    const margin=36;
    state.repairs.push({x:margin+Math.random()*(W-margin*2), y:-40, r:17, taken:false, bob:Math.random()*Math.PI*2});
  }

  function spawnParticles(x,y,color,n){
    for(let i=0;i<n;i++){
      state.particles.push({
        x,y, vx:(Math.random()-0.5)*220, vy:(Math.random()-0.5)*220,
        life:0.5+Math.random()*0.3, t:0, color
      });
    }
  }

  // ---------------- Update ----------------
  function update(dt){
    if(state.screen!=='playing') return;

    // difficulty-adjusted values
    const diff = state.difficulty * pendingIslandMods.diffMul;
    const scroll = state.scrollSpeed + diff*22;

    // --- boost input flag ---
    state.boosting = (state.keys[' ']||touchBoost()) && !state.overheated;

    // --- boat movement ---
    const man = boatManeuver();
    let mvx=0, mvy=0;
    if(state.keys['arrowleft']||state.keys['a']||touchLeft()) mvx-=1;
    if(state.keys['arrowright']||state.keys['d']||touchRight()) mvx+=1;
    if(state.keys['arrowup']||state.keys['w']||touchUp()) mvy-=1;
    if(state.keys['arrowdown']||state.keys['s']||touchDown()) mvy+=1;
    const len=Math.hypot(mvx,mvy)||1;
    state.boat.x += (mvx/len)*man*dt;
    state.boat.y += (mvy/len)*man*dt;

    const bw=state.boat.w, bh=state.boat.h;
    state.boat.x = Math.max(bw*0.7, Math.min(W-bw*0.7, state.boat.x));
    state.boat.y = Math.max(H*0.32, Math.min(H-bh*0.55, state.boat.y));

    // --- engine temperature ---
    if(state.boosting){
      state.engineTemp += boostHeatRate()*pendingIslandMods.heatMul*dt;
    } else {
      state.engineTemp -= ENGINE_COOL_RATE*dt;
    }
    state.engineTemp = Math.max(0, Math.min(100, state.engineTemp));
    if(state.engineTemp>=100 && !state.overheated){
      state.overheated = true;
      state.boosting = false;
      spawnParticles(state.boat.x, state.boat.y, '#E85B4A', 10);
      showToast('🔥 Mesin overheat! Kecepatan menurun.', '#F2A25C');
    }
    if(state.overheated && state.engineTemp<=35){
      state.overheated = false;
      showToast('✅ Mesin kembali normal.', '#63D9C4');
    }

    // --- distance & income ---
    const distGain = scroll*dt*0.12;
    state.distance += distGain;
    state.totalDistance += distGain;
    state.incomeTimer += dt;
    if(state.incomeTimer>=1){
      state.incomeTimer-=1;
      if(passiveIncome()>0) state.money += passiveIncome();
    }
    if(state.invuln>0) state.invuln-=dt;

    // --- repair milestone every 1000m ---
    if(state.totalDistance >= state.nextRepairAt){
      spawnRepairBuoy();
      state.nextRepairAt += 1000;
    }

    // --- spawn timers ---
    state.spawnTimer -= dt;
    const spawnEvery = Math.max(0.45, 1.25 - diff*0.09);
    if(state.spawnTimer<=0){ spawnObstacle(); state.spawnTimer = spawnEvery*(0.7+Math.random()*0.6); }

    state.coinTimer -= dt;
    if(state.coinTimer<=0){ spawnCoin(); state.coinTimer = 0.9+Math.random()*0.9; }

    // --- obstacles ---
    for(const o of state.obstacles){
      o.y += scroll*dt;
      o.phase += dt;
      if(o.type==='enemy'){ o.x = o.baseX + Math.sin(o.phase*1.6)*46; }
      if(o.type==='mine'){ o.x = o.baseX + Math.sin(o.phase*2.4)*10; }
    }
    state.obstacles = state.obstacles.filter(o=>o.y < H+80);

    for(const c of state.coins){ c.y += scroll*dt; c.bob+=dt*4; }
    state.coins = state.coins.filter(c=>c.y < H+40 && !c.taken);

    for(const r of state.repairs){ r.y += scroll*dt; r.bob+=dt*3; }
    state.repairs = state.repairs.filter(r=>r.y < H+50 && !r.taken);

    // --- particles ---
    for(const p of state.particles){ p.t+=dt; p.x+=p.vx*dt; p.y+=p.vy*dt; p.vx*=0.92; p.vy*=0.92; }
    state.particles = state.particles.filter(p=>p.t<p.life);

    // --- toasts ---
    for(const t of state.toasts){ t.t+=dt; t.y -= 16*dt; }
    state.toasts = state.toasts.filter(t=>t.t<t.life);

    // --- collisions: coins ---
    for(const c of state.coins){
      if(c.taken) continue;
      const dx=c.x-state.boat.x, dy=c.y-(state.boat.y-8);
      if(Math.hypot(dx,dy) < c.r+bw*0.42){
        c.taken=true;
        state.money += Math.round(8*coinMult()*pendingIslandMods.rewardMul);
        spawnParticles(c.x,c.y,'#F4C542',8);
      }
    }

    // --- collisions: repair buoys ---
    for(const r of state.repairs){
      if(r.taken) continue;
      const dx=r.x-state.boat.x, dy=r.y-(state.boat.y-8);
      if(Math.hypot(dx,dy) < r.r+bw*0.42){
        r.taken=true;
        const healed = state.health < state.maxHealth;
        state.health = Math.min(state.maxHealth, state.health+1);
        state.engineTemp = 0;
        state.overheated = false;
        spawnParticles(r.x,r.y,'#63D9C4',12);
        showToast(healed ? '🛠️ Kapal diperbaiki! +1 nyawa' : '🛠️ Mesin didinginkan penuh!', '#63D9C4');
      }
    }

    // --- collisions: obstacles ---
    if(state.invuln<=0){
      for(const o of state.obstacles){
        if(o.hit) continue;
        const dx=o.x-state.boat.x, dy=o.y-(state.boat.y-4);
        const hitR = o.r + bw*0.36;
        if(Math.hypot(dx,dy) < hitR){
          o.hit=true;
          state.health -= (o.type==='mine'?2:1);
          state.invuln = 1.35;
          spawnParticles(state.boat.x,state.boat.y,'#E85B4A',14);
          if(state.health<=0){ state.health=0; triggerGameOver(); return; }
        }
      }
    }

    // --- island check ---
    if(state.distance >= state.segmentTarget){
      openIslandScreen();
    }

    updateHUD();
  }

  // ---------------- Render ----------------
  let waveT=0;
  function render(dt){
    waveT+=dt;
    // ocean gradient
    const g=ctx.createLinearGradient(0,0,0,H);
    g.addColorStop(0,'#0E4F6C');
    g.addColorStop(1,'#0A3049');
    ctx.fillStyle=g; ctx.fillRect(0,0,W,H);

    // scrolling wave lines
    ctx.strokeStyle='rgba(234,246,243,0.10)';
    ctx.lineWidth=2;
    const off = (waveT*90)%80;
    for(let y=-80+off; y<H; y+=80){
      ctx.beginPath();
      for(let x=0;x<=W;x+=20){
        const yy = y + Math.sin((x*0.02)+waveT*1.4)*6;
        if(x===0) ctx.moveTo(x,yy); else ctx.lineTo(x,yy);
      }
      ctx.stroke();
    }

    if(state.screen==='playing'){
      drawRepairs();
      drawCoins();
      drawObstacles();
      drawBoat();
      drawParticles();
      drawToasts();
    }
  }

  function drawBoat(){
    const {x,y,w,h} = state.boat;
    const skin = SKINS[selectedSkin];
    ctx.save();
    ctx.translate(x,y);
    const flash = state.invuln>0 && Math.floor(state.invuln*14)%2===0;
    ctx.globalAlpha = flash?0.4:1;
    // wake (longer/brighter while boosting)
    ctx.fillStyle= state.boosting ? 'rgba(234,246,243,0.55)' : 'rgba(234,246,243,0.35)';
    ctx.beginPath();
    ctx.ellipse(0,h*0.42,w*(state.boosting?0.72:0.55),state.boosting?14:10,0,0,Math.PI*2);
    ctx.fill();
    // hull
    ctx.fillStyle=skin.hull;
    ctx.beginPath();
    ctx.moveTo(0,-h/2);
    ctx.lineTo(w/2,h*0.18);
    ctx.quadraticCurveTo(w/2,h/2, 0, h/2);
    ctx.quadraticCurveTo(-w/2,h/2,-w/2,h*0.18);
    ctx.closePath();
    ctx.fill();
    ctx.strokeStyle=skin.trim; ctx.lineWidth=2.5; ctx.stroke();
    // deck stripe
    ctx.fillStyle=skin.stripe;
    ctx.fillRect(-w*0.32,-4,w*0.64,10);
    // sail level indicator = ship level dots
    ctx.fillStyle=skin.trim;
    for(let i=0;i<Math.min(state.shipLevel,4);i++){
      ctx.beginPath(); ctx.arc(-w*0.22+i*(w*0.16), h*0.02, 2.6, 0, Math.PI*2); ctx.fill();
    }
    // boost flame
    if(state.boosting){
      ctx.fillStyle='rgba(244,197,66,0.9)';
      ctx.beginPath();
      ctx.moveTo(-w*0.18,h*0.5); ctx.lineTo(0,h*0.5+10+Math.random()*6); ctx.lineTo(w*0.18,h*0.5);
      ctx.closePath(); ctx.fill();
    }
    ctx.restore();
    ctx.globalAlpha=1;
  }

  function drawObstacles(){
    for(const o of state.obstacles){
      ctx.save();
      ctx.translate(o.x,o.y);
      if(o.type==='rock'){
        ctx.fillStyle='#6E5B4A';
        ctx.beginPath();
        ctx.moveTo(-o.r,4); ctx.lineTo(-o.r*0.5,-o.r); ctx.lineTo(o.r*0.3,-o.r*0.9);
        ctx.lineTo(o.r,0); ctx.lineTo(o.r*0.6,o.r*0.7); ctx.lineTo(-o.r*0.6,o.r*0.7);
        ctx.closePath(); ctx.fill();
        ctx.strokeStyle='#493A2C'; ctx.lineWidth=2; ctx.stroke();
      } else if(o.type==='enemy'){
        ctx.fillStyle='#3A3F52';
        ctx.beginPath();
        ctx.moveTo(0,-o.r); ctx.lineTo(o.r*0.8,o.r*0.6); ctx.quadraticCurveTo(0,o.r, -o.r*0.8,o.r*0.6);
        ctx.closePath(); ctx.fill();
        ctx.fillStyle='#E85B4A';
        ctx.fillRect(-o.r*0.35,-o.r*0.3,o.r*0.7,o.r*0.5);
      } else {
        ctx.rotate(o.phase*3);
        ctx.fillStyle='#232323';
        ctx.beginPath(); ctx.arc(0,0,o.r*0.55,0,Math.PI*2); ctx.fill();
        ctx.strokeStyle='#E85B4A'; ctx.lineWidth=3;
        for(let i=0;i<8;i++){
          const a=i/8*Math.PI*2;
          ctx.beginPath();
          ctx.moveTo(Math.cos(a)*o.r*0.55, Math.sin(a)*o.r*0.55);
          ctx.lineTo(Math.cos(a)*o.r, Math.sin(a)*o.r);
          ctx.stroke();
        }
      }
      ctx.restore();
    }
  }

  function drawCoins(){
    for(const c of state.coins){
      if(c.taken) continue;
      const bob=Math.sin(c.bob)*3;
      ctx.save();
      ctx.translate(c.x,c.y+bob);
      ctx.fillStyle='#F4C542';
      ctx.beginPath(); ctx.arc(0,0,c.r,0,Math.PI*2); ctx.fill();
      ctx.strokeStyle='#B8860B'; ctx.lineWidth=2; ctx.stroke();
      ctx.fillStyle='#B8860B';
      ctx.font='bold 13px Baloo 2, sans-serif';
      ctx.textAlign='center'; ctx.textBaseline='middle';
      ctx.fillText('$',0,1);
      ctx.restore();
    }
  }

  function drawRepairs(){
    for(const r of state.repairs){
      if(r.taken) continue;
      const bob=Math.sin(r.bob)*4;
      ctx.save();
      ctx.translate(r.x,r.y+bob);
      const glow = 0.55+Math.sin(r.bob*1.7)*0.25;
      ctx.fillStyle=`rgba(99,217,196,${glow})`;
      ctx.beginPath(); ctx.arc(0,0,r.r+7,0,Math.PI*2); ctx.fill();
      ctx.fillStyle='#EAF6F3';
      ctx.beginPath(); ctx.arc(0,0,r.r,0,Math.PI*2); ctx.fill();
      ctx.strokeStyle='#1E8AA8'; ctx.lineWidth=3; ctx.stroke();
      ctx.font='bold 16px sans-serif';
      ctx.textAlign='center'; ctx.textBaseline='middle';
      ctx.fillText('🔧',0,1);
      ctx.restore();
    }
  }

  function drawParticles(){
    for(const p of state.particles){
      const a = 1-(p.t/p.life);
      ctx.fillStyle=p.color;
      ctx.globalAlpha=Math.max(a,0);
      ctx.beginPath(); ctx.arc(p.x,p.y,3.2,0,Math.PI*2); ctx.fill();
    }
    ctx.globalAlpha=1;
  }

  function drawToasts(){
    ctx.save();
    ctx.textAlign='center'; ctx.textBaseline='middle';
    ctx.font='bold 15px Baloo 2, sans-serif';
    state.toasts.forEach((t,i)=>{
      const alpha = Math.max(0, 1-(t.t/t.life));
      const ty = 130 + i*26 + t.y;
      ctx.globalAlpha = alpha;
      ctx.lineWidth=4; ctx.strokeStyle='rgba(6,35,49,0.85)';
      ctx.strokeText(t.text, W/2, ty);
      ctx.fillStyle = t.color;
      ctx.fillText(t.text, W/2, ty);
    });
    ctx.restore();
    ctx.globalAlpha=1;
  }

  // ---------------- HUD ----------------
  function updateHUD(){
    document.getElementById('moneyVal').textContent = Math.floor(state.money);
    const heartsEl = document.getElementById('hearts');
    heartsEl.innerHTML='';
    for(let i=0;i<state.maxHealth;i++){
      const filled = i<state.health;
      heartsEl.innerHTML += `<svg viewBox="0 0 24 24" fill="${filled?'#E85B4A':'rgba(234,246,243,0.25)'}"><path d="M12 21s-7.5-4.6-10-9.3C.4 8.1 2 4.5 5.6 4c2-.3 3.8.7 5 2.3C11.6 4.7 13.4 3.7 15.4 4c3.6.5 5.2 4.1 3.6 7.7C19.5 16.4 12 21 12 21z"/></svg>`;
    }
    const pct = Math.min(100, (state.distance/state.segmentTarget)*100);
    document.getElementById('progressFill').style.width = pct+'%';
    document.getElementById('islandLabel').textContent = `Pulau ke-${state.islandsVisited+1} · ${Math.floor(state.distance)}/${state.segmentTarget} m`;

    const tempFill = document.getElementById('tempBarFill');
    tempFill.style.width = state.engineTemp+'%';
    tempFill.style.background = state.engineTemp<60
      ? 'linear-gradient(90deg,#1E8AA8,#63D9C4)'
      : state.engineTemp<85
        ? 'linear-gradient(90deg,#F2A25C,#F4C542)'
        : 'linear-gradient(90deg,#E85B4A,#ff7a63)';
    document.getElementById('tempIcon').textContent = state.overheated ? '🔥' : '🌡️';
    document.getElementById('tempPill').classList.toggle('overheat', state.overheated);
  }

  // ---------------- Screens ----------------
  function showScreen(id){
    ['startScreen','islandScreen','gameOverScreen'].forEach(s=>{
      document.getElementById(s).classList.toggle('hidden', s!==id);
    });
  }

  function openIslandScreen(){
    state.screen='island';
    state.islandsVisited++;
    document.getElementById('islandTitle').textContent = `🏝️ Pulau ke-${state.islandsVisited}`;
    document.getElementById('islandSub').textContent = `Kapalmu berhasil berlayar sejauh ${Math.floor(state.distance)} m. Belanja upgrade lalu pilih rute selanjutnya.`;
    refreshShop();
    refreshSkinRows();
    renderIslandChoices();
    document.getElementById('islandScreen').classList.remove('hidden');
  }

  function refreshShop(){
    document.getElementById('shipLvlText').textContent = `Lvl ${state.shipLevel} · Nyawa maks: ${state.maxHealth} · Berat: ${currentWeight()}`;
    document.getElementById('speedLvlText').textContent = `Lvl ${state.speedLevel} · Manuver: ${Math.round(boatManeuverBase())} px/s`;
    document.getElementById('boostLvlText').textContent = `Lvl ${state.boostLevel} · Boost x${boostMultiplier().toFixed(2)}, panas +${boostHeatRate().toFixed(1)}/dtk`;
    document.getElementById('incomeLvlText').textContent = `Lvl ${state.incomeLevel} · +${passiveIncome().toFixed(1)}/dtk, koin x${coinMult().toFixed(2)}`;

    const bShip=document.getElementById('buyShip');
    const bSpeed=document.getElementById('buySpeed');
    const bBoost=document.getElementById('buyBoost');
    const bIncome=document.getElementById('buyIncome');
    bShip.textContent = `🪙 ${shipCost()}`;
    bSpeed.textContent = `🪙 ${speedCost()}`;
    bBoost.textContent = `🪙 ${boostCost()}`;
    bIncome.textContent = `🪙 ${incomeCost()}`;
    bShip.disabled = state.money<shipCost();
    bSpeed.disabled = state.money<speedCost();
    bBoost.disabled = state.money<boostCost();
    bIncome.disabled = state.money<incomeCost();
  }

  document.getElementById('buyShip').onclick=()=>{
    const c=shipCost();
    if(state.money>=c){ state.money-=c; state.shipLevel++; state.maxHealth++; state.health++; refreshShop(); updateHUD(); }
  };
  document.getElementById('buySpeed').onclick=()=>{
    const c=speedCost();
    if(state.money>=c){ state.money-=c; state.speedLevel++; refreshShop(); updateHUD(); }
  };
  document.getElementById('buyBoost').onclick=()=>{
    const c=boostCost();
    if(state.money>=c){ state.money-=c; state.boostLevel++; refreshShop(); updateHUD(); }
  };
  document.getElementById('buyIncome').onclick=()=>{
    const c=incomeCost();
    if(state.money>=c){ state.money-=c; state.incomeLevel++; refreshShop(); updateHUD(); }
  };

  function renderIslandChoices(){
    const wrap=document.getElementById('islandChoices');
    wrap.innerHTML='';
    // shuffle a sample of 3 (could repeat types with slight variance)
    const picks = [...ISLAND_TYPES];
    picks.forEach(opt=>{
      const div=document.createElement('div');
      div.className='islandCard';
      div.innerHTML = `<div class="tag">${opt.tag}</div>
        <div class="meta"><div class="name">${opt.name}</div><div class="desc">${opt.desc}</div></div>
        <div class="reward">x${opt.rewardMul.toFixed(2)} hadiah</div>`;
      div.onclick=()=>{
        pendingIslandMods = {diffMul:opt.diffMul, rewardMul:opt.rewardMul, heatMul:opt.heatMul};
        state.difficulty += 0.55;
        state.distance = 0;
        state.segmentTarget = Math.round(900 + state.islandsVisited*140);
        state.obstacles=[]; state.coins=[]; state.repairs=[];
        state.screen='playing';
        showScreen(null);
        document.getElementById('islandScreen').classList.add('hidden');
      };
      wrap.appendChild(div);
    });
  }

  function triggerGameOver(){
    state.screen='gameover';
    document.getElementById('statDistance').textContent = Math.floor(state.totalDistance) + ' m';
    document.getElementById('statIslands').textContent = state.islandsVisited;
    document.getElementById('statMoney').textContent = '🪙 ' + Math.floor(state.money);
    document.getElementById('gameOverScreen').classList.remove('hidden');
  }

  document.getElementById('btnStart').onclick=()=>{
    fullReset();
    state.screen='playing';
    document.getElementById('startScreen').classList.add('hidden');
    updateHUD();
  };
  document.getElementById('btnRestart').onclick=()=>{
    fullReset();
    state.screen='playing';
    document.getElementById('gameOverScreen').classList.add('hidden');
    updateHUD();
  };

  // ---------------- Loop ----------------
  function loop(t){
    if(!state.lastT) state.lastT=t;
    let dt=(t-state.lastT)/1000;
    state.lastT=t;
    dt=Math.min(dt,0.05);
    update(dt);
    render(dt);
    requestAnimationFrame(loop);
  }
  resetBoat();
  refreshSkinRows();
  updateHUD();
  requestAnimationFrame(loop);
})();
</script>
</body>
</html>
