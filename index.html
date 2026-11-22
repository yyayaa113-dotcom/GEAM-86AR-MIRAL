<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">
<title>محاكي القطار 3D</title>
<style>
  *{box-sizing:border-box;margin:0;padding:0;font-family:Tahoma,Arial,sans-serif;user-select:none;-webkit-user-select:none}
  html,body{width:100%;height:100%;overflow:hidden;background:#111;color:#fff}
  canvas#c{position:fixed;inset:0;width:100%;height:100%;display:block;touch-action:none;cursor:grab}
  canvas#c.drag{cursor:grabbing}
  .hidden{display:none!important}

  /* اللوبي */
  #lobby{position:fixed;inset:0;background:linear-gradient(160deg,#0f2027,#203a43,#2c5364);overflow:auto;padding:20px;z-index:10}
  #lobby h1{text-align:center;font-size:34px;margin:10px 0}
  .topbar{display:flex;justify-content:center;gap:12px;flex-wrap:wrap;margin:10px 0 20px}
  .pill{background:rgba(255,255,255,.12);padding:8px 18px;border-radius:30px;font-size:18px}
  .coins{color:#ffd54a;font-weight:bold}
  .section{max-width:1000px;margin:0 auto 22px}
  .section h2{margin-bottom:10px;font-size:22px;border-right:5px solid #ffd54a;padding-right:10px}
  .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(230px,1fr));gap:14px}
  .card{background:rgba(255,255,255,.09);border-radius:14px;padding:14px;border:2px solid transparent}
  .card.sel{border-color:#4cd964;background:rgba(76,217,100,.15)}
  .card .tname{font-size:19px;font-weight:bold;margin-bottom:6px}
  .card .row{font-size:14px;opacity:.9;margin:2px 0}
  .bar{height:6px;background:rgba(255,255,255,.15);border-radius:4px;margin:2px 0 6px;overflow:hidden}
  .bar i{display:block;height:100%;background:#4fc3f7}
  .swatch{height:22px;border-radius:6px;margin-bottom:8px}
  button{cursor:pointer;border:none;border-radius:10px;padding:10px 18px;font-size:16px;font-weight:bold;color:#fff;background:#2e86de}
  button:hover{filter:brightness(1.15)}
  button.green{background:#27ae60} button.gold{background:#e1a600;color:#222}
  button.red{background:#c0392b} button.gray{background:#576574}
  button:disabled{opacity:.45;cursor:not-allowed}
  .card button{width:100%;margin-top:8px}
  .jobs{display:flex;gap:12px;flex-wrap:wrap}
  .job{flex:1;min-width:200px;text-align:center;padding:16px;font-size:18px;cursor:pointer}
  .job.sel{border-color:#ffd54a;background:rgba(255,213,74,.15)}
  .startrow{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}
  .startrow button{font-size:20px;padding:14px 34px}

  /* HUD */
  #hud{position:fixed;inset:0;pointer-events:none;z-index:5;overflow:hidden}
  .hudbox{position:absolute;background:rgba(0,0,0,.55);border-radius:12px;padding:10px 16px}
  #hudTop{top:10px;right:10px;font-size:16px;line-height:1.7}
  #hudRoute{top:10px;left:10px;font-size:15px;line-height:1.7;max-width:260px}
  #hudSpeed{bottom:14px;left:50%;transform:translateX(-50%);text-align:center;min-width:300px}
  #spd{font-size:44px;font-weight:bold}
  #spd small{font-size:16px;opacity:.8}
  .thr{height:14px;background:rgba(255,255,255,.2);border-radius:8px;overflow:hidden;margin-top:6px}
  .thr i{display:block;height:100%;width:0;background:linear-gradient(90deg,#4cd964,#ffd54a,#ff5252)}
  #msg{position:absolute;top:90px;left:50%;transform:translateX(-50%);background:rgba(0,0,0,.75);padding:12px 24px;border-radius:12px;font-size:20px;text-align:center;max-width:90%;transition:opacity .3s}
  #tut{position:absolute;top:150px;left:50%;transform:translateX(-50%);background:rgba(20,80,160,.92);padding:12px 24px;border-radius:14px;font-size:19px;text-align:center;max-width:92%;border:2px solid #7ec8ff}
  #prompt{position:absolute;top:30%;left:50%;transform:translate(-50%,-50%);background:rgba(39,174,96,.92);padding:12px 28px;border-radius:14px;font-size:22px;font-weight:bold;text-align:center}
  #loadbar{position:absolute;top:36%;left:50%;transform:translateX(-50%);width:300px;height:18px;background:rgba(0,0,0,.6);border-radius:10px;overflow:hidden}
  #loadbar i{display:block;height:100%;width:0;background:#4cd964}
  #loadInfo{position:absolute;top:40%;left:50%;transform:translateX(-50%);background:rgba(0,0,0,.65);padding:6px 16px;border-radius:10px;font-size:16px;white-space:nowrap}
  .fp{position:absolute;left:50%;top:46%;font-size:26px;font-weight:bold;color:#ffd54a;text-shadow:0 2px 6px #000;animation:fp 1.5s ease-out forwards;pointer-events:none}
  @keyframes fp{from{opacity:1;transform:translate(-50%,0)}to{opacity:0;transform:translate(-50%,-110px)}}
  #quit{position:absolute;top:10px;left:50%;transform:translateX(-50%);pointer-events:auto;padding:6px 14px;font-size:14px}
  #hint{position:absolute;bottom:8px;left:50%;transform:translateX(-50%);font-size:12px;opacity:.75;background:rgba(0,0,0,.4);padding:4px 12px;border-radius:8px;white-space:nowrap}

  /* أزرار اللمس للايباد */
  #touch{display:none!important}
  #pad{position:fixed;inset:0;z-index:7;pointer-events:none;-webkit-touch-callout:none}
  #pad .sl{position:absolute;bottom:26px;width:74px;height:230px;border-radius:20px;background:rgba(10,14,18,.55);border:2px solid rgba(255,255,255,.28);pointer-events:auto;touch-action:none;overflow:hidden}
  #pad .sl .fill{position:absolute;left:0;right:0;bottom:0;height:0;background:linear-gradient(0deg,rgba(76,217,100,.55),rgba(255,213,74,.5))}
  #pad .sl.br .fill{background:linear-gradient(0deg,rgba(255,150,80,.5),rgba(255,70,70,.6))}
  #pad .sl .knob{position:absolute;left:6px;right:6px;height:38px;border-radius:12px;background:linear-gradient(#e8edf2,#9aa6b2);box-shadow:0 3px 8px rgba(0,0,0,.6);bottom:0}
  #pad .sl .lab{position:absolute;top:6px;left:0;right:0;text-align:center;font-size:13px;font-weight:bold;text-shadow:0 1px 3px #000}
  #pad .pb{position:absolute;width:66px;height:66px;border-radius:50%;font-size:26px;padding:0;pointer-events:auto;touch-action:none;opacity:.9;border:2px solid rgba(255,255,255,.35);display:flex;align-items:center;justify-content:center;flex-direction:column;line-height:1}
  #pad .pb small{font-size:11px;margin-top:3px;font-weight:bold}
  #pad .pb.on{box-shadow:0 0 16px 4px rgba(255,235,120,.9)}
  #padToggle{position:absolute;top:86px;left:50%;transform:translateX(-50%);pointer-events:auto;padding:6px 14px;font-size:14px}

  /* نافذة النهاية */
  #modal{position:fixed;inset:0;background:rgba(0,0,0,.7);display:flex;align-items:center;justify-content:center;z-index:20}
  #modal .box{background:#1d2b36;border-radius:18px;padding:26px 30px;min-width:300px;max-width:92%;text-align:center;border:2px solid #ffd54a}
  #modal h2{margin-bottom:14px;font-size:28px}
  #modal .line{display:flex;justify-content:space-between;gap:30px;font-size:18px;margin:6px 0}
  #modal .total{font-size:24px;color:#ffd54a;font-weight:bold;margin:14px 0;border-top:1px solid #ffffff44;padding-top:10px}
  #modal .q{margin:14px 0 8px;font-size:20px}
  #modal .btns{display:flex;gap:10px;justify-content:center;flex-wrap:wrap}
</style>
</head>
<body>

<!-- اللوبي -->
<div id="lobby">
  <h1>🚆 محاكي القطار 3D</h1>
  <div class="topbar">
    <div class="pill">🪙 الكوينز: <span class="coins" id="lbCoins">0</span></div>
    <button class="gray" id="btnTut">📖 إعادة التعليمات</button>
    <button class="red" id="btnReset">🗑️ مسح التقدم</button>
  </div>
  <div class="section">
    <h2>اختر نوع الرحلة</h2>
    <div class="jobs">
      <div class="card job sel" id="jobP" data-job="passengers">👥 توصيل الزباين (ركاب)</div>
      <div class="card job" id="jobC" data-job="cargo">📦 توصيل البضايع</div>
    </div>
  </div>
  <div class="section">
    <h2>القطارات (المتجر)</h2>
    <div class="grid" id="shop"></div>
  </div>
  <div class="section startrow">
    <button class="green" id="btnStart">▶ ابدأ الرحلة</button>
  </div>
</div>

<canvas id="c"></canvas>

<!-- واجهة اللعب -->
<div id="hud" class="hidden">
  <div class="hudbox" id="hudTop"></div>
  <div class="hudbox" id="hudRoute"></div>
  <button class="gray" id="quit">🏠 اللوبي</button>
  <button class="gray" id="camBtn" style="position:absolute;top:48px;left:50%;transform:translateX(-50%);pointer-events:auto;padding:6px 14px;font-size:14px">📷 الكاميرا (C)</button>
  <div id="msg" class="hidden"></div>
  <div id="tut" class="hidden"></div>
  <div id="prompt" class="hidden"></div>
  <div id="loadbar" class="hidden"><i></i></div>
  <div id="loadInfo" class="hidden"></div>
  <div class="hudbox" id="hudSpeed">
    <div id="spd">0 <small>كم/س</small></div>
    <div class="thr"><i id="thrBar"></i></div>
    <div style="font-size:13px;opacity:.8;margin-top:4px">الدفع (W/S) • فرامل (Space) • طوارئ (X) • زمارة (H) • أبواب (E) • فرامل اليد (B) • أضواء (L) • مساحات (V) • كاميرا (C)</div>
  </div>
  <button class="gray" id="padToggle">🎮 أزرار اللمس</button>
  <div id="hint">اسحب بالماوس للالتفات 🖱 • A يسار • D يمين • F تحت • R رجوع للأمام • الأزرار والأذرع تنضغط وتنسحب بالماوس</div>
</div>

<div id="pad" class="hidden">
  <div class="sl" id="slThr" style="left:14px"><div class="fill"></div><div class="knob"></div><div class="lab">الدفع</div></div>
  <div class="sl br" id="slBrk" style="left:100px"><div class="fill"></div><div class="knob"></div><div class="lab">الفرامل</div></div>
  <button class="pb red"   data-a="emg"   style="right:14px;bottom:26px">🛑<small>طوارئ</small></button>
  <button class="pb gold"  data-a="horn"  style="right:90px;bottom:26px">📯<small>زمارة</small></button>
  <button class="pb green" data-a="door"  style="right:166px;bottom:26px">🚪<small>أبواب</small></button>
  <button class="pb gray"  data-a="hand"  style="right:14px;bottom:102px">🔒<small>يد</small></button>
  <button class="pb gray"  data-a="lights" style="right:90px;bottom:102px">💡<small>أضواء</small></button>
  <button class="pb gray"  data-a="wipers" style="right:166px;bottom:102px">🌧<small>مساحات</small></button>
  <button class="pb gray"  data-a="bell"  style="right:242px;bottom:26px">🔔<small>جرس</small></button>
  <button class="pb gray"  data-a="radio" style="right:242px;bottom:102px">📻<small>راديو</small></button>
  <button class="pb gray"  data-a="lookC" style="left:200px;bottom:26px">👁<small>أمام</small></button>
  <button class="pb gray"  data-a="lookL" style="left:276px;bottom:26px">◀<small>يسار</small></button>
  <button class="pb gray"  data-a="lookR" style="left:352px;bottom:26px">▶<small>يمين</small></button>
  <button class="pb gray"  data-a="lookD" style="left:276px;bottom:102px">▼<small>تحت</small></button>
</div>
<div id="touch" class="hidden">
  <div class="grp">
    <button id="tbBrake" class="red">🛑</button>
    <button id="tbDown" class="gray">⬇</button>
    <button id="tbUp" class="green">⬆</button>
  </div>
  <div class="grp">
    <button id="tbHorn" class="gold">📯</button>
    <button id="tbDoor" class="green">🚪</button>
  </div>
</div>

<div id="modal" class="hidden"><div class="box" id="modalBox"></div></div>

<script>
'use strict';
/* =====================================================================
   الحفظ والبيانات
   ===================================================================== */
const SAVE_KEY='trainSim_v1';
let save=JSON.parse(localStorage.getItem(SAVE_KEY)||'null')||{coins:0,owned:[0],selected:0,tut:false};
const persist=()=>localStorage.setItem(SAVE_KEY,JSON.stringify(save));

const TRAINS=[
  {name:'القطار المبتدئ',     max:80,  acc:1.0, cap:40,  cars:2, price:0,    pm:1.0, cm:0.6, color:'#c0392b'},
  {name:'الديزل السريع',      max:110, acc:1.3, cap:60,  cars:3, price:400,  pm:1.1, cm:0.8, color:'#2980b9'},
  {name:'قطار البضائع الثقيل',max:90,  acc:1.1, cap:120, cars:4, price:900,  pm:0.5, cm:1.5, color:'#6c7a89'},
  {name:'القطار الكهربائي',   max:160, acc:1.8, cap:90,  cars:4, price:1800, pm:1.5, cm:1.0, color:'#16a085'},
  {name:'الإكسبرس الذهبي',    max:220, acc:2.2, cap:140, cars:5, price:3500, pm:2.0, cm:1.2, color:'#e0a800'},
  {name:'قطار الرصاصة',       max:320, acc:3.0, cap:200, cars:6, price:7000, pm:3.0, cm:2.0, color:'#ecf0f1'},
];
const CITIES=['الرياض','جدة','الدمام','مكة','المدينة','الخبر','تبوك','حائل','أبها','القصيم','نجران','الطائف'];
const STOPS=6;

const $=id=>document.getElementById(id);
const cvs=$('c');
let W=1,H=1,DPR=1;
const rand=(a,b)=>a+Math.random()*(b-a);
const fmt=n=>Math.round(n).toLocaleString('en');
const clamp=(v,a,b)=>Math.max(a,Math.min(b,v));
const clamp01=v=>clamp(v,0,1);
const hash=n=>{const x=Math.sin(n*127.1+311.7)*43758.5453;return x-Math.floor(x);};
const lerp=(a,b,t)=>a+(b-a)*t;
const smooth=(a,b,x)=>{const t=clamp01((x-a)/(b-a));return t*t*(3-2*t);};

/* ---------- ألوان ---------- */
const _cc={};
function C(h){ if(Array.isArray(h)) return h; return _cc[h]||(_cc[h]=[parseInt(h.slice(1,3),16)/255,parseInt(h.slice(3,5),16)/255,parseInt(h.slice(5,7),16)/255]); }
function jit(h,a,seed){ const c=C(h),k=1+(hash(seed*1.7+.3)-.5)*2*a; return [c[0]*k,c[1]*k,c[2]*k]; }
function mulC(c,k){ c=C(c); return [c[0]*k,c[1]*k,c[2]*k]; }
function mixC(a,b,t){ a=C(a); b=C(b); return [a[0]+(b[0]-a[0])*t,a[1]+(b[1]-a[1])*t,a[2]+(b[2]-a[2])*t]; }
const css=(c,a=1)=>`rgba(${(c[0]*255)|0},${(c[1]*255)|0},${(c[2]*255)|0},${a})`;
function shade(hex,p){ const n=parseInt(hex.slice(1),16); const r=clamp((n>>16)+p,0,255),g2=clamp(((n>>8)&255)+p,0,255),b=clamp((n&255)+p,0,255); return `rgb(${r},${g2},${b})`; }

/* ---------- صوت ---------- */
let actx=null;
function audio(){ if(!actx){ try{actx=new (window.AudioContext||window.webkitAudioContext)();}catch(e){} } return actx; }
function beep(freq,dur,type='sine',vol=.15,delay=0){
  const a=audio(); if(!a) return;
  const o=a.createOscillator(),gn=a.createGain();
  o.type=type; o.frequency.value=freq; gn.gain.value=vol;
  o.connect(gn); gn.connect(a.destination);
  const t=a.currentTime+delay; o.start(t);
  gn.gain.exponentialRampToValueAtTime(0.0001,t+dur); o.stop(t+dur);
}
const horn=()=>{ beep(220,.7,'sawtooth',.18); beep(277,.7,'sawtooth',.18); };
const ding=()=>{ beep(880,.15,'square',.1); beep(1320,.25,'square',.1,.12); };
const bell=()=>{ beep(1200,.35,'sine',.12); beep(1500,.3,'sine',.08,.05); };

/* ---------- الوقت: كل 10 دقايق يجي ليل ---------- */
let worldT=0,LV=1,NV=0,DK=0;
const CYC=720;
function setLight(){
  const c=worldT%CYC; let l;
  if(c<600) l=1; else if(c<630) l=1-(c-600)/30; else if(c<690) l=0; else l=(c-690)/30;
  LV=l*l*(3-2*l); NV=1-LV; DK=1-Math.abs(2*LV-1);
}
function phaseName(){ const c=worldT%CYC; return c<600?'day':c<630?'dusk':c<690?'night':'dawn'; }

/* =====================================================================
   الرياضيات (مصفوفات + متجهات)
   ===================================================================== */
const V3={
  sub:(a,b)=>[a[0]-b[0],a[1]-b[1],a[2]-b[2]], add:(a,b)=>[a[0]+b[0],a[1]+b[1],a[2]+b[2]],
  mul:(a,k)=>[a[0]*k,a[1]*k,a[2]*k], dot:(a,b)=>a[0]*b[0]+a[1]*b[1]+a[2]*b[2],
  cross:(a,b)=>[a[1]*b[2]-a[2]*b[1],a[2]*b[0]-a[0]*b[2],a[0]*b[1]-a[1]*b[0]],
  norm:a=>{const l=Math.hypot(a[0],a[1],a[2])||1;return [a[0]/l,a[1]/l,a[2]/l];}
};
function persp(fovy,asp,n,f){ const t=1/Math.tan(fovy/2); return [t/asp,0,0,0, 0,t,0,0, 0,0,(f+n)/(n-f),-1, 0,0,2*f*n/(n-f),0]; }
function mat4mul(a,b){ const o=new Array(16); for(let c=0;c<4;c++)for(let r=0;r<4;r++){ let s=0; for(let k=0;k<4;k++) s+=a[k*4+r]*b[c*4+k]; o[c*4+r]=s; } return new Float32Array(o); }

/* =====================================================================
   بناء المجسمات (إحداثيات العالم: x يمين، y فوق، s على امتداد السكة للأمام)
   ===================================================================== */
class MB{
  constructor(cap=8192){ this.a=new Float32Array(cap*10); this.n=0; this.ox=0; this.oy=0; this.os=0; }
  reset(ox,oy,os){ this.n=0; this.ox=ox; this.oy=oy; this.os=os; }
  _g(){ const b=new Float32Array(this.a.length*2); b.set(this.a); this.a=b; }
  tri(p,q,r,c,e=0){
    if((this.n+3)*10>this.a.length) this._g();
    const ox=this.ox,oy=this.oy,os=this.os;
    const ax=p[0]-ox,ay=p[1]-oy,az=os-p[2], bx=q[0]-ox,by=q[1]-oy,bz=os-q[2], cx=r[0]-ox,cy=r[1]-oy,cz=os-r[2];
    const ux=bx-ax,uy=by-ay,uz=bz-az, vx=cx-ax,vy=cy-ay,vz=cz-az;
    let nx=uy*vz-uz*vy, ny=uz*vx-ux*vz, nz=ux*vy-uy*vx; const l=Math.hypot(nx,ny,nz)||1; nx/=l; ny/=l; nz/=l;
    const a=this.a; let i=this.n*10; const c0=c[0],c1=c[1],c2=c[2];
    a[i]=ax;a[i+1]=ay;a[i+2]=az;a[i+3]=nx;a[i+4]=ny;a[i+5]=nz;a[i+6]=c0;a[i+7]=c1;a[i+8]=c2;a[i+9]=e; i+=10;
    a[i]=bx;a[i+1]=by;a[i+2]=bz;a[i+3]=nx;a[i+4]=ny;a[i+5]=nz;a[i+6]=c0;a[i+7]=c1;a[i+8]=c2;a[i+9]=e; i+=10;
    a[i]=cx;a[i+1]=cy;a[i+2]=cz;a[i+3]=nx;a[i+4]=ny;a[i+5]=nz;a[i+6]=c0;a[i+7]=c1;a[i+8]=c2;a[i+9]=e;
    this.n+=3;
  }
  quad(p,q,r,s,c,e=0){ this.tri(p,q,r,c,e); this.tri(p,r,s,c,e); }
  box(x0,x1,y0,y1,s0,s1,c,e=0,bottom=false){
    c=C(c);
    const a=[x0,y0,s0],b=[x1,y0,s0],cc=[x1,y1,s0],d=[x0,y1,s0],E=[x0,y0,s1],F=[x1,y0,s1],G=[x1,y1,s1],Hh=[x0,y1,s1];
    this.quad(d,cc,G,Hh,c,e);
    const k1=mulC(c,.82),k2=mulC(c,.9);
    this.quad(a,b,cc,d,k2,e); this.quad(E,F,G,Hh,k2,e);
    this.quad(a,E,Hh,d,k1,e); this.quad(b,F,G,cc,k1,e);
    if(bottom) this.quad(a,b,F,E,mulC(c,.6),e);
  }
  boxT(cx,cy,cs,hx,hy,hs,yaw,pitch,c,e=0){
    c=C(c); const cp=Math.cos(pitch),sp=Math.sin(pitch),cy2=Math.cos(yaw),sy=Math.sin(yaw);
    const T=(lx,ly,ls)=>{ const y2=ly*cp-ls*sp, s2=ly*sp+ls*cp; return [cx+lx*cy2+s2*sy, cy+y2, cs-lx*sy+s2*cy2]; };
    const a=T(-hx,-hy,-hs),b=T(hx,-hy,-hs),cc=T(hx,hy,-hs),d=T(-hx,hy,-hs),E=T(-hx,-hy,hs),F=T(hx,-hy,hs),G=T(hx,hy,hs),Hh=T(-hx,hy,hs);
    this.quad(d,cc,G,Hh,c,e);
    const k1=mulC(c,.82),k2=mulC(c,.9);
    this.quad(a,b,cc,d,k2,e); this.quad(E,F,G,Hh,k2,e); this.quad(a,E,Hh,d,k1,e); this.quad(b,F,G,cc,k1,e); this.quad(a,b,F,E,mulC(c,.6),e);
  }
  beam(p0,p1,w,c,e=0){
    c=C(c); const d=V3.sub(p1,p0); const ref=Math.abs(d[1])<Math.hypot(d[0],d[1],d[2])*.9?[0,1,0]:[1,0,0];
    const u=V3.mul(V3.norm(V3.cross(d,ref)),w/2), v=V3.mul(V3.norm(V3.cross(d,u)),w/2);
    const k=[V3.add(u,v),V3.sub(u,v),V3.mul(V3.add(u,v),-1),V3.sub(v,u)];
    for(let i=0;i<4;i++){ const a=k[i],b=k[(i+1)%4];
      this.quad(V3.add(p0,a),V3.add(p0,b),V3.add(p1,b),V3.add(p1,a),i%2?mulC(c,.85):c,e); }
  }
  ring(cx,y,cs,r,n,rot=0){ const o=[]; for(let i=0;i<n;i++){ const a=rot+i/n*Math.PI*2; o.push([cx+Math.cos(a)*r,y,cs+Math.sin(a)*r]); } return o; }
  tube(r0pts,r1pts,c,e=0,alt=0){ const n=r0pts.length; for(let i=0;i<n;i++){ const j=(i+1)%n; this.quad(r0pts[i],r0pts[j],r1pts[j],r1pts[i],i%2?mulC(c,1-alt):c,e); } }
  cone(cx,cs,y0,y1,r,n,c,e=0){ const rg=this.ring(cx,y0,cs,r,n,.3),top=[cx,y1,cs]; for(let i=0;i<n;i++){ const j=(i+1)%n; this.tri(rg[i],rg[j],top,i%2?mulC(c,.88):c,e); } }
  blob(cx,cy,cs,r,c,seed){
    for(let f=0;f<20;f++){
      const ids=ICOF[f],v=ids.map((id,k)=>{ const u=ICOV[id],j=.78+.5*hash(seed*3.1+id*1.7); return [cx+u[0]*r*j,cy+u[1]*r*j*.9,cs+u[2]*r*j]; });
      const ny=(ICOV[ids[0]][1]+ICOV[ids[1]][1]+ICOV[ids[2]][1])/3;
      const k=.72+.42*ny+(hash(seed*5.3+f)-.5)*.14, cc=C(c);
      this.tri(v[0],v[1],v[2],[cc[0]*k,cc[1]*k,cc[2]*k]);
    }
  }
}
const _t=(1+Math.sqrt(5))/2;
const ICOV=[[-1,_t,0],[1,_t,0],[-1,-_t,0],[1,-_t,0],[0,-1,_t],[0,1,_t],[0,-1,-_t],[0,1,-_t],[_t,0,-1],[_t,0,1],[-_t,0,-1],[-_t,0,1]].map(v=>V3.norm(v));
const ICOF=[[0,11,5],[0,5,1],[0,1,7],[0,7,10],[0,10,11],[1,5,9],[5,11,4],[11,10,2],[10,7,6],[7,1,8],[3,9,4],[3,4,2],[3,2,6],[3,6,8],[3,8,9],[4,9,5],[2,4,11],[6,2,10],[8,6,7],[9,8,1]];

/* =====================================================================
   WebGL
   ===================================================================== */
const gl=cvs.getContext('webgl',{antialias:true,alpha:false,powerPreference:'high-performance'})||cvs.getContext('experimental-webgl');
if(!gl){ document.body.innerHTML='<h2 style="padding:30px;font-family:Tahoma">المتصفح ما يدعم WebGL — جرّب Chrome أو Edge</h2>'; throw new Error('no webgl'); }
function compile(type,src){ const s=gl.createShader(type); gl.shaderSource(s,src); gl.compileShader(s); if(!gl.getShaderParameter(s,gl.COMPILE_STATUS)) console.error(gl.getShaderInfoLog(s),src); return s; }
function program(vs,fs,attrs){
  const p=gl.createProgram(); gl.attachShader(p,compile(gl.VERTEX_SHADER,vs)); gl.attachShader(p,compile(gl.FRAGMENT_SHADER,fs));
  attrs.forEach((a,i)=>gl.bindAttribLocation(p,i,a)); gl.linkProgram(p);
  if(!gl.getProgramParameter(p,gl.LINK_STATUS)) console.error(gl.getProgramInfoLog(p));
  const u={}; const n=gl.getProgramParameter(p,gl.ACTIVE_UNIFORMS);
  for(let i=0;i<n;i++){ const nm=gl.getActiveUniform(p,i).name; u[nm]=gl.getUniformLocation(p,nm); }
  return {p,u:new Proxy(u,{get:(t,k)=>(k in t?t[k]:null)})};
}
const PREC='#ifdef GL_FRAGMENT_PRECISION_HIGH\nprecision highp float;\n#else\nprecision mediump float;\n#endif\n';

const PA=program(`
attribute vec3 aP; attribute vec3 aN; attribute vec3 aC; attribute float aE;
uniform mat4 uVP; uniform vec3 uOff;
varying vec3 vC; varying vec3 vN; varying vec3 vW; varying float vE;
void main(){ vec3 w=aP+uOff; vW=w; vN=aN; vC=aC; vE=aE; gl_Position=uVP*vec4(w,1.0); }`,
PREC+`
varying vec3 vC; varying vec3 vN; varying vec3 vW; varying float vE;
uniform vec3 uSun,uSunCol,uAmbS,uAmbG,uFogCol; uniform float uFogD,uNight,uHead,uInt;
void main(){
  vec3 n=normalize(vN); if(!gl_FrontFacing) n=-n;
  float nd=max(dot(n,uSun),0.0);
  vec3 amb=mix(uAmbG,uAmbS,n.y*0.5+0.5);
  vec3 lit=vC*(amb+uSunCol*nd);
  float dist=length(vW);
  if(uHead>0.0){
    vec3 L=vW/max(dist,0.01); float c=dot(L,normalize(vec3(0.0,-0.07,-1.0)));
    float sp=smoothstep(0.86,0.975,c)*uHead/(1.0+dist*dist*0.0008);
    lit+=vC*vec3(1.0,0.93,0.75)*sp*1.7*max(dot(n,-L),0.25);
  }
  if(vE>0.5){
    vec3 ec=vE<1.5?vec3(1.0,0.78,0.42):(vE<2.5?vec3(1.0,0.14,0.08):(vE<3.5?vec3(1.0,0.97,0.86):(vE<4.5?vec3(0.3,1.0,0.5):vec3(1.0,0.55,0.15))));
    lit=mix(lit,ec,uNight*0.95);
  }
  float f=(1.0-exp(-dist*dist*uFogD*uFogD))*(1.0-uInt);
  gl_FragColor=vec4(mix(lit,uFogCol,f),1.0);
}`,['aP','aN','aC','aE']);

const PB=program(`
attribute vec3 aP; attribute vec2 aT; uniform mat4 uVP; uniform vec3 uOff; varying vec2 vT; varying vec3 vW;
void main(){ vec3 w=aP+uOff; vW=w; vT=aT; gl_Position=uVP*vec4(w,1.0); }`,
PREC+`
varying vec2 vT; varying vec3 vW; uniform sampler2D uTex; uniform vec4 uTint; uniform vec3 uFogCol; uniform float uFogD,uInt;
void main(){
  vec4 t=texture2D(uTex,vT)*uTint; float dist=length(vW);
  float f=(1.0-exp(-dist*dist*uFogD*uFogD))*(1.0-uInt);
  gl_FragColor=vec4(mix(t.rgb,uFogCol,f*t.a),t.a);
}`,['aP','aT']);

const PC=program(`
attribute vec2 aP; varying vec2 vP; void main(){ vP=aP; gl_Position=vec4(aP,0.9999,1.0); }`,
PREC+`
varying vec2 vP;
uniform vec3 uR,uU,uF,uTop,uBot,uSun,uMoon,uCloud;
uniform float uT,uA,uNight,uDusk,uTime,uSunVis;
float h21(vec2 p){ return fract(sin(dot(p,vec2(127.1,311.7)))*43758.5453); }
float vn(vec2 p){ vec2 i=floor(p),f=fract(p); f=f*f*(3.0-2.0*f);
  return mix(mix(h21(i),h21(i+vec2(1.0,0.0)),f.x),mix(h21(i+vec2(0.0,1.0)),h21(i+vec2(1.0,1.0)),f.x),f.y); }
float fbm(vec2 p){ float a=0.5,s=0.0; for(int i=0;i<5;i++){ s+=a*vn(p); p=p*2.03+vec2(17.0,9.0); a*=0.5; } return s; }
void main(){
  vec3 d=normalize(uF+uR*(vP.x*uA*uT)+uU*(vP.y*uT));
  float y=d.y;
  vec3 col=mix(uBot,uTop,pow(clamp(y,0.0,1.0),0.5));
  float sd=max(dot(d,uSun),0.0);
  col+=vec3(1.0,0.9,0.65)*(pow(sd,900.0)*4.0+pow(sd,40.0)*0.45+pow(sd,5.0)*0.10*(0.4+uDusk))*uSunVis;
  float md=max(dot(d,uMoon),0.0);
  col+=vec3(0.85,0.9,1.0)*(smoothstep(0.99935,0.9997,md)*1.2+pow(md,60.0)*0.25)*uNight;
  if(y>0.0 && uNight>0.02){
    vec3 cell=floor(d*vec3(230.0)); float h=h21(cell.xy+cell.z*7.13); float tw=0.6+0.4*sin(uTime*3.0+h*40.0);
    col+=vec3(1.0)*step(0.9965,h)*tw*uNight*smoothstep(0.0,0.15,y);
  }
  if(y>-0.02){
    vec2 p=d.xz/(max(y,0.0)+0.22)*1.35+vec2(uTime*0.012,uTime*0.005);
    float n=fbm(p); float cov=smoothstep(0.50,0.74,n);
    float sh=0.62+0.38*fbm(p*1.9+3.0);
    float fade=smoothstep(0.0,0.2,y);
    col=mix(col,uCloud*sh,cov*fade*0.92);
  }
  col=mix(col,uBot,pow(1.0-clamp(y,0.0,1.0),7.0)*0.85);
  gl_FragColor=vec4(col,1.0);
}`,['aP']);

const buf={
  quad:gl.createBuffer(), sky:gl.createBuffer(), dyn:gl.createBuffer(), dynTex:gl.createBuffer()
};
gl.bindBuffer(gl.ARRAY_BUFFER,buf.sky); gl.bufferData(gl.ARRAY_BUFFER,new Float32Array([-1,-1,1,-1,-1,1,1,-1,1,1,-1,1]),gl.STATIC_DRAW);

function enableAttr(n){ for(let i=0;i<4;i++){ if(i<n) gl.enableVertexAttribArray(i); else gl.disableVertexAttribArray(i); } }
function bindMesh(vbo){ gl.bindBuffer(gl.ARRAY_BUFFER,vbo); gl.vertexAttribPointer(0,3,gl.FLOAT,false,40,0); gl.vertexAttribPointer(1,3,gl.FLOAT,false,40,12); gl.vertexAttribPointer(2,3,gl.FLOAT,false,40,24); gl.vertexAttribPointer(3,1,gl.FLOAT,false,40,36); }
function makeVBO(mb){ const v=gl.createBuffer(); gl.bindBuffer(gl.ARRAY_BUFFER,v); gl.bufferData(gl.ARRAY_BUFFER,mb.a.slice(0,mb.n*10),gl.STATIC_DRAW); return {vbo:v,n:mb.n}; }
function freeMesh(m){ if(m&&m.vbo) gl.deleteBuffer(m.vbo); }

function canvasTex(cv){
  const t=gl.createTexture(); gl.bindTexture(gl.TEXTURE_2D,t);
  gl.texParameteri(gl.TEXTURE_2D,gl.TEXTURE_MIN_FILTER,gl.LINEAR); gl.texParameteri(gl.TEXTURE_2D,gl.TEXTURE_MAG_FILTER,gl.LINEAR);
  gl.texParameteri(gl.TEXTURE_2D,gl.TEXTURE_WRAP_S,gl.CLAMP_TO_EDGE); gl.texParameteri(gl.TEXTURE_2D,gl.TEXTURE_WRAP_T,gl.CLAMP_TO_EDGE);
  gl.texImage2D(gl.TEXTURE_2D,0,gl.RGBA,gl.RGBA,gl.UNSIGNED_BYTE,cv); return t;
}
function updTex(t,cv){ gl.bindTexture(gl.TEXTURE_2D,t); gl.texImage2D(gl.TEXTURE_2D,0,gl.RGBA,gl.RGBA,gl.UNSIGNED_BYTE,cv); }
function mkCanvas(w,h){ const c=document.createElement('canvas'); c.width=w; c.height=h; return c; }

/* نسيج الإضاءة (توهج) */
const glowTex=(()=>{ const c=mkCanvas(64,64),x=c.getContext('2d'),gr=x.createRadialGradient(32,32,0,32,32,32);
  gr.addColorStop(0,'rgba(255,255,255,1)'); gr.addColorStop(.25,'rgba(255,255,255,.55)'); gr.addColorStop(1,'rgba(255,255,255,0)');
  x.fillStyle=gr; x.fillRect(0,0,64,64); return canvasTex(c); })();

/* لوحات الأسماء */
const signCache={};
function signTex(text,bg='#1e3a5f',fg='#ffffff',w=512,h=128){
  const k=text+bg+fg; if(signCache[k]) return signCache[k];
  const c=mkCanvas(w,h),x=c.getContext('2d');
  x.fillStyle=bg; x.fillRect(0,0,w,h); x.strokeStyle=fg; x.lineWidth=6; x.strokeRect(6,6,w-12,h-12);
  x.fillStyle=fg; x.font='bold '+Math.round(h*.52)+'px Tahoma'; x.textAlign='center'; x.textBaseline='middle'; x.fillText(text,w/2,h/2+3);
  return (signCache[k]=canvasTex(c));
}

/* =====================================================================
   حالة اللعبة
   ===================================================================== */
let g={state:'lobby'};
let job='passengers';
let viewMode='cab';
function T(){ return TRAINS[save.selected]; }
function toggleView(){ viewMode=viewMode==='cab'?'out':'cab'; if(g.state!=='lobby') showMsg(viewMode==='cab'?'📷 كاميرا السائق':'📷 كاميرا خارجية (اسحب بالماوس للدوران وعجلة الماوس للتقريب)',3); }
$('camBtn').onclick=toggleView;

/* رأس السائق */
let yaw=0,pitch=-0.06,yawT=0,pitchT=-0.06;
const PITCH0=-0.06;
let oyaw=0.75,opitch=0.2,odist=44;

/* =====================================================================
   المدخلات
   ===================================================================== */
const keys={};
const keyMap={KeyW:'w',ArrowUp:'w',KeyS:'s',ArrowDown:'s',Space:'space',KeyX:'x',KeyH:'h',KeyE:'e',KeyC:'c',KeyL:'l',KeyV:'v',KeyB:'b',KeyA:'lookl',ArrowLeft:'lookl',KeyD:'lookr',ArrowRight:'lookr',KeyF:'lookd',KeyR:'r'};
addEventListener('keydown',e=>{ const k=keyMap[e.code]; if(!k) return; e.preventDefault(); if(!keys[k]) onPress(k); keys[k]=true; });
addEventListener('keyup',e=>{ const k=keyMap[e.code]; if(!k) return; keys[k]=false; if(k.startsWith('look')){ yawT=0; pitchT=PITCH0; } });
function bindTouch(id,k){ const el=$(id); el.addEventListener('pointerdown',e=>{e.preventDefault(); if(!keys[k]) onPress(k); keys[k]=true;}); ['pointerup','pointerleave','pointercancel'].forEach(ev=>el.addEventListener(ev,()=>keys[k]=false)); }
bindTouch('tbUp','w'); bindTouch('tbDown','s'); bindTouch('tbBrake','space'); bindTouch('tbHorn','h'); bindTouch('tbDoor','e');

function onPress(k){
  if(g.state==='lobby'||g.state==='done') return;
  if(k==='h'){ horn(); g.horned=true; g.hornT=.5; }
  if(k==='e') tryDoors();
  if(k==='c') toggleView();
  if(k==='l') g.lights=!g.lights;
  if(k==='v') g.wipers=!g.wipers;
  if(k==='b') toggleHand();
  if(k==='r'){ yawT=0; pitchT=PITCH0; }
  if(viewMode==='cab'){
    if(k==='lookl'){ yawT=-1.45; pitchT=-0.12; }
    if(k==='lookr'){ yawT=1.45; pitchT=-0.12; }
    if(k==='lookd'){ yawT=0; pitchT=-0.95; }
  }
}
function toggleHand(){
  if(g.state==='lobby'||g.state==='done') return;
  if(!g.hand&&g.v>0.8){ showMsg('لا ترفع فرامل اليد والقطار يتحرك!',2); return; }
  g.hand=!g.hand; beep(300,.12,'square',.08);
  showMsg(g.hand?'🔒 فرامل اليد: مفعّلة':'🔓 فرامل اليد: محرّرة',2);
}

/* =====================================================================
   اللوبي
   ===================================================================== */
function renderLobby(){
  $('lbCoins').textContent=fmt(save.coins);
  const shop=$('shop'); shop.innerHTML='';
  TRAINS.forEach((t,i)=>{
    const owned=save.owned.includes(i),sel=save.selected===i;
    const d=document.createElement('div'); d.className='card'+(sel?' sel':'');
    d.innerHTML=`
      <div class="swatch" style="background:${t.color}"></div>
      <div class="tname">${t.name}</div>
      <div class="row">⚡ السرعة: ${t.max} كم/س</div><div class="bar"><i style="width:${t.max/320*100}%"></i></div>
      <div class="row">🚀 التسارع: ${t.acc}</div><div class="bar"><i style="width:${t.acc/3*100}%"></i></div>
      <div class="row">👥 السعة: ${t.cap} • 🚃 العربات: ${t.cars}</div>
      <div class="row">ربح ركاب ×${t.pm} • ربح بضائع ×${t.cm}</div>`;
    const b=document.createElement('button');
    if(sel){ b.textContent='✔ مستخدم حالياً'; b.className='green'; b.disabled=true; }
    else if(owned){ b.textContent='اختيار'; b.onclick=()=>{save.selected=i;persist();renderLobby();}; }
    else { b.textContent='شراء 🪙 '+fmt(t.price); b.className='gold'; b.disabled=save.coins<t.price;
      b.onclick=()=>{ if(save.coins>=t.price){ save.coins-=t.price; save.owned.push(i); save.selected=i; persist(); ding(); renderLobby(); } }; }
    d.appendChild(b); shop.appendChild(d);
  });
}
document.querySelectorAll('.job').forEach(el=>el.onclick=()=>{ job=el.dataset.job; document.querySelectorAll('.job').forEach(x=>x.classList.toggle('sel',x===el)); });
$('btnStart').onclick=()=>{ audio(); startTrip(); };
$('btnTut').onclick=()=>{ save.tut=false; persist(); alert('تمام! لما تبدأ رحلة بتظهر لك التعليمات من جديد.'); };
$('btnReset').onclick=()=>{ if(confirm('متأكد تبي تمسح كل التقدم والكوينز؟')){ save={coins:0,owned:[0],selected:0,tut:false}; persist(); renderLobby(); } };
$('quit').onclick=()=>{ if(confirm('تبي ترجع اللوبي؟ بتخسر الرحلة الحالية بدون مكافأة.')) goLobby(); };
function goLobby(){
  g={state:'lobby'}; clearChunks();
  $('modal').classList.add('hidden'); $('hud').classList.add('hidden'); $('touch').classList.add('hidden'); $('lobby').classList.remove('hidden');
  renderLobby();
}

/* =====================================================================
   الركاب
   ===================================================================== */
function genPeople(st){
  st.people=[];
  const n=Math.round(9+hash(st.x*0.01)*6);
  for(let i=0;i<n;i++){
    const right=i<n-3;
    st.people.push({state:'wait',s:st.x+rand(-75,45),lat:(right?1:-1)*rand(3,6.2),type:hashType(st.x+i),seed:st.x*.31+i*7.7,ph:rand(0,6)});
  }
}
function hashType(n){ const h=hash(n*2.7); return h<.5?'thobe':h<.75?'abaya':'casual'; }
function doorList(){
  const out=[],t=T(); for(let i=0;i<t.cars;i++){ const base=g.x-16-1-i*19; out.push(base-4.5,base-13.5); } return out;
}
function personPos(p,t){
  if(p.state==='wait') return {s:p.s,lat:p.lat,vis:true,mv:false,face:p.lat>0?-1:1};
  const u=(t-p.t0)/p.dur;
  if(p.state==='board'){
    if(u<0) return {s:p.from,lat:p.latFrom,vis:true,mv:false,face:-1};
    if(u>=1) return {vis:false};
    return {s:p.from+(p.doorS-p.from)*u,lat:p.latFrom+(1.95-p.latFrom)*u,vis:true,mv:true,dx:(1.95-p.latFrom),ds:(p.doorS-p.from)};
  }
  if(u<0||u>=1.6) return {vis:false};
  const e=Math.min(1,u);
  return {s:p.from+(p.to-p.from)*e,lat:p.latFrom+(p.latTo-p.latFrom)*e,vis:true,mv:u<1,dx:p.latTo-p.latFrom,ds:p.to-p.from,face:-1};
}
function personTime(st){ return (g.state==='loading'&&st===g.route[g.next])?g.loadT:1e9; }

/* =====================================================================
   بدء الرحلة
   ===================================================================== */
function legGap(t){ const vmax=t.max/3.6; return Math.max(1500,1.6*(vmax*vmax/6)+500)*rand(1,1.35); }
function startTrip(){
  const t=T();
  const names=[...CITIES].sort(()=>Math.random()-.5).slice(0,STOPS);
  const route=[]; let x=0;
  names.forEach((n,i)=>{ if(i>0) x+=legGap(t); const st={name:n,x:Math.round(x),served:false}; genPeople(st); route.push(st); });
  g={
    state:'running',x:0,v:0,th:0,time:0,next:1,route,
    load:0,job,coins:0,penalties:0,emerg:0,delivered:0,deliveredTotal:0,legsBonus:0,
    loadT:0,loadDur:5,plan:null,popped:0,msgT:0,warnT:0,
    tutStep:save.tut?-1:0,horned:false,braked:false,started:false,sawRight:false,sawDown:false,
    brk:0,brkShown:0,ampShown:0,hornT:0,bellT:0,lights:false,wipers:false,wiperP:0,press:null,
    hand:true,radio:false,radioT:0,ph:phaseName(),clack:0,gates:{},xings:[]
  };
  g.xings=crossingList(g.route);
  g.route[0].served=true;
  g.load=Math.round(t.cap*rand(.5,1));
  clearChunks(); yaw=0; pitch=PITCH0; yawT=0; pitchT=PITCH0;
  $('lobby').classList.add('hidden'); $('hud').classList.remove('hidden'); $('touch').classList.remove('hidden'); $('modal').classList.add('hidden');
  showMsg(`بدأت الرحلة من ${route[0].name} إلى ${route[route.length-1].name} — حرر فرامل اليد أول (B)`,5);
}
function crossingList(route){
  const out=[],end=route[route.length-1].x+400;
  for(let m=450;m<end;m+=450){ if(hash(m/450*3.7)<.5) continue; if(route.some(s=>Math.abs(s.x-m)<280)) continue; out.push(m); }
  return out;
}
function isXing(s){ const L=g.xings; for(let i=0;i<L.length;i++) if(Math.abs(L[i]-s)<4.3) return true; return false; }

/* =====================================================================
   الرسائل والتعليمات
   ===================================================================== */
function showMsg(t,sec=3){ const m=$('msg'); m.textContent=t; m.classList.remove('hidden'); g.msgT=sec; }
const TUT=[
  {t:'قبل ما تتحرك: حرر <b>فرامل اليد</b> — اضغط <b>B</b>، أو انزل بنظرك (<b>F</b>) واضغط على الذراع',ok:()=>!g.hand},
  {t:'الحين ارفع <b>ذراع الدفع</b> بالماوس (أو اضغط <b>W</b>) لتحريك القطار 🚂',ok:()=>g.th>0.3},
  {t:'ممتاز! انتظر لين تصل سرعتك <b>40 كم/س</b>',ok:()=>g.v*3.6>=40},
  {t:'للتخفيف أنزل ذراع الدفع (أو S)، وللفرملة اسحب <b>ذراع الفرامل</b> لتحت (أو Space)',ok:()=>g.braked},
  {t:'اضغط زر <b>زمارة</b> (أو H) لتزمير القطار 📯',ok:()=>g.horned},
  {t:'التفت! اسحب الماوس يمين أو اضغط <b>D</b> وشوف الرصيف والباب من الشباك 🪟',ok:()=>g.sawRight},
  {t:'وانزل بنظرك تحت (<b>F</b>) وشوف فرامل اليد ودرج الأجرة والراديو 👇',ok:()=>g.sawDown},
  {t:'توجه للمحطة 🏁 وأوقف القطار داخل الرصيف ثم اضغط زر <b>أبواب</b> (أو E) — بينزلون الركاب ويركبون غيرهم وتاخذ الفلوس 🪙',ok:()=>g.state==='loading'}
];
function updateTut(){
  const el=$('tut');
  if(g.tutStep<0||g.tutStep>=TUT.length){ el.classList.add('hidden'); return; }
  el.classList.remove('hidden');
  el.innerHTML=`<div style="font-size:13px;opacity:.8;margin-bottom:4px">تعليمات (${g.tutStep+1}/${TUT.length})</div>`+TUT[g.tutStep].t;
  if(TUT[g.tutStep].ok()){ g.tutStep++; ding(); if(g.tutStep>=TUT.length){ save.tut=true; persist(); showMsg('✅ خلصت التعليمات! بالتوفيق يا كابتن',4); } }
}

/* =====================================================================
   الأبواب والمحطات
   ===================================================================== */
function inZone(){ const st=g.route[g.next]; if(!st) return false; return Math.abs(g.x-st.x)<=70; }
function popCoin(n){ if(n<=0) return; const s=document.createElement('div'); s.className='fp'; s.textContent='+'+n+' 🪙'; s.style.marginLeft=rand(-70,70)+'px'; $('hud').appendChild(s); setTimeout(()=>{ if(s.remove) s.remove(); },1500); }
function tryDoors(){
  if(g.state!=='running') return;
  const st=g.route[g.next];
  if(!st||!inZone()){ showMsg('لازم تكون داخل الرصيف عشان تفتح الأبواب',2); return; }
  if(g.v>0.5){ showMsg('أوقف القطار تماماً أول!',2); return; }
  const t=T(),last=g.next===g.route.length-1;
  const mult=g.job==='passengers'?t.pm:t.cm,unit=g.job==='passengers'?0.7:1.0;
  g.plan={alight:g.load,board:last?0:Math.round(t.cap*rand(.5,1)),earn:Math.round(g.load*unit*mult)};
  g.loadDur=Math.min(9,3.5+(g.plan.alight+g.plan.board)/35);
  g.state='loading'; g.loadT=0; g.popped=0;
  const doors=doorList(); g.doors=doors;
  const nb=Math.min(10,Math.round(g.plan.board/5)),na=Math.min(10,Math.round(g.plan.alight/5));
  const cands=st.people.filter(p=>p.state==='wait'&&p.lat>0).sort((a,b)=>Math.abs(a.s-g.x)-Math.abs(b.s-g.x));
  cands.slice(0,nb).forEach((p,i)=>{ const dS=doors[i%doors.length]; p.state='board'; p.from=p.s; p.latFrom=p.lat; p.doorS=dS; p.t0=.25*g.loadDur*i/Math.max(1,nb); p.dur=1.2+Math.hypot(p.s-dS,p.lat-1.95)/1.6; });
  for(let i=0;i<na;i++){
    const dS=doors[i%doors.length];
    st.people.push({state:'alight',from:dS,latFrom:1.95,to:dS+(Math.random()>.5?1:-1)*rand(10,40),latTo:rand(3.2,6.5),t0:.12*g.loadDur+(i/Math.max(1,na))*.5*g.loadDur,dur:4,type:hashType(st.x*3+i*5),seed:st.x+i*13,ph:rand(0,6)});
  }
  beep(700,.12,'square',.07); beep(500,.15,'square',.07,.12);
}
function finishLoading(){
  const st=g.route[g.next],unitName=g.job==='passengers'?'راكب':'طن';
  g.coins+=g.plan.earn; g.delivered+=g.plan.alight; ding();
  const legBonus=Math.round((st.x-g.route[g.next-1].x)/40);
  g.coins+=legBonus; g.legsBonus+=legBonus; popCoin(legBonus);
  st.served=true;
  $('loadbar').classList.add('hidden'); $('loadInfo').classList.add('hidden');
  if(g.next===g.route.length-1){ endTrip(true); return; }
  const got=g.plan.earn+legBonus; g.load=g.plan.board;
  showMsg(`وصلت ${st.name} • نزل ${g.delivered} ${unitName} وركب ${g.load} • +${got} 🪙`,4);
  g.deliveredTotal+=g.delivered; g.delivered=0; g.next++; g.state='running';
}
function endTrip(success){
  g.state='done'; keys.x=false; g.deliveredTotal+=g.delivered;
  const smoothBonus=(success&&g.emerg===0)?50:0, total=Math.max(0,Math.round(g.coins+smoothBonus-g.penalties));
  save.coins+=total; persist();
  const unitName=g.job==='passengers'?'راكب':'طن بضاعة';
  $('modalBox').innerHTML=`
    <h2>${success?'🎉 وصلت بالسلامة!':'❌ فشلت الرحلة'}</h2>
    <div class="line"><span>${g.job==='passengers'?'الركاب':'البضائع'} المنقولة</span><b>${g.deliveredTotal} ${unitName}</b></div>
    <div class="line"><span>أرباح التوصيل</span><b>+${fmt(g.coins-g.legsBonus)} 🪙</b></div>
    <div class="line"><span>مكافأة المسافة</span><b>+${fmt(g.legsBonus)} 🪙</b></div>
    ${smoothBonus?`<div class="line"><span>مكافأة قيادة ناعمة</span><b>+${smoothBonus} 🪙</b></div>`:''}
    ${g.penalties?`<div class="line"><span>غرامات</span><b style="color:#ff6b6b">-${g.penalties} 🪙</b></div>`:''}
    <div class="total">المجموع: +${fmt(total)} 🪙<br><span style="font-size:15px;color:#fff">رصيدك: ${fmt(save.coins)} 🪙</span></div>
    <div class="q">هل تريد بدء رحلة جديدة؟</div>
    <div class="btns"><button class="green" id="mNew">🚆 رحلة جديدة</button><button class="gray" id="mLobby">🏠 الذهاب إلى اللوبي</button></div>`;
  $('modal').classList.remove('hidden');
  $('mNew').onclick=()=>startTrip(); $('mLobby').onclick=()=>goLobby();
}

/* =====================================================================
   التحديث
   ===================================================================== */
function update(dt){
  worldT+=dt; setLight();
  if(g.state==='lobby'||g.state==='done') return;
  const t=T(),vmax=t.max/3.6;
  const ph=phaseName();
  if(g.ph!==ph){ g.ph=ph;
    if(ph==='dusk') showMsg('🌅 بدأ الغروب — شغّل الأضواء (L)',5);
    else if(ph==='night') showMsg('🌙 دخل الليل',4);
    else if(ph==='dawn') showMsg('🌄 بدأ الفجر',4);
    else showMsg('☀️ طلع النهار',3); }

  // الالتفات
  const kk=Math.min(1,dt*7);
  yaw+=(yawT-yaw)*kk; pitch+=(pitchT-pitch)*kk;
  if(yaw>0.9) g.sawRight=true;
  if(pitch<-0.6) g.sawDown=true;

  g.hornT=Math.max(0,g.hornT-dt); g.bellT=Math.max(0,g.bellT-dt);
  if(g.wipers) g.wiperP+=dt*4;
  g.brkShown+=(Math.max(keys.space?1:0,g.brk)-g.brkShown)*Math.min(1,dt*6);
  g.ampShown+=((g.state==='running'&&!g.hand?g.th*(1-g.v/vmax):0)-g.ampShown)*Math.min(1,dt*5);
  if(g.radio){ g.radioT-=dt; if(g.radioT<=0){ g.radioT=2.4; [392,494,587,494].forEach((f,i)=>beep(f,.4,'sine',.035,i*.3)); } }

  if(keys.w) g.th=Math.min(1,g.th+0.7*dt);
  if(keys.s) g.th=Math.max(0,g.th-1.0*dt);

  if(g.state==='running'){
    let a=0;
    if(g.hand){ a-=6; if(g.th>0.1){ g.warnT-=dt; if(g.warnT<=0){ showMsg('🔒 فرامل اليد شغالة! حررها (B)',3); g.warnT=3; } } }
    else a+=g.th*t.acc*(1-g.v/vmax);
    if(g.v>0) a-=0.05+0.0008*g.v*g.v;
    g.braked=false;
    const bk=Math.max(keys.space?1:0,g.brk);
    if(bk>0.02){ a-=3.0*bk; g.braked=true; if(g.v>1) g.th=Math.max(0,g.th-2*bk*dt); }
    if(keys.x){ a-=6.0; g.braked=true; g.th=0; if(g.v>8) g.emerg+=dt; }
    g.v=Math.max(0,g.v+a*dt);
    g.x+=g.v*dt; g.time+=dt;
    if(g.v>0.2) g.started=true;
    g.clack+=g.v*dt; if(g.clack>25){ g.clack-=25; if(g.v>2){ beep(95+Math.random()*25,.05,'square',Math.min(.05,.01+g.v*.0006)); beep(120,.04,'square',.02,.08); } }
    const st=g.route[g.next];
    if(st&&g.x>st.x+70){
      g.penalties+=40; st.served=true;
      if(g.next===g.route.length-1){ showMsg('فوّت المحطة الأخيرة!',3); endTrip(false); return; }
      showMsg(`فوّت محطة ${st.name}! غرامة 40 🪙`,4); g.next++;
    }
  } else if(g.state==='loading'){
    g.v=0; g.th=0; g.loadT+=dt;
    const p=Math.min(1,g.loadT/g.loadDur);
    $('loadbar').classList.remove('hidden'); $('loadInfo').classList.remove('hidden');
    $('loadbar').firstElementChild.style.width=(p*100)+'%';
    const shown=Math.round(g.plan.earn*p);
    if(shown-g.popped>=4||(p>=1&&shown>g.popped)){ popCoin(shown-g.popped); g.popped=shown; ding(); }
    $('loadInfo').textContent=`نزل ${Math.round(g.plan.alight*Math.min(1,p*1.7))} • ركب ${Math.round(g.plan.board*clamp01((p-.3)*1.6))} • +${shown} 🪙`;
    if(g.loadT>=g.loadDur) finishLoading();
  }
  if(g.msgT>0){ g.msgT-=dt; if(g.msgT<=0) $('msg').classList.add('hidden'); }
  if(g.state==='done') return;
  updateTut(); updateHud();
}
function updateHud(){
  const st=g.route[g.next],cab=viewMode==='cab';
  $('hudSpeed').classList.toggle('hidden',cab); $('touch').classList.toggle('hidden',cab);
  $('hint').classList.toggle('hidden',!cab||g.time>20||padOn); syncPad();
  $('spd').innerHTML=`${Math.round(g.v*3.6)} <small>كم/س</small>`;
  $('thrBar').style.width=(g.th*100)+'%';
  const dist=st?Math.max(0,Math.round(st.x-g.x)):0,unit=g.job==='passengers'?'👥 ركاب':'📦 طن';
  const c=worldT%CYC,day=c<600,nightIn=day?Math.ceil(600-c):0;
  $('hudTop').innerHTML=`🪙 ${fmt(g.coins-g.penalties)}<br>${unit}: ${g.load}<br>⏱ ${Math.floor(g.time/60)}:${String(Math.floor(g.time%60)).padStart(2,'0')}<br>${LV>.5?'☀️ نهار':'🌙 ليل'}${day?` • الليل بعد ${Math.floor(nightIn/60)}:${String(nightIn%60).padStart(2,'0')}`:''}`;
  $('hudRoute').innerHTML=g.route.map((r,i)=>`${i<g.next?'✅':(i===g.next?'🏁':'⚪')} ${r.name}`).join('<br>')+(st?`<br><b>المسافة للمحطة: ${dist>=1000?(dist/1000).toFixed(1)+' كم':dist+' م'}</b>`:'');
  const p=$('prompt');
  if(g.state==='running'&&inZone()){ p.classList.remove('hidden'); p.textContent=g.v>0.5?'أنت في الرصيف — أوقف القطار!':'اضغط E لفتح الأبواب 🚪'; p.style.background='rgba(39,174,96,.92)'; }
  else if(g.state==='running'&&st&&dist<800&&g.v*3.6>60){ p.classList.remove('hidden'); p.textContent='⚠ المحطة قريبة — خفف السرعة!'; p.style.background='rgba(230,126,34,.92)'; }
  else p.classList.add('hidden');
}

/* =====================================================================
   توليد العالم (قطع طول كل منها 100 متر)
   ===================================================================== */
const CH=100;
const chunks=new Map();
function clearChunks(){ chunks.forEach(c=>{ freeMesh(c.main); freeMesh(c.dec); }); chunks.clear(); }

const GRASS=['#7a9d4f','#86a756','#6f9448','#93ab5c','#7c9a52','#a0a862'];
const DRY=['#9aa35d','#a8a864','#8f9a58','#b0aa6a'];
const CROP=[['#7fae52','#6f9f48'],['#8b6b47','#7c5d3c'],['#b9b070','#c6bd7e'],['#6f9a45','#5f8a3c']];
const HOUSE_COLS=['#e8d8b4','#d9c9a3','#f0e6d2','#c9b79c','#e2cfb6','#efe3cc'];
const ROOF_COLS=['#8e5b3a','#7a4a3a','#6d6d6d','#9a6a45'];
const CAR_COLS=['#c0392b','#2980b9','#ecf0f1','#27ae60','#f39c12','#34495e','#8e44ad','#f4f4f4','#222a31'];
const ROAD_X0=15.5,ROAD_X1=23.3;

function palm(B,x,s,seed){
  const r=n=>hash(seed*9.1+n), Hh=6.5+r(1)*4.5, lean=(r(2)-.5)*1.5, ang=r(3)*6.28, lx=Math.cos(ang)*lean, ls=Math.sin(ang)*lean;
  let prev=B.ring(x,0,s,.34,6);
  for(let i=1;i<=6;i++){ const t=i/6, cur=B.ring(x+lx*t*t,Hh*t,s+ls*t*t,.31-.13*t,6); B.tube(prev,cur,i%2?C('#6b5841'):C('#85735a'),0,.18); prev=cur; }
  const cx=x+lx,cs=s+ls;
  const nf=11+Math.floor(r(4)*3);
  for(let i=0;i<nf;i++){
    const a=i/nf*6.283+r(i+10)*.5, len=2.8+r(i+30)*1.5, lift=1.3+r(i+50)*.8, drop=2.8+r(i+70)*1.4, wmax=.5+r(i+90)*.25;
    const dx=Math.cos(a),ds=Math.sin(a),px=-ds,ps=dx, col=i%2?C('#2f6b2a'):C('#3d8a35');
    let last=null;
    for(let k=0;k<=4;k++){
      const t=k/4, hh=Hh+lift*t-drop*t*t, w=wmax*Math.sin(Math.PI*(.12+.88*t))*(1-.2*t);
      const c0=[cx+dx*len*t,hh,cs+ds*len*t];
      const cur=[[c0[0]+px*w,c0[1]-.15*w,c0[2]+ps*w],[c0[0]-px*w,c0[1]-.15*w,c0[2]-ps*w]];
      if(last) B.quad(last[0],last[1],cur[1],cur[0],mulC(col,.92+.16*t),0);
      last=cur;
    }
  }
  for(let i=0;i<3;i++) B.box(cx-.2+i*.18,cx-.04+i*.18,Hh-.5,Hh-.05,cs-.12,cs+.1,'#7a4a1e');
}
function leafy(B,x,s,seed){
  const r=n=>hash(seed*11.3+n), Hh=2.6+r(1)*1.4;
  let prev=B.ring(x,0,s,.32,6);
  for(let i=1;i<=3;i++){ const t=i/3,cur=B.ring(x+(r(2)-.5)*.4*t,Hh*t,s+(r(3)-.5)*.4*t,.3-.15*t,6); B.tube(prev,cur,i%2?C('#5a4330'):C('#6b5240'),0,.15); prev=cur; }
  const cols=['#2f5f26','#3f7a32','#4b8a37','#58963f'], n=5+Math.floor(r(4)*3);
  for(let i=0;i<n;i++){ const a=i/n*6.28+r(i+5), d=r(i+20)*1.8; B.blob(x+Math.cos(a)*d,Hh+1.4+r(i+40)*1.6,s+Math.sin(a)*d,1.1+r(i+60)*.9,cols[Math.floor(r(i+80)*4)],seed*7+i); }
}
function cypress(B,x,s,seed){
  const r=n=>hash(seed*5.5+n), Hh=6+r(1)*3;
  B.box(x-.14,x+.14,0,.8,s-.14,s+.14,'#4a3626');
  for(let i=0;i<5;i++){ const t=i/5; B.cone(x,s,.7+t*Hh*.7,1.8+t*Hh*.7+Hh*.35,(1.25-t*.7),7,i%2?C('#1f4a2a'):C('#2a5c33')); }
}
function bush(B,x,s,seed){ const r=n=>hash(seed*3.3+n); for(let i=0;i<3;i++) B.blob(x+(r(i)-.5)*1.2,.45+r(i+5)*.25,s+(r(i+9)-.5)*1.2,.55+r(i+13)*.4,i%2?'#3a6b2c':'#4a7d34',seed*3+i); }

function house(B,Bd,o){
  const {x0,x1,s0,s1,h,col,roof,tall,idx}=o, xm=(x0+x1)/2;
  B.box(x0,x1,0,h,s0,s1,col,0,false);
  const lowC=mulC(col,.78); B.box(x0-.05,x1+.05,0,.5,s0-.05,s1+.05,lowC);
  if(!tall){
    const rh=1.7, rc=C(roof);
    B.quad([x0-.4,h,s0-.4],[x0-.4,h,s1+.4],[xm,h+rh,s1+.4],[xm,h+rh,s0-.4],rc);
    B.quad([x1+.4,h,s0-.4],[x1+.4,h,s1+.4],[xm,h+rh,s1+.4],[xm,h+rh,s0-.4],mulC(rc,.88));
    B.tri([x0-.4,h,s0-.4],[x1+.4,h,s0-.4],[xm,h+rh,s0-.4],mulC(col,.85));
    B.tri([x0-.4,h,s1+.4],[x1+.4,h,s1+.4],[xm,h+rh,s1+.4],mulC(col,.85));
  } else {
    B.box(x0-.2,x1+.2,h,h+.5,s0-.2,s1+.2,'#8d8f93');
    B.box(xm-1.5,xm+1.5,h+.5,h+1.6,s0+1,s0+3.5,'#9a9da1');
  }
  // نوافذ على الوجه المقابل للسكة (قريب من x=0) وعلى وجه الشارع
  const faceX=(Math.abs(x0)<Math.abs(x1))?x0:x1, dirx=faceX===x0?-1:1;
  const rows=tall?Math.max(1,Math.floor(h/3.3)):(h>5?2:1), cols=Math.max(1,Math.floor((s1-s0)/3.2));
  for(let rw=0;rw<rows;rw++) for(let c=0;c<cols;c++){
    const ws=s0+1+c*3.2, wy=(tall?1.3:1.2)+rw*3.1, lit=hash(idx*13+c*7+rw*3)>.5;
    B.box(faceX+(dirx<0?-.06:-.01),faceX+(dirx<0?.01:.06),wy,wy+1.5,ws,ws+1.5,lit?'#6f8fa8':'#4b6477',lit?1:0);
    B.box(faceX+(dirx<0?-.09:.04),faceX+(dirx<0?-.05:.09),wy-.12,wy-.02,ws-.1,ws+1.6,'#cfc7b5');
  }
  if(!tall){ B.box(faceX+(dirx<0?-.1:0),faceX+(dirx<0?0:.1),0,2.1,s0+(s1-s0)/2-.5,s0+(s1-s0)/2+.5,'#5d4037'); }
}

function genChunk(ci){
  const s0=ci*CH,s1=s0+CH, B=new MB(1<<15), Bd=new MB(1<<12);
  B.reset(0,0,s0); Bd.reset(0,0,s0);
  /* ---- الأرض ---- */
  const bands=[-420,-140,-70,-40,-24,-14,-6.5,6.5,13,26,40,70,140,420];
  for(let b=0;b<bands.length-1;b++){
    const xa=bands[b],xb=bands[b+1],mid=Math.abs((xa+xb)/2),step=mid<14?10:50;
    for(let a=s0;a<s1;a+=step){
      const cell=Math.floor(a/step), seed=b*37.1+cell*1.3;
      let cropT=-1; if(mid>13&&mid<70&&hash(seed*2.1)>.62) cropT=Math.floor(hash(seed*3.7)*4);
      if(cropT>=0){
        const rw=2.4, n=Math.max(1,Math.round((xb-xa)/rw)), w2=(xb-xa)/n;
        for(let k=0;k<n;k++) B.quad([xa+k*w2,0,a],[xa+(k+1)*w2,0,a],[xa+(k+1)*w2,0,a+step],[xa+k*w2,0,a+step],C(CROP[cropT][k%2]));
      } else {
        const base=(mid<14)?DRY[Math.floor(hash(seed)*4)]:GRASS[Math.floor(hash(seed)*6)];
        B.quad([xa,0,a],[xb,0,a],[xb,0,a+step],[xa,0,a+step],jit(base,.06,seed+.5));
      }
    }
  }
  /* ---- السكة ---- */
  for(let a=s0;a<s1;a+=10){
    const c=jit('#7d7a73',.07,a*.13);
    B.quad([-2.3,.28,a],[2.3,.28,a],[2.3,.28,a+10],[-2.3,.28,a+10],c);
    B.quad([2.3,.28,a],[3.7,0,a],[3.7,0,a+10],[2.3,.28,a+10],mulC(c,.9));
    B.quad([-2.3,.28,a],[-3.7,0,a],[-3.7,0,a+10],[-2.3,.28,a+10],mulC(c,.9));
  }
  const sp=.65;
  for(let k=Math.ceil(s0/sp);k*sp<s1;k++){ const s=k*sp; if(isXing(s)) continue; B.box(-1.4,1.4,.28,.38,s-.13,s+.13,k%9===0?'#4f4e4a':(k%2?'#6b6862':'#77736b')); }
  [-.72,.72].forEach(xr=>{ B.box(xr-.05,xr+.05,.38,.5,s0,s1,'#555a5f'); B.box(xr-.036,xr+.036,.5,.57,s0,s1,'#b4babf'); });
  /* ---- تقاطعات ---- */
  g.xings.forEach(xm=>{
    if(xm+8<s0||xm-8>s1) return;
    const a=xm-4.2,b=xm+4.2, rc=C('#4a4d52');
    B.box(-2.6,2.6,0,.385,a,b,'#55585d');
    Bd.quad([-150,.05,a],[-3.7,.05,a],[-3.7,.05,b],[-150,.05,b],rc); Bd.quad([3.7,.05,a],[150,.05,a],[150,.05,b],[3.7,.05,b],rc);
    Bd.quad([2.6,.386,a],[3.7,.05,a],[3.7,.05,b],[2.6,.386,b],mulC(rc,1.05)); Bd.quad([-2.6,.386,a],[-3.7,.05,a],[-3.7,.05,b],[-2.6,.386,b],mulC(rc,1.05));
    for(let xx=-70;xx<70;xx+=5){ if(Math.abs(xx)<4) continue; Bd.quad([xx,.06,xm-.08],[xx+2.4,.06,xm-.08],[xx+2.4,.06,xm+.08],[xx,.06,xm+.08],C('#d6d6d0')); }
    // خطوط المشاة
    [a+.6,b-1.2].forEach(sz=>{ for(let xx=-9;xx<=9;xx+=1.2){ if(Math.abs(xx)<3.9) continue; Bd.quad([xx,.07,sz],[xx+.6,.07,sz],[xx+.6,.07,sz+.6],[xx,.07,sz+.6],C('#e8e8e2')); } });
  });
  /* ---- الشارع الموازي ---- */
  for(let a=s0;a<s1;a+=10){ Bd.quad([ROAD_X0,.05,a],[ROAD_X1,.05,a],[ROAD_X1,.05,a+10],[ROAD_X0,.05,a+10],jit('#4b4e53',.07,a*.21)); }
  B.box(ROAD_X0-2.2,ROAD_X0,0,.16,s0,s1,'#a6a39b'); B.box(ROAD_X1,ROAD_X1+2.2,0,.16,s0,s1,'#a6a39b');
  B.box(ROAD_X0-.18,ROAD_X0,0,.17,s0,s1,'#8f8c85'); B.box(ROAD_X1,ROAD_X1+.18,0,.17,s0,s1,'#8f8c85');
  Bd.quad([ROAD_X0+.35,.07,s0],[ROAD_X0+.5,.07,s0],[ROAD_X0+.5,.07,s1],[ROAD_X0+.35,.07,s1],C('#d8d8d2'));
  Bd.quad([ROAD_X1-.5,.07,s0],[ROAD_X1-.35,.07,s0],[ROAD_X1-.35,.07,s1],[ROAD_X1-.5,.07,s1],C('#d8d8d2'));
  for(let a=Math.ceil(s0/9)*9;a<s1;a+=9) Bd.quad([19.32,.07,a],[19.48,.07,a],[19.48,.07,a+3.6],[19.32,.07,a+3.6],C('#e6e2d4'));
  /* ---- أعمدة كهرباء وأسلاك ---- */
  const inSt=m=>g.route.some(st=>Math.abs(st.x-m)<115);
  for(let a=Math.ceil(s0/40)*40;a<s1;a+=40){ if(inSt(a)) continue;
    B.box(-4.75,-4.55,0,7.4,a-.1,a+.1,'#6b5a46'); B.box(-5.9,-3.4,6.9,7.05,a-.07,a+.07,'#5a4a3a');
    [-5.6,-4.65,-3.7].forEach(xw=>{ B.box(xw-.04,xw+.04,7.05,7.25,a-.04,a+.04,'#d8d8d8');
      B.beam([xw,7.25,a],[xw,6.95,a+20],.035,'#222'); B.beam([xw,6.95,a+20],[xw,7.25,a+40],.035,'#222'); });
  }
  /* ---- أسوار ---- */
  [-9.8,13.3].forEach(xf=>{
    for(let a=Math.ceil(s0/5)*5;a<s1;a+=5){ if(inSt(a)) continue; B.box(xf-.05,xf+.05,0,1.25,a-.05,a+.05,'#6b5a46'); [.45,.85,1.2].forEach(hh=>B.beam([xf,hh,a],[xf,hh,a+5],.03,'#8a8a88')); }
  });
  /* ---- إنارة الشارع ---- */
  for(let a=Math.ceil(s0/30)*30;a<s1;a+=30){
    B.box(14.35,14.6,0,8,a-.12,a+.12,'#585c61'); B.beam([14.5,8,a],[16.6,8.35,a],.14,'#585c61'); B.box(16.2,17.4,8.2,8.4,a-.2,a+.2,'#d8d8d0',0); B.box(16.3,17.3,8.12,8.22,a-.15,a+.15,'#fff0c0',1);
    const rg=B.ring(16.9,.07,a,3.4,10); const pc=C('#4b4e53'); for(let i=0;i<10;i++) Bd.tri([16.9,.07,a],rg[i],rg[(i+1)%10],pc,1);
  }
  /* ---- أشجار وشجيرات ---- */
  for(let m=Math.ceil(s0/15)*15;m<s1;m+=15){
    const i=Math.round(m/15);
    [[-1,i*2+1],[1,i*2+2]].forEach(([side,sd])=>{
      const h=hash(sd*1.7),sj=m+(hash(sd*6.1)-.5)*10;
      if(inSt(sj)&&(side>0&&(hash(sd*2.9)<.6||h>=.5)||(h>=.5&&h<.72))) return;
      if(h<.5){
        let X;
        if(side>0) X=hash(sd*2.9)<.6?7+hash(sd*3.3)*5:26+hash(sd*3.7)*34; else X=-(7+hash(sd*3.3)*52);
        const ty=Math.floor(hash(sd*5.1)*4);
        if(ty===0) palm(B,X,sj,sd); else if(ty===1) leafy(B,X,sj,sd); else if(ty===2) cypress(B,X,sj,sd); else leafy(B,X,sj,sd+.5);
      } else if(h<.72) bush(B,side*(4.6+hash(sd*4.4)*6),sj,sd);
    });
  }
  /* ---- حشائش ---- */
  for(let k=0;k<120;k++){
    const r=n=>hash(s0*.37+k*5.9+n), x=(r(1)>.5?1:-1)*(3.9+r(2)*8), s=s0+r(3)*CH;
    if(x>12.4||x>ROAD_X0-2.5&&x<ROAD_X1+2.5||inSt(s)) continue;
    const gc=C(r(4)>.5?'#5d8a3a':'#739b43');
    for(let b=0;b<3;b++){ const an=b*2.1+r(5), dx=Math.cos(an)*.04,ds=Math.sin(an)*.04, h2=.28+r(6+b)*.35, ln=(r(9)-.5)*.2;
      B.tri([x-dx,.0,s-ds],[x+dx,.0,s+ds],[x+ln,h2,s+ln*.5],mulC(gc,.9+b*.07)); }
  }
  /* ---- بيوت ومباني ---- */
  for(let m=Math.ceil(s0/30)*30;m<s1;m+=30){
    const idx=m/30,h=hash(idx*7.7); if(h<=.55) continue;
    const side=hash(idx*1.3)>.5?1:-1, near=g.route.some(st=>Math.abs(st.x-m)<430);
    if(near){
      const wid=10+hash(idx*5.3)*8,hh=9+hash(idx*6.4)*24,dep=10+hash(idx*4.2)*8, xo=(side>0?28:26)+hash(idx*3.1)*16;
      const x0=side>0?xo:-xo-wid, x1=x0+wid;
      house(B,Bd,{x0,x1,s0:m-dep/2,s1:m+dep/2,h:hh,col:['#cfd6dc','#bfc8cf','#d8cfc2','#aab4bc'][Math.floor(hash(idx*7.5)*4)],roof:'#666',tall:true,idx});
    } else {
      const wid=8+hash(idx*4.4)*5, dep=9+hash(idx*3.3)*5, hh=3.4+hash(idx*5.5)*2.6, xo=(side>0?28:25)+hash(idx*2.2)*14;
      const x0=side>0?xo:-xo-wid, x1=x0+wid;
      house(B,Bd,{x0,x1,s0:m-dep/2,s1:m+dep/2,h:hh,col:HOUSE_COLS[Math.floor(hash(idx*6.6)*6)],roof:ROOF_COLS[Math.floor(hash(idx*8.8)*4)],tall:false,idx});
      const wx=side>0?x0-2:x1+2; B.box(Math.min(wx,wx+(side>0?9:-9)),Math.max(wx,wx+(side>0?9:-9)),0,2,m-dep/2-3,m-dep/2-2.8,'#d8cdb8');
    }
  }
  /* ---- المحطات ---- */
  g.route.forEach(st=>stationGeo(B,Bd,st,s0,s1));
  return {main:makeVBO(B),dec:makeVBO(Bd)};
}

function stationGeo(B,Bd,st,s0,s1){
  const a=Math.max(s0,st.x-100),b=Math.min(s1,st.x+100); if(b<=a) return;
  // أرصفة
  [[1.95,7.4],[-7.4,-1.95]].forEach(([xa,xb])=>{
    B.box(xa,xb,0,1.0,a,b,'#aeb1b5');
    for(let s=Math.ceil(a/4)*4;s<b;s+=4) Bd.quad([xa,1.002,s],[xb,1.002,s],[xb,1.002,s+.07],[xa,1.002,s+.07],C('#8e9298'));
  });
  Bd.quad([1.95,1.005,a],[2.35,1.005,a],[2.35,1.005,b],[1.95,1.005,b],C('#e0b92c'));
  Bd.quad([-2.35,1.005,a],[-1.95,1.005,a],[-1.95,1.005,b],[-2.35,1.005,b],C('#e0b92c'));
  // مظلة
  const ca=Math.max(a,st.x-62),cb=Math.min(b,st.x+62);
  if(cb>ca){
    B.box(2.2,7.1,4.5,4.75,ca,cb,'#d9dcdf'); B.box(2.2,7.1,4.75,4.85,ca,cb,'#8a8f94');
    for(let s=Math.ceil(ca/12)*12;s<cb;s+=12){ B.box(6.5,6.78,1,4.5,s-.14,s+.14,'#6c7076'); B.box(3.4,4.2,4.35,4.5,s-.3,s+.3,'#fff6dc',1); }
  }
  // مقاعد وأعمدة إنارة
  for(let s=Math.ceil(a/16)*16+4;s<b;s+=16){ B.box(5.2,5.7,1.0,1.45,s-.8,s+.8,'#5b6168'); B.box(5.2,5.28,1.45,1.9,s-.8,s+.8,'#5b6168'); }
  for(let s=Math.ceil(a/20)*20;s<b;s+=20){ B.box(3.5,3.62,1,5,s-.06,s+.06,'#555'); B.box(3.3,3.8,5,5.1,s-.14,s+.14,'#fff6dc',1); }
  // المبنى
  const ba=Math.max(s0,st.x-38),bb=Math.min(s1,st.x+38);
  if(bb>ba){
    B.box(8.6,14,0,5.6,ba,bb,'#e3d4b0'); B.box(8.3,14.3,5.6,6.1,ba,bb,'#8e5b3a'); B.box(8.6,14,0,.5,ba,bb,'#bfb08e');
    for(let s=Math.ceil(ba/6)*6;s<bb;s+=6){ const lit=hash(s*.31+st.x)>.35; B.box(8.55,8.62,1.6,4.4,s,s+3.6,lit?'#6f8fa8':'#4b6477',lit?1:0); B.box(8.5,8.58,1.5,1.62,s-.1,s+3.7,'#d8cfb8'); }
    B.box(8.5,8.7,0,2.7,st.x-1.2,st.x+1.2,'#5d4037');
  }
}

/* =====================================================================
   الكابينة (مجسم ثابت حول السائق، الأمام = -z في GL، هنا نستخدم s للأمام)
   ===================================================================== */
let cabMesh=null;
function buildCab(){
  const B=new MB(8192); B.reset(0,0,0);
  const wall='#2b3036',trim='#4a525b',floor='#2f343a',dark='#171b1f';
  const X=1.45,S0=-1.25,S1=1.55,Y0=-1.55,Y1=0.95;
  B.box(-X,X,Y0-.05,Y0,S0,S1,floor); B.box(-X,X,Y1,Y1+.05,S0,S1,'#464d55');
  B.box(-X,X,Y0,Y1,S0-.05,S0,wall);
  [-1,1].forEach(sd=>{
    const xa=sd>0?X-.06:-X, xb=sd>0?X:-X+.06;
    B.box(xa,xb,Y0,-.5,S0,S1,wall); B.box(xa,xb,.62,Y1,S0,S1,wall);
    B.box(xa,xb,-.5,.62,S0,-.65,wall); B.box(xa,xb,-.5,.62,1.2,S1,wall);
    const t1=sd>0?X-.1:-X, t2=sd>0?X:-X+.1;
    B.box(t1,t2,-.53,-.47,-.67,1.22,trim); B.box(t1,t2,.6,.66,-.67,1.22,trim); B.box(t1,t2,-.5,.62,-.7,-.64,trim); B.box(t1,t2,-.5,.62,1.19,1.25,trim);
  });
  B.box(X-.13,X-.06,-1.4,.5,-1.15,-.7,'#343b42'); B.box(X-.17,X-.12,-.7,-.62,-1.0,-.82,'#aab4be'); B.box(X-.15,X-.1,-1.0,-.55,-.78,-.74,dark);
  // الواجهة الأمامية: فتحة زجاج كبيرة وأعمدة نحيفة
  B.box(-X,X,Y0,-.3,S1-.05,S1,wall); B.box(-X,X,.8,Y1,S1-.05,S1,wall);
  B.box(-X,-1.34,-.3,.8,S1-.05,S1,wall); B.box(1.34,X,-.3,.8,S1-.05,S1,wall);
  B.box(-1.38,-1.3,-.3,.8,S1-.1,S1,trim); B.box(1.3,1.38,-.3,.8,S1-.1,S1,trim);
  B.box(-1.34,1.34,.76,.82,S1-.1,S1,trim); B.box(-1.34,1.34,-.33,-.28,S1-.08,S1,trim);
  B.box(-X,X,.8,.95,1.0,S1,'#3b424a');
  const prof=[[-1.55,.78],[-.82,.927],[-.42,1.313],[-.33,1.55],[-1.55,1.55]];
  for(let i=0;i<prof.length;i++){ const p=prof[i],q=prof[(i+1)%prof.length];
    B.quad([-X,p[0],p[1]],[X,p[0],p[1]],[X,q[0],q[1]],[-X,q[0],q[1]],mulC(dark,i===1?1.4:(i===2?1.2:1))); }
  [-X,X].forEach(xs=>{ for(let i=1;i<prof.length-1;i++) B.tri([xs,prof[0][0],prof[0][1]],[xs,prof[i][0],prof[i][1]],[xs,prof[i+1][0],prof[i+1][1]],dark); });
  // دعسات على الجانبين
  [-.85,.85].forEach((xc,i)=>{ B.box(xc-.14,xc+.14,-1.5,-1.38,.25,.5,'#3a4048'); B.box(xc-.12,xc+.12,-1.38,-1.35,.27,.48,i?'#8a2a22':'#555d66'); });
  // طفاية صغيرة وصندوق إسعاف
  B.box(-X+.06,-X+.2,-1.45,-1.0,-.9,-.7,'#b3261e'); B.box(-X+.06,-X+.16,-1.0,-.94,-.84,-.76,'#222');
  B.box(X-.2,X-.06,-.2,.15,-1.2,-.7,'#f2f2f2'); B.box(X-.22,X-.18,-.1,.05,-1.0,-.9,'#d32f2f'); B.box(X-.22,X-.18,-.04,.0,-1.05,-.85,'#d32f2f');
  B.box(-.3,.3,.88,.95,.1,.5,'#d8d8d0',1);
  cabMesh=makeVBO(B);
}

/* لوحات الكابينة (نسيج + موقع ثلاثي الأبعاد) */
const PAN={
  dash:{cv:mkCanvas(1024,336),c:[0,-.62,-1.12],r:[1,0,0],u:[0,.72,-.69],w:1.7,h:.557,hot:[]},
  low :{cv:mkCanvas(768,330),c:[0,-1.2,-.83],r:[1,0,0],u:[0,.95,-.31],w:1.5,h:.64,hot:[]},
  door:{cv:mkCanvas(512,300),c:[1.405,-.95,-.18],r:[0,0,1],u:[0,1,0],w:1.0,h:.585,hot:[]},
  map :{cv:mkCanvas(512,330),c:[-1.405,-.95,-.18],r:[0,0,-1],u:[0,1,0],w:1.0,h:.645,hot:[]}
};
Object.values(PAN).forEach(p=>{ p.tex=canvasTex(p.cv); p.n=V3.norm(V3.cross(p.r,p.u)); p.ctx=p.cv.getContext('2d'); });
let px=null; // سياق الرسم الحالي للوحة

/* ---------- أدوات الرسم على اللوحات ---------- */
function rr(x,y,w,h,r){ px.beginPath(); px.moveTo(x+r,y); px.arcTo(x+w,y,x+w,y+h,r); px.arcTo(x+w,y+h,x,y+h,r); px.arcTo(x,y+h,x,y,r); px.arcTo(x,y,x+w,y,r); px.closePath(); }
function dial(x,y,r,val,max,step,label){
  const bg=px.createRadialGradient(x-r*.35,y-r*.35,r*.1,x,y,r*1.15); bg.addColorStop(0,'#aab4be'); bg.addColorStop(1,'#39414a');
  px.fillStyle=bg; px.beginPath(); px.arc(x,y,r*1.1,0,7); px.fill();
  px.fillStyle='#0b0e11'; px.beginPath(); px.arc(x,y,r*.95,0,7); px.fill();
  const sw=Math.PI*1.5,a0=Math.PI*0.75,minor=step/2; px.textAlign='center';
  for(let v=0;v<=max+0.001;v+=minor){
    const a=a0+(v/max)*sw,major=Math.abs(v/step-Math.round(v/step))<0.01,r1=r*(major?.7:.8),r2=r*.9;
    px.strokeStyle=v>max*0.9?'#ff5252':'#dfe6ea'; px.lineWidth=major?2.5:1.3;
    px.beginPath(); px.moveTo(x+Math.cos(a)*r1,y+Math.sin(a)*r1); px.lineTo(x+Math.cos(a)*r2,y+Math.sin(a)*r2); px.stroke();
    if(major){ px.fillStyle='#fff'; px.font='bold '+Math.max(10,Math.round(r*.17))+'px Tahoma'; px.fillText(Math.round(v),x+Math.cos(a)*r*.53,y+Math.sin(a)*r*.53+r*.06); }
  }
  px.fillStyle='#9fb0bd'; px.font=Math.max(10,Math.round(r*.15))+'px Tahoma'; px.fillText(label,x,y+r*.45);
  const a=a0+clamp01(val/max)*sw;
  px.strokeStyle='#ff5252'; px.lineWidth=Math.max(2.5,r*.05); px.lineCap='round';
  px.beginPath(); px.moveTo(x-Math.cos(a)*r*.12,y-Math.sin(a)*r*.12); px.lineTo(x+Math.cos(a)*r*.82,y+Math.sin(a)*r*.82); px.stroke(); px.lineCap='butt';
  px.fillStyle='#222'; px.beginPath(); px.arc(x,y,r*.09,0,7); px.fill();
  px.fillStyle='rgba(255,255,255,.06)'; px.beginPath(); px.arc(x-r*.15,y-r*.3,r*.6,Math.PI,Math.PI*2); px.fill();
}
function lamp(x,y,r,on,col,label){
  px.fillStyle='#0b0e11'; px.beginPath(); px.arc(x,y,r*1.3,0,7); px.fill();
  if(on){ const gl2=px.createRadialGradient(x,y,0,x,y,r*2.6); gl2.addColorStop(0,col); gl2.addColorStop(1,'rgba(0,0,0,0)'); px.globalAlpha=.5; px.fillStyle=gl2; px.beginPath(); px.arc(x,y,r*2.6,0,7); px.fill(); px.globalAlpha=1; }
  px.fillStyle=on?col:'#2a3138'; px.beginPath(); px.arc(x,y,r,0,7); px.fill();
  if(label){ px.fillStyle='#aab6c0'; px.font='13px Tahoma'; px.textAlign='center'; px.fillText(label,x,y+r*2.6); }
}
function pbtn(P,x,y,r,id,label,col,lit,inside){
  const pr=g.press===id; P.hot.push({id,t:'c',x,y,r:r*1.2});
  px.fillStyle='#0b0e11'; px.beginPath(); px.arc(x,y,r*1.22,0,7); px.fill();
  if(lit){ const gl2=px.createRadialGradient(x,y,r*.5,x,y,r*2); gl2.addColorStop(0,col); gl2.addColorStop(1,'rgba(0,0,0,0)'); px.globalAlpha=.45; px.fillStyle=gl2; px.beginPath(); px.arc(x,y,r*2,0,7); px.fill(); px.globalAlpha=1; }
  const on=lit||pr,gr=px.createRadialGradient(x-r*.3,y-r*.3,r*.1,x,y,r);
  gr.addColorStop(0,on?'#ffffff':shade(col,45)); gr.addColorStop(1,on?col:shade(col,-35));
  px.fillStyle=gr; px.beginPath(); px.arc(x,y+(pr?2:0),r*(pr?.94:1),0,7); px.fill();
  const fs=Math.max(12,Math.round(r*.6)); px.textAlign='center';
  if(inside){ px.fillStyle='#fff'; px.font='bold '+fs+'px Tahoma'; px.fillText(label,x,y+fs*.35); }
  else { px.fillStyle='#c5d0d8'; px.font='14px Tahoma'; px.fillText(label,x,y+r*1.2+16); }
}
function lever(P,x,y0,y1,val,id,label,col){
  P.hot.push({id,t:'l',x:x-34,y:y0-22,w:68,h:(y1-y0)+44,y0,y1});
  px.fillStyle='#07090b'; rr(x-6,y0,12,y1-y0,6); px.fill();
  px.strokeStyle='#6c7883'; px.lineWidth=1.5;
  for(let i=0;i<=4;i++){ const yy=y1-(y1-y0)*i/4; px.beginPath(); px.moveTo(x-26,yy); px.lineTo(x-12,yy); px.stroke(); px.beginPath(); px.moveTo(x+12,yy); px.lineTo(x+26,yy); px.stroke(); }
  const ky=y1-(y1-y0)*val,hw=44,hh=30,g1=px.createLinearGradient(x-hw/2,0,x+hw/2,0);
  g1.addColorStop(0,shade(col,-45)); g1.addColorStop(.5,shade(col,25)); g1.addColorStop(1,shade(col,-45));
  px.fillStyle='#14181c'; px.fillRect(x-4,ky-2,8,18);
  px.fillStyle=g1; rr(x-hw/2,ky-hh/2,hw,hh,8); px.fill();
  px.strokeStyle='rgba(0,0,0,.5)'; px.lineWidth=2.5;
  for(let i=-1;i<=1;i++){ px.beginPath(); px.moveTo(x-hw/2+8,ky+i*7); px.lineTo(x+hw/2-8,ky+i*7); px.stroke(); }
  px.fillStyle='#c5d0d8'; px.font='15px Tahoma'; px.textAlign='center'; px.fillText(label,x,y1+30);
}
function panelBase(P,c1,c2){
  const w=P.cv.width,h=P.cv.height,gr=px.createLinearGradient(0,0,0,h); gr.addColorStop(0,c1); gr.addColorStop(1,c2);
  px.fillStyle=gr; px.fillRect(0,0,w,h);
  px.strokeStyle='rgba(255,255,255,.08)'; px.lineWidth=3; px.strokeRect(2,2,w-4,h-4);
  px.fillStyle='rgba(255,255,255,.035)'; px.fillRect(0,0,w,h*.18);
}

function drawDash(){
  const P=PAN.dash; px=P.ctx; P.hot=[]; const t=T(),st=g.route[g.next],bt=Math.max(keys.space?1:0,g.brk);
  px.clearRect(0,0,1024,336); panelBase(P,'#2c343b','#1a1f24');
  const sm=Math.ceil(t.max/20)*20,stp=[10,20,25,40,50].find(s=>sm/s<=9)||50;
  dial(110,205,66,g.brkShown*10,10,2,'ضغط الفرامل');
  dial(290,172,116,g.v*3.6,sm,stp,'كم/س');
  dial(478,205,66,g.ampShown*1000,1000,200,'التيار');
  // الشاشة الرقمية
  const sx=560,sy=26,sw=236,sh=150;
  px.fillStyle='#0b0e11'; rr(sx-8,sy-8,sw+16,sh+16,12); px.fill(); px.fillStyle='#06240f'; rr(sx,sy,sw,sh,8); px.fill();
  px.fillStyle='#5dff8a'; px.textAlign='center'; px.font='bold 62px monospace'; px.fillText(Math.round(g.v*3.6),sx+66,sy+78);
  px.font='17px Tahoma'; px.fillText('كم/س',sx+66,sy+108);
  px.fillStyle='rgba(93,255,138,.3)'; px.fillRect(sx+128,sy+16,2,sh-32);
  px.fillStyle='#5dff8a'; px.font='16px Tahoma';
  if(st){ const dist=Math.max(0,Math.round(st.x-g.x)); px.fillText('التالي',sx+182,sy+34); px.font='bold 22px Tahoma'; px.fillText(st.name,sx+182,sy+66); px.font='19px Tahoma'; px.fillText(dist>=1000?(dist/1000).toFixed(1)+' كم':dist+' م',sx+182,sy+98); }
  px.font='17px monospace'; px.fillText((LV>.5?'☀ ':'☾ ')+Math.floor(g.time/60)+':'+String(Math.floor(g.time%60)).padStart(2,'0'),sx+182,sy+134);
  // مصابيح
  const mx=sx+sw/2,lsp=40,ly=240,lr=9;
  lamp(mx-lsp*2.5,ly,lr,g.state==='loading','#2ecc71','أبواب'); lamp(mx-lsp*1.5,ly,lr,bt>0.05,'#ff4d4d','فرامل'); lamp(mx-lsp*.5,ly,lr,g.hand,'#ff9f43','يد');
  lamp(mx+lsp*.5,ly,lr,g.hornT>0,'#ffd54a','زمارة'); lamp(mx+lsp*1.5,ly,lr,g.lights,'#fff3b0','أضواء'); lamp(mx+lsp*2.5,ly,lr,!!keys.x&&(Math.floor(g.time*4)%2===0),'#ff2d2d','طوارئ');
  // أذرع
  lever(P,838,50,262,g.th,'thr','الدفع','#34495e'); lever(P,916,50,262,1-g.brk,'brk','الفرامل','#b3261e');
  // أزرار
  pbtn(P,972,60,22,'horn','زمارة','#e1a600',g.hornT>0);
  const canDoor=inZone()&&g.v<0.5&&g.state==='running';
  pbtn(P,972,138,22,'door','أبواب','#27ae60',g.state==='loading'||(canDoor&&Math.floor(g.time*3)%2===0));
  pbtn(P,972,216,22,'lights','أضواء','#c9b458',g.lights);
  pbtn(P,972,294,18,'wipers','مساحات','#2e86de',g.wipers);
  pbtn(P,40,50,22,'emg','طوارئ','#d32f2f',!!keys.x,true);
  updTex(P.tex,P.cv);
}
function drawLow(){
  const P=PAN.low; px=P.ctx; P.hot=[]; px.clearRect(0,0,768,330); panelBase(P,'#262d33','#14181c');
  // فرامل اليد
  const hx=100,hy=250,len=140,ang=g.hand?-Math.PI*0.44:-Math.PI*0.08;
  px.fillStyle='#0b0e11'; rr(hx-52,hy-14,104,52,10); px.fill();
  px.strokeStyle='#8a949e'; px.lineWidth=14; px.lineCap='round'; px.beginPath(); px.moveTo(hx,hy); px.lineTo(hx+Math.cos(ang)*len,hy+Math.sin(ang)*len); px.stroke(); px.lineCap='butt';
  const kx=hx+Math.cos(ang)*len,ky=hy+Math.sin(ang)*len;
  if(g.hand){ const gl2=px.createRadialGradient(kx,ky,0,kx,ky,60); gl2.addColorStop(0,'rgba(255,60,60,.6)'); gl2.addColorStop(1,'rgba(255,60,60,0)'); px.fillStyle=gl2; px.fillRect(kx-60,ky-60,120,120); }
  px.fillStyle=g.hand?'#ff4d4d':'#c0392b'; px.beginPath(); px.arc(kx,ky,24,0,7); px.fill();
  P.hot.push({id:'hand',t:'c',x:hx+30,y:hy-70,r:105});
  px.fillStyle='#fff'; px.font='bold 20px Tahoma'; px.textAlign='center'; px.fillText('فرامل اليد',hx,hy+68);
  px.fillStyle=g.hand?'#ff8a8a':'#5dff8a'; px.font='17px Tahoma'; px.fillText(g.hand?'مفعّلة 🔒 (اضغط لتحريرها)':'محرّرة 🔓',hx,hy+92);
  // درج الأجرة
  const tx=250,ty=88,tw=250,th=170,coins=Math.max(0,Math.round(g.coins-g.penalties+(g.state==='loading'?g.popped:0)));
  px.fillStyle='#0b0e11'; rr(tx-8,ty-8,tw+16,th+16,14); px.fill(); px.fillStyle='#2b3239'; rr(tx,ty,tw,th,10); px.fill();
  const n=Math.min(60,Math.floor(coins/4)),cw=tw/5;
  for(let c=0;c<5;c++){
    px.fillStyle='#161b20'; rr(tx+c*cw+5,ty+8,cw-10,th-16,6); px.fill();
    const cnt=Math.floor(n/5)+(c<n%5?1:0);
    for(let i=0;i<Math.min(cnt,12);i++){ const cxx=tx+c*cw+cw/2,cyy=ty+th-16-i*(th*.055);
      px.fillStyle='#b8860b'; px.beginPath(); px.ellipse(cxx,cyy+3,cw*.3,cw*.12,0,0,7); px.fill(); px.fillStyle=i%2?'#f1c40f':'#ffd54a'; px.beginPath(); px.ellipse(cxx,cyy,cw*.3,cw*.12,0,0,7); px.fill(); }
  }
  px.fillStyle='#06240f'; rr(tx+tw*.15,ty-46,tw*.7,34,6); px.fill(); px.fillStyle='#5dff8a'; px.font='bold 24px monospace'; px.textAlign='center'; px.fillText('🪙 '+fmt(coins),tx+tw/2,ty-20);
  px.fillStyle='#c5d0d8'; px.font='15px Tahoma'; px.fillText('درج الأجرة',tx+tw/2,ty+th+30);
  // راديو
  const rx=556,ry=38,rw=180,rh=110;
  P.hot.push({id:'radio',t:'r',x:rx,y:ry,w:rw,h:rh});
  px.fillStyle='#0b0e11'; rr(rx-5,ry-5,rw+10,rh+10,10); px.fill(); px.fillStyle='#2b3239'; rr(rx,ry,rw,rh,8); px.fill();
  px.fillStyle=g.radio?'#06240f':'#0a0f0c'; rr(rx+14,ry+14,98,38,4); px.fill();
  px.fillStyle=g.radio?'#5dff8a':'#264a33'; px.font='bold 22px monospace'; px.textAlign='center'; px.fillText(g.radio?'FM 98.4':'---',rx+63,ry+42);
  px.fillStyle='#8a949e'; [0,1].forEach(i=>{ px.beginPath(); px.arc(rx+138+i*28-14,ry+34,13,0,7); px.fill(); });
  px.fillStyle=g.radio?'#2ecc71':'#555'; px.beginPath(); px.arc(rx+rw-12,ry+12,5,0,7); px.fill();
  px.strokeStyle='#161b20'; px.lineWidth=2; for(let i=0;i<5;i++){ px.beginPath(); px.moveTo(rx+14,ry+66+i*8); px.lineTo(rx+rw-14,ry+66+i*8); px.stroke(); }
  px.fillStyle='#c5d0d8'; px.font='15px Tahoma'; px.fillText('الراديو (اضغط)',rx+rw/2,ry+rh+28);
  // سجل الرحلة
  const lx=556,ly2=190,lw=180,lh=125;
  px.fillStyle='#e9e2cf'; rr(lx,ly2,lw,lh,6); px.fill(); px.strokeStyle='#cfc6ae'; px.lineWidth=1; for(let i=1;i<7;i++){ px.beginPath(); px.moveTo(lx+8,ly2+i*lh/7.5+10); px.lineTo(lx+lw-8,ly2+i*lh/7.5+10); px.stroke(); }
  px.fillStyle='#2a2a2a'; px.font='bold 15px Tahoma'; px.textAlign='center'; px.fillText('سجل الرحلة',lx+lw/2,ly2+22);
  px.font='12.5px Tahoma'; px.textAlign='right'; const rt=g.route;
  px.fillText('من: '+rt[0].name+'  إلى: '+rt[rt.length-1].name,lx+lw-10,ly2+46); px.fillText('القطار: '+T().name,lx+lw-10,ly2+66);
  px.fillText((g.job==='passengers'?'الركاب':'البضائع')+': '+g.load,lx+lw-10,ly2+86); px.fillText('المحطة '+Math.min(g.next,rt.length-1)+' من '+(rt.length-1),lx+lw-10,ly2+106);
  updTex(P.tex,P.cv);
}
function drawDoor(){
  const P=PAN.door; px=P.ctx; P.hot=[]; px.clearRect(0,0,512,300); panelBase(P,'#2a3137','#171b1f');
  const st=g.route[g.next],canDoor=inZone()&&g.v<0.5&&g.state==='running',blink=Math.floor(g.time*3)%2===0;
  px.fillStyle='#9fb0bd'; px.font='bold 22px Tahoma'; px.textAlign='center'; px.fillText('🚪 لوحة الأبواب',256,34);
  pbtn(P,140,150,44,'door','فتح','#27ae60',g.state==='loading'||(canDoor&&blink));
  pbtn(P,260,150,44,'bell','جرس','#e1a600',g.bellT>0);
  const n=T().cars+1; for(let i=0;i<n;i++) lamp(300+(i%4)*0+ (i*(190/Math.max(1,n-1))),80,8,true,g.state==='loading'?'#2ecc71':'#d33',''+(i+1));
  px.fillStyle=g.state==='loading'?'#5dff8a':'#ff8a8a'; px.font='bold 20px Tahoma'; px.fillText(g.state==='loading'?'الأبواب مفتوحة':'الأبواب مغلقة',395,140);
  px.fillStyle='#c5d0d8'; px.font='17px Tahoma';
  px.fillText(st?(inZone()?(g.v<0.5?'داخل الرصيف — تقدر تفتح الأبواب':'داخل الرصيف — أوقف القطار'):'المحطة: '+st.name+' — '+Math.max(0,Math.round(st.x-g.x))+' م'):'',256,250);
  updTex(P.tex,P.cv);
}
function drawMap(){
  const P=PAN.map; px=P.ctx; P.hot=[]; px.clearRect(0,0,512,330); panelBase(P,'#0d3347','#082230');
  px.textAlign='center'; px.fillStyle='#7ee0ff'; px.font='bold 24px Tahoma'; px.fillText('🗺 مسار الرحلة',256,38);
  const n=g.route.length,y0=82,dy=(330-130)/Math.max(1,n-1);
  g.route.forEach((r,i)=>{ const y=y0+i*dy,done=i<g.next,cur=i===g.next;
    px.fillStyle=done?'#5dff8a':cur?'#ffd54a':'#6a8a9a'; px.beginPath(); px.arc(70,y,9,0,7); px.fill();
    if(i<n-1){ px.strokeStyle=done?'#5dff8a':'#3a5a6a'; px.lineWidth=3; px.beginPath(); px.moveTo(70,y+9); px.lineTo(70,y+dy-9); px.stroke(); }
    px.fillStyle=done?'#9fe8b8':cur?'#fff':'#8aa6b4'; px.font=(cur?'bold ':'')+'20px Tahoma'; px.textAlign='left'; px.fillText(r.name+(cur?'  ◀':''),96,y+7);
    if(cur){ px.textAlign='right'; px.fillStyle='#ffd54a'; px.fillText(Math.max(0,Math.round(r.x-g.x))+' م',486,y+7); } });
  const tot=g.route[n-1].x,pr=clamp01(g.x/tot); px.fillStyle='#123b4f'; px.fillRect(30,306,452,10); px.fillStyle='#5dff8a'; px.fillRect(30,306,452*pr,10);
  updTex(P.tex,P.cv);
}

/* ---------- الالتقاط بالماوس على اللوحات ---------- */
let cam=null;
function rayFromMouse(mx,my){
  const x=(mx/W)*2-1,y=1-(my/H)*2,t=Math.tan(cam.fov/2),asp=W/H;
  return V3.norm(V3.add(V3.add(cam.f,V3.mul(cam.r,x*asp*t)),V3.mul(cam.u,y*t)));
}
function hitPanel(P,d,clampB){
  const dn=V3.dot(d,P.n); if(dn>-1e-4) return null;
  const o=[cabLean,0,0], t=V3.dot(V3.sub(P.c,o),P.n)/dn; if(t<=0) return null;
  const p=V3.add(o,V3.mul(d,t)),l=V3.sub(p,P.c), a=V3.dot(l,P.r)/(P.w/2), b=V3.dot(l,P.u)/(P.h/2);
  if(!clampB&&(Math.abs(a)>1||Math.abs(b)>1)) return null;
  return {t,cx:(a*.5+.5)*P.cv.width,cy:(.5-b*.5)*P.cv.height};
}
function pick(mx,my){
  if(!cam||viewMode!=='cab') return null;
  const d=rayFromMouse(mx,my); let best=null;
  for(const k in PAN){ const P=PAN[k],h=hitPanel(P,d,false); if(h&&(!best||h.t<best.t)){ best={P,k,t:h.t,cx:h.cx,cy:h.cy}; } }
  if(!best) return null;
  const {P,cx,cy}=best;
  for(let i=P.hot.length-1;i>=0;i--){ const o=P.hot[i];
    if(o.t==='c'&&Math.hypot(cx-o.x,cy-o.y)<=o.r) return {...best,hot:o};
    if((o.t==='r'||o.t==='l')&&cx>=o.x&&cx<=o.x+o.w&&cy>=o.y&&cy<=o.y+o.h) return {...best,hot:o}; }
  return best;
}
const drags=new Map();
function leverTo(P,hot,mx,my){ const h=hitPanel(P,rayFromMouse(mx,my),true); if(!h) return; const v=clamp01((h.cy-hot.y0)/(hot.y1-hot.y0)); if(hot.id==='thr') g.th=Math.round((1-v)*20)/20; else g.brk=Math.round(v*20)/20; }
cvs.addEventListener('pointerdown',e=>{
  if(g.state==='lobby'||g.state==='done') return; audio();
  const mx=e.offsetX,my=e.offsetY,id0=e.pointerId;
  if(viewMode==='cab'){
    const hit=pick(mx,my);
    if(hit&&hit.hot){
      e.preventDefault(); const id=hit.hot.id; g.press=id;
      if(id==='thr'||id==='brk'){ drags.set(id0,{kind:'lever',P:hit.P,hot:hit.hot}); leverTo(hit.P,hit.hot,mx,my); try{cvs.setPointerCapture(id0);}catch(_){} return; }
      if(id==='emg'){ keys.x=true; drags.set(id0,{kind:'btn',id}); try{cvs.setPointerCapture(id0);}catch(_){} return; }
      doAction(id); return;
    }
    drags.set(id0,{kind:'look',x:e.clientX,y:e.clientY,yaw:yawT,pitch:pitchT}); cvs.classList.add('drag'); try{cvs.setPointerCapture(id0);}catch(_){}
  } else { drags.set(id0,{kind:'orbit',x:e.clientX,y:e.clientY,yaw:oyaw,pitch:opitch}); cvs.classList.add('drag'); try{cvs.setPointerCapture(id0);}catch(_){} }
});
cvs.addEventListener('pointermove',e=>{
  const d=drags.get(e.pointerId); if(!d) return;
  if(d.kind==='lever') leverTo(d.P,d.hot,e.offsetX,e.offsetY);
  else if(d.kind==='look'){ yawT=clamp(d.yaw+(e.clientX-d.x)*0.0045,-2.3,2.3); pitchT=clamp(d.pitch-(e.clientY-d.y)*0.0045,-1.3,0.6); }
  else if(d.kind==='orbit'){ oyaw=d.yaw-(e.clientX-d.x)*0.006; opitch=clamp(d.pitch+(e.clientY-d.y)*0.005,0.03,1.3); }
});
function endPtr(e){ const d=drags.get(e.pointerId); if(d&&d.kind==='btn'&&d.id==='emg') keys.x=false; drags.delete(e.pointerId); if(!drags.size){ cvs.classList.remove('drag'); } g.press=null; }
addEventListener('pointerup',endPtr); addEventListener('pointercancel',endPtr);
function doAction(id){
  if(id==='horn'){ horn(); g.horned=true; g.hornT=.5; }
  else if(id==='door') tryDoors();
  else if(id==='bell'){ bell(); g.bellT=.5; }
  else if(id==='lights'){ g.lights=!g.lights; beep(600,.05,'square',.06); }
  else if(id==='wipers'){ g.wipers=!g.wipers; beep(500,.05,'square',.06); }
  else if(id==='hand') toggleHand();
  else if(id==='radio'){ g.radio=!g.radio; g.radioT=0; beep(700,.05,'square',.05); }
  else if(id==='lookC'){ yawT=0; pitchT=PITCH0; }
  else if(id==='lookL'){ viewMode='cab'; yawT=-1.45; pitchT=-0.12; }
  else if(id==='lookR'){ viewMode='cab'; yawT=1.45; pitchT=-0.12; }
  else if(id==='lookD'){ viewMode='cab'; yawT=0; pitchT=-0.95; }
}
/* ---- لوحة اللمس (ايباد) ---- */
const IS_TOUCH=(window.matchMedia&&matchMedia('(pointer:coarse)').matches)||navigator.maxTouchPoints>1;
let padOn=IS_TOUCH;
function setupSlider(id,set,get){
  const el=$(id),knob=el.querySelector('.knob'),fill=el.querySelector('.fill');
  const apply=e=>{ const r=el.getBoundingClientRect(); set(Math.round(clamp01(1-(e.clientY-r.top)/r.height)*20)/20); };
  el.addEventListener('pointerdown',e=>{ e.preventDefault(); audio(); try{el.setPointerCapture(e.pointerId);}catch(_){} el._d=e.pointerId; apply(e); });
  el.addEventListener('pointermove',e=>{ if(el._d===e.pointerId) apply(e); });
  const up=e=>{ if(el._d===e.pointerId) el._d=null; }; el.addEventListener('pointerup',up); el.addEventListener('pointercancel',up);
  el._sync=()=>{ const v=get(),h=el.clientHeight-38; knob.style.bottom=(v*h)+'px'; fill.style.height=(v*100)+'%'; };
}
setupSlider('slThr',v=>{ g.th=v; },()=>g.th||0);
setupSlider('slBrk',v=>{ g.brk=v; },()=>g.brk||0);
document.querySelectorAll('#pad .pb').forEach(b=>{
  const a=b.dataset.a;
  b.addEventListener('pointerdown',e=>{ e.preventDefault(); audio(); try{b.setPointerCapture(e.pointerId);}catch(_){} if(a==='emg'){ keys.x=true; b.classList.add('on'); } else doAction(a); });
  const up=()=>{ if(a==='emg'){ keys.x=false; b.classList.remove('on'); } };
  b.addEventListener('pointerup',up); b.addEventListener('pointercancel',up);
});
function syncPad(){
  const show=padOn&&g.state!=='lobby'&&g.state!=='done';
  $('pad').classList.toggle('hidden',!show);
  if(show){ $('slThr')._sync(); $('slBrk')._sync();
    document.querySelector('#pad [data-a=hand]').classList.toggle('on',!!g.hand); document.querySelector('#pad [data-a=lights]').classList.toggle('on',!!g.lights);
    document.querySelector('#pad [data-a=wipers]').classList.toggle('on',!!g.wipers); document.querySelector('#pad [data-a=radio]').classList.toggle('on',!!g.radio); }
}
$('padToggle').onclick=()=>{ padOn=!padOn; };
document.addEventListener('touchmove',e=>{ if(g.state!=='lobby') e.preventDefault(); },{passive:false});
document.addEventListener('gesturestart',e=>e.preventDefault());
cvs.addEventListener('wheel',e=>{ if(viewMode==='out'){ e.preventDefault(); odist=clamp(odist*(e.deltaY>0?1.08:.92),14,160); } },{passive:false});

/* =====================================================================
   الإضاءة والكاميرا
   ===================================================================== */
const LT={};
function computeLight(){
  const c=worldT%CYC; let sunEl;
  if(c<600) sunEl=14+56*Math.sin(Math.PI*c/600); else if(c<630) sunEl=lerp(14,-9,(c-600)/30); else if(c<690) sunEl=-9; else sunEl=lerp(-9,14,(c-690)/30);
  const e=sunEl*Math.PI/180,az=.45;
  LT.sunDir=[Math.sin(az)*Math.cos(e),Math.sin(e),-Math.cos(az)*Math.cos(e)];
  const me=(28+22*Math.sin(Math.PI*clamp01((c-600)/120)))*Math.PI/180,maz=-.5;
  LT.moonDir=[Math.sin(maz)*Math.cos(me),Math.sin(me),-Math.cos(maz)*Math.cos(me)];
  LT.sunVis=sunEl>-4?1:0;
  const dayCol=mixC([1.0,.96,.86],[1.0,.6,.33],DK*.95);
  const lightDir=V3.norm(V3.add(V3.mul(LT.sunDir,LV+.001),V3.mul(LT.moonDir,NV*.9)));
  LT.dir=lightDir;
  LT.col=[dayCol[0]*LV*.95+.10*NV,dayCol[1]*LV*.95+.13*NV,dayCol[2]*LV*.95+.22*NV];
  const aS=mixC(mixC([.55,.62,.74],[.07,.09,.17],NV),[.55,.42,.46],DK*.5), aG=[aS[0]*.62,aS[1]*.58,aS[2]*.5];
  LT.ambS=aS; LT.ambG=aG;
  LT.top=mixC(mixC('#3d8fd1','#050c24',NV),'#5a4a8a',DK*.3); LT.bot=mixC(mixC('#cfe9f7','#16224a',NV),'#ff9a55',DK*.75);
  LT.fog=LT.bot; LT.fogD=1/(650-120*NV);
  LT.cloud=mixC(mixC([1,1,1],[1.0,.62,.45],DK),[.16,.18,.28],NV);
}
let EX=0,EY=0,ES=0,cabLean=0;
function makeCamera(){
  const asp=W/H,fov=viewMode==='cab'?1.32:1.0; let f,eye;
  if(viewMode==='cab'){
    const sway=g.v>1?Math.sin(g.time*23)*Math.min(.0028,g.v*.00004):0, roll=g.v>1?Math.sin(g.time*1.7)*Math.min(.003,g.v*.00005):0;
    const yw=yaw+roll,pt=pitch+sway;
    f=[Math.sin(yw)*Math.cos(pt),Math.sin(pt),-Math.cos(yw)*Math.cos(pt)]; cabLean=clamp((Math.abs(yaw)-.45)/.75,0,1)*Math.sign(yaw)*.98; eye=[cabLean,3.2,g.x];
  } else {
    const ty=2.2,ts=g.x-14,cp=Math.cos(opitch),ox=odist*cp*Math.sin(oyaw),oy=odist*Math.sin(opitch),oz=odist*cp*Math.cos(oyaw);
    eye=[ox,Math.max(.8,ty+oy),ts-oz]; f=V3.norm([-ox,ty-eye[1],-(ts)-(-eye[2])]);
  }
  const r=V3.norm(V3.cross(f,[0,1,0])),u=V3.cross(r,f);
  const Vm=new Float32Array([r[0],u[0],-f[0],0, r[1],u[1],-f[1],0, r[2],u[2],-f[2],0, 0,0,0,1]);
  const vp=mat4mul(persp(fov,asp,.25,4200),Vm);
  EX=eye[0]; EY=eye[1]; ES=eye[2];
  return {f,r,u,vp,fov,asp,eye};
}

/* =====================================================================
   الرسم الديناميكي (سيارات، ركاب، بوابات، قطار خارجي، مساحات)
   ===================================================================== */
const D=new MB(1<<14), DC=new MB(1<<11);
const glows=[];
function carList(){
  const out=[];
  for(let i=0;i<14;i++){
    const h1=hash(i*9.1+1),h2=hash(i*4.7+2),h3=hash(i*2.3+3),h4=hash(i*6.1+4);
    const dir=h1>.5?1:-1,spd=(9+h2*16)*dir,raw=i*101+h3*500+spd*worldT, rel=((raw-g.x+300)%1500+1500)%1500-300, truck=(i%5===0);
    out.push({s:g.x+rel,x:dir>0?21.3:17.5,dir,truck,len:truck?9:4+h4*1.2,col:truck?'#dfe3e6':CAR_COLS[Math.floor(h4*9)],i});
  }
  return out;
}
function dCar(c){
  const night=NV>.15, hl=c.dir>0?c.s+c.len/2:c.s-c.len/2, tl=c.dir>0?c.s-c.len/2:c.s+c.len/2;
  if(c.truck){
    D.box(c.x-1.0,c.x+1.0,.5,3.0,c.s-c.len/2,c.s-c.len/2+c.len*.72,c.col); D.box(c.x-1.0,c.x+1.0,.5,2.4,c.dir>0?c.s+c.len/2-2.2:c.s-c.len/2,c.dir>0?c.s+c.len/2:c.s-c.len/2+2.2,'#3b78ad');
    D.box(c.x-.95,c.x+.95,.25,.55,c.s-c.len/2,c.s+c.len/2,'#2a2e33');
  } else {
    D.box(c.x-.9,c.x+.9,.32,1.02,c.s-c.len/2,c.s+c.len/2,c.col); D.box(c.x-.8,c.x+.8,1.02,1.55,c.s-c.len*.28,c.s+c.len*.2,'#202b38');
    D.box(c.x-.86,c.x+.86,.2,.34,c.s-c.len/2,c.s+c.len/2,'#1d2024');
  }
  [[-.9,-.32],[.9,-.32],[-.9,.32],[.9,.32]].forEach(([dx,ds])=>{ const ws=ds<0?c.s-c.len*.32:c.s+c.len*.32; D.box(c.x+dx-.1,c.x+dx+.1,0,.62,ws-.34,ws+.34,'#16181b'); });
  [-.62,.62].forEach(dx=>{ D.box(c.x+dx-.16,c.x+dx+.16,.55,.8,hl-.06,hl+.02,'#fff6d8',3); D.box(c.x+dx-.16,c.x+dx+.16,.6,.8,tl-.02,tl+.04,'#c0201a',2); });
  if(night){ const dd=c.dir; glows.push({x:c.x-.62,y:.7,s:hl+dd*.3,sz:1.3,c:[1,.95,.8],a:.85},{x:c.x+.62,y:.7,s:hl+dd*.3,sz:1.3,c:[1,.95,.8],a:.85},{x:c.x-.6,y:.7,s:tl-dd*.3,sz:.9,c:[1,.1,.05],a:.8},{x:c.x+.6,y:.7,s:tl-dd*.3,sz:.9,c:[1,.1,.05],a:.8}); }
}
const SHIRT=['#c0392b','#2980b9','#27ae60','#f39c12','#8e44ad','#16a085','#ecf0f1','#34495e'];
function dPerson(o){
  const {x,y,s,yaw:Y,type,seed,mv,ph}=o, cY=Math.cos(Y),sY=Math.sin(Y);
  const Pw=(lx,ly,ls)=>[x+lx*cY+ls*sY,y+ly,s-lx*sY+ls*cY];
  const sw=mv?Math.sin(ph)*.5:0, bob=mv?Math.abs(Math.sin(ph))*.03:0;
  const skin=['#e0b48c','#c99a6e','#d9a87c','#b98a5e'][Math.floor(hash(seed*1.3)*4)];
  const part=(lx,ly,ls,hx,hy,hs,c,pi=0,e=0)=>{ const p=Pw(lx,ly+bob,ls); D.boxT(p[0],p[1],p[2],hx,hy,hs,Y,pi,c,e); };
  if(type==='thobe'){
    const col=['#f4f1ea','#e9e4d6','#d9d6cc','#f0ede4'][Math.floor(hash(seed*2.1)*4)];
    part(0,.62,0,.2,.62,.12,col); part(0,1.35,0,.21,.22,.13,col);
    part(-.27,1.2,sw*.3,.05,.28,.06,col,sw*.4); part(.27,1.2,-sw*.3,.05,.28,.06,col,-sw*.4);
    if(mv){ part(-.1,.1,sw*.35,.06,.1,.1,'#3a3a3a'); part(.1,.1,-sw*.35,.06,.1,.1,'#3a3a3a'); }
    part(0,1.68,0,.115,.12,.11,skin); const red=hash(seed*3.3)>.5;
    part(0,1.8,-.01,.135,.06,.13,red?'#d4d4d4':'#f6f6f6'); if(red) part(0,1.76,-.01,.14,.015,.14,'#b3261e');
  } else if(type==='abaya'){
    part(0,.6,0,.2,.6,.13,'#16181b'); part(0,1.32,0,.21,.22,.13,'#16181b'); part(0,1.62,0,.13,.17,.12,'#16181b'); part(0,1.58,.1,.07,.07,.02,skin);
  } else {
    const shirt=SHIRT[Math.floor(hash(seed*4.4)*8)], pants=['#2c3e50','#34495e','#3b3b3b'][Math.floor(hash(seed*5.5)*3)];
    part(-.09,.42,sw*.4,.07,.42,.08,pants,sw*.5); part(.09,.42,-sw*.4,.07,.42,.08,pants,-sw*.5);
    part(0,1.12,0,.19,.3,.11,shirt); part(-.27,1.12,-sw*.35,.05,.28,.06,shirt,-sw*.45); part(.27,1.12,sw*.35,.05,.28,.06,shirt,sw*.45);
    part(0,1.63,0,.11,.13,.11,skin); part(0,1.74,-.01,.115,.05,.11,['#2a1d12','#4a3322','#1a1a1a'][Math.floor(hash(seed*6.6)*3)]);
  }
  if(g.job==='cargo'&&mv){ const p=Pw(0,1.0,.3); D.boxT(p[0],p[1],p[2],.22,.18,.18,Y,0,'#a1783f'); }
}
function dTrain(){
  const t=T(), col=t.color, open=g.state==='loading';
  const sA=g.x-16;
  // القاطرة
  D.box(-1.45,1.45,1.0,3.7,sA,g.x,col); D.box(-1.4,1.4,3.7,3.85,sA,g.x,mulC(col,1.15)); D.box(-1.46,1.46,1.0,1.5,sA,g.x,'#2a2d31');
  D.box(-1.2,1.2,1.9,3.2,g.x-.05,g.x+.02,'#1c2d3d',1); D.box(-1.0,1.0,3.85,4.0,sA+3,g.x-3,'#555a60');
  [-1.0,1.0].forEach(dx=>{ D.box(dx-.2,dx+.2,1.3,1.6,g.x,g.x+.08,'#fff6d8',3); });
  D.box(-1.45,1.45,1.0,3.7,g.x-.01,g.x,'#d9dce0');
  for(let k=0;k<2;k++){ const c0=sA+3+k*10; D.box(-1.2,1.2,.35,1.0,c0-1.4,c0+1.4,'#262a2e'); [-.75,.75].forEach(dx=>D.box(dx-.1,dx+.1,0,.7,c0-1.2,c0+1.2,'#15181b')); }
  D.box(-1.0,1.0,3.9,4.5,sA+4,sA+5.5,'#50565c'); D.beam([-1.0,4.5,sA+4],[0,5.7,sA+4.8],.07,'#33383d'); D.beam([1.0,4.5,sA+4],[0,5.7,sA+4.8],.07,'#33383d'); D.beam([-.8,5.7,sA+4.8],[.8,5.7,sA+4.8],.08,'#2a2e32');
  [-1.46,1.46].forEach(sd=>{ for(let k=0;k<3;k++){ const w0=sA+1.5+k*4.6; D.box(sd-.02,sd+.02,1.9,3.0,w0,w0+2.4,'#1c2d3d',1); } });
  // العربات
  for(let i=0;i<t.cars;i++){
    const b1=g.x-16-1-i*19,b0=b1-18, cc=g.job==='cargo'?'#8d6e63':col;
    D.box(-1.45,1.45,1.0,3.6,b0,b1,cc); D.box(-1.4,1.4,3.6,3.75,b0,b1,mulC(cc,1.15)); D.box(-1.46,1.46,1.0,1.5,b0,b1,'#2a2d31');
    for(let k=0;k<2;k++){ const c0=b0+3+k*12; D.box(-1.2,1.2,.35,1.0,c0-1.4,c0+1.4,'#262a2e'); [-.75,.75].forEach(dx=>D.box(dx-.1,dx+.1,0,.7,c0-1.2,c0+1.2,'#15181b')); }
    [-1.46,1.46].forEach(sd=>{
      if(g.job==='passengers'){ for(let k=0;k<6;k++){ const w0=b0+.7+k*2.9; const isDoor=(k===1||k===4); D.box(sd-.02,sd+.02,isDoor?1.1:1.9,3.1,w0,w0+(isDoor?1.7:2.0),isDoor?(open&&sd>0?'#2ecc71':'#cdd3d8'):'#1c2d3d',isDoor?0:1); }
      } else { for(let k=1;k<5;k++) D.box(sd-.03,sd+.03,1.0,3.6,b0+k*3.6,b0+k*3.6+.12,'#5d4037'); }
    });
    D.box(-.5,.5,1.2,1.8,b1,b1+1,'#1f2326');
  }
}
function xingState(xm){
  const d=xm-g.x, closing=(d<170&&d>-30);
  const st=g.gates[xm]||(g.gates[xm]={a:0}); st.t=closing?1:0; return st;
}
function dCrossings(){
  g.xings.forEach(xm=>{
    const d=xm-g.x; if(d>700||d<-200) return;
    const st=xingState(xm); st.a+=(st.t-st.a)*Math.min(1,.04); const act=st.t>.5, blink=Math.floor(worldT*2)%2;
    [-1,1].forEach(sd=>{
      const px2=sd*4.6, ps=xm-3.4*sd*0+(-2.2);
      D.box(px2-.1,px2+.1,0,3.6,xm-2.4,xm-2.2,'#e8e8e8'); D.box(px2-.35,px2+.35,3.2,3.9,xm-2.45,xm-2.15,'#222');
      const on=act&&((sd>0)===(blink===1)); const onC=on?'#ff3028':'#4a1210';
      D.box(px2-.28,px2-.06,3.4,3.62,xm-2.5,xm-2.44,onC,2); D.box(px2+.06,px2+.28,3.4,3.62,xm-2.5,xm-2.44,(act&&!on)?'#ff3028':'#4a1210',2);
      if(act){ const gl1=(on?px2-.17:px2+.17); glows.push({x:gl1,y:3.5,s:xm-2.6,sz:1.1,c:[1,.15,.1],a:.9}); }
      // الذراع
      const ang=lerp(1.25,.03,st.a), L=6.2;
      D.beam([px2,1.1,xm-2.3],[px2+sd*Math.cos(ang)*L*-1*-1,1.1+Math.sin(ang)*L,xm-2.3],.12,'#f0f0f0');
      for(let k=1;k<5;k++){ const tt=k/5; D.box(px2+sd*Math.cos(ang)*L*tt-.07,px2+sd*Math.cos(ang)*L*tt+.07,1.1+Math.sin(ang)*L*tt-.07,1.1+Math.sin(ang)*L*tt+.07,xm-2.36,xm-2.24,k%2?'#d33':'#f5f5f5'); }
    });
    if(act&&d>-10&&worldT%1<dt0()) { beep(1500,.06,'square',.02); }
  });
}
function dt0(){ return .02; }
function dWipers(){
  const s=g.wipers?(Math.sin(g.wiperP)*.5+.5):0;
  [-.45,.45].forEach(px2=>{
    const th=lerp(2.9,.35,s)*(px2<0?1:-1)*0+lerp(Math.PI*.97,Math.PI*.08,s), L=.62, ex=px2+Math.cos(th)*L, ey=-.3+Math.sin(th)*L;
    DC.beam([px2,-.3,1.5],[ex,ey,1.5],.018,'#0a0a0a'); DC.beam([px2+Math.cos(th)*L*.3,-.3+Math.sin(th)*L*.3,1.5],[ex,ey,1.5],.03,'#0a0a0a');
  });
}
function buildDynamic(){
  D.reset(EX,EY,ES); DC.reset(0,0,0); glows.length=0;
  const lo=g.x-200,hi=g.x+900;
  carList().forEach(c=>{ if(c.s>lo&&c.s<hi) dCar(c); });
  g.route.forEach(st=>{
    if(st.x<lo-100||st.x>hi+100) return;
    st.people.forEach(p=>{
      const pp=personPos(p,personTime(st)); if(!pp.vis) return;
      if(pp.s<lo||pp.s>hi) return;
      const Y=pp.mv?Math.atan2(pp.dx||0,pp.ds||0.001):(pp.face>0?Math.PI/2:-Math.PI/2);
      dPerson({x:pp.lat,y:1.0,s:pp.s,yaw:Y,type:p.type,seed:p.seed,mv:pp.mv,ph:p.ph+worldT*7});
    });
  });
  dCrossings();
  if(viewMode==='out') dTrain();
  if(NV>.1){
    for(let a=Math.ceil(lo/30)*30;a<hi;a+=30) glows.push({x:16.9,y:8.1,s:a,sz:2.6,c:[1,.82,.5],a:.9});
    g.route.forEach(st=>{ for(let a=Math.ceil(Math.max(lo,st.x-100)/20)*20;a<Math.min(hi,st.x+100);a+=20) glows.push({x:3.56,y:5,s:a,sz:2.0,c:[1,.95,.8],a:.9}); });
  }
  if(viewMode==='cab') dWipers();
}

/* =====================================================================
   الرسم الرئيسي
   ===================================================================== */
function setCommonA(P,intr){
  const u=P.u;
  gl.uniform3fv(u.uSun,LT.dir); gl.uniform3fv(u.uSunCol,intr?[0,0,0]:LT.col);
  gl.uniform3fv(u.uAmbS,intr?[.62-.4*NV,.62-.4*NV,.66-.38*NV]:LT.ambS); gl.uniform3fv(u.uAmbG,intr?[.42-.28*NV,.42-.28*NV,.44-.26*NV]:LT.ambG);
  gl.uniform3fv(u.uFogCol,LT.fog); gl.uniform1f(u.uFogD,LT.fogD); gl.uniform1f(u.uNight,NV); gl.uniform1f(u.uInt,intr?1:0);
  gl.uniform1f(u.uHead,intr?0:(g.lights?1:0));
}
function ensureChunks(){
  const a=Math.floor((ES-150)/CH),b=Math.floor((ES+950)/CH); let made=0;
  for(let i=a;i<=b;i++){ if(i<-1) continue; if(!chunks.has(i)){ if(made>=2&&chunks.size>6) break; chunks.set(i,genChunk(i)); made++; } }
  chunks.forEach((c,i)=>{ if(i<a-2||i>b+2){ freeMesh(c.main); freeMesh(c.dec); chunks.delete(i); } });
}
const hillMesh=(()=>{
  const B=new MB(4096); B.reset(0,0,0);
  [[2000,0,'#8aa0b2',130,.9],[1500,1.3,'#7f9c8c',60,1.4]].forEach(([R,ph,col,amp,fr])=>{
    const N=96; let prev=null;
    for(let i=0;i<=N;i++){ const a=i/N*Math.PI*2, hgt=amp*(.5+.3*Math.sin(a*3+ph)+.2*Math.sin(a*7+ph*2)+.12*Math.sin(a*13+ph*3))*fr;
      const px2=Math.cos(a)*R, pz=Math.sin(a)*R; const cur=[[px2,-2,pz],[px2,hgt,pz]];
      if(prev) B.quad([prev[0][0],prev[0][1],-prev[0][2]],[cur[0][0],cur[0][1],-cur[0][2]],[cur[1][0],cur[1][1],-cur[1][2]],[prev[1][0],prev[1][1],-prev[1][2]],jit(col,.08,i*.3+ph));
      prev=cur; }
  });
  return makeVBO(B);
})();
const farGround=(()=>{ const B=new MB(64); B.reset(0,0,0); B.quad([-4000,0,-4000],[4000,0,-4000],[4000,0,4000],[-4000,0,4000],C('#82a052')); return makeVBO(B); })();

function drawSky(){
  gl.disable(gl.DEPTH_TEST); gl.useProgram(PC.p); enableAttr(1);
  gl.bindBuffer(gl.ARRAY_BUFFER,buf.sky); gl.vertexAttribPointer(0,2,gl.FLOAT,false,0,0);
  const u=PC.u;
  gl.uniform3fv(u.uR,cam.r); gl.uniform3fv(u.uU,cam.u); gl.uniform3fv(u.uF,cam.f); gl.uniform1f(u.uT,Math.tan(cam.fov/2)); gl.uniform1f(u.uA,cam.asp);
  gl.uniform3fv(u.uTop,LT.top); gl.uniform3fv(u.uBot,LT.bot); gl.uniform3fv(u.uSun,LT.sunDir); gl.uniform3fv(u.uMoon,LT.moonDir); gl.uniform3fv(u.uCloud,LT.cloud);
  gl.uniform1f(u.uNight,NV); gl.uniform1f(u.uDusk,DK); gl.uniform1f(u.uTime,worldT); gl.uniform1f(u.uSunVis,LT.sunVis*(1-NV*.6));
  gl.drawArrays(gl.TRIANGLES,0,6);
  gl.enable(gl.DEPTH_TEST);
}
function gp(x,y,s){ return [x-EX,y-EY,ES-s]; }
function texQuad(tex,c4,tint,fogOn){
  const d=new Float32Array([c4[0][0],c4[0][1],c4[0][2],0,0, c4[1][0],c4[1][1],c4[1][2],1,0, c4[2][0],c4[2][1],c4[2][2],1,1, c4[0][0],c4[0][1],c4[0][2],0,0, c4[2][0],c4[2][1],c4[2][2],1,1, c4[3][0],c4[3][1],c4[3][2],0,1]);
  gl.bindBuffer(gl.ARRAY_BUFFER,buf.dynTex); gl.bufferData(gl.ARRAY_BUFFER,d,gl.DYNAMIC_DRAW);
  gl.vertexAttribPointer(0,3,gl.FLOAT,false,20,0); gl.vertexAttribPointer(1,2,gl.FLOAT,false,20,12);
  gl.bindTexture(gl.TEXTURE_2D,tex); gl.uniform4fv(PB.u.uTint,tint); gl.drawArrays(gl.TRIANGLES,0,6);
}
function drawSigns(){
  gl.useProgram(PB.p); enableAttr(2);
  gl.uniformMatrix4fv(PB.u.uVP,false,cam.vp); gl.uniform3f(PB.u.uOff,0,0,0); gl.uniform3fv(PB.u.uFogCol,LT.fog); gl.uniform1f(PB.u.uFogD,LT.fogD); gl.uniform1f(PB.u.uInt,0); gl.uniform1i(PB.u.uTex,0);
  const dl=1-NV*.62, tint=[dl,dl,dl,1];
  g.route.forEach(st=>{
    const d=st.x-g.x; if(d<-120||d>1400) return;
    // لوحة معلقة فوق السكة قبل المحطة
    const sg=st.x-62;
    if(sg>g.x-10){
      [-4.3,4.3].forEach(xx=>{ D.box(xx-.12,xx+.12,0,7.3,sg-.12,sg+.12,'#555'); });
    }
    texQuad(signTex(st.name),[gp(-3.8,7.0,sg+.15),gp(3.8,7.0,sg+.15),gp(3.8,4.9,sg+.15),gp(-3.8,4.9,sg+.15)],tint);
    // لوحة على المبنى
    texQuad(signTex(st.name,'#124c3a'),[gp(8.45,8.0,st.x+8),gp(8.45,8.0,st.x-8),gp(8.45,6.1,st.x-8),gp(8.45,6.1,st.x+8)],tint);
  });
  const nx=g.route[g.next];
  if(nx) [1500,800,400].forEach(dd=>{ const s=nx.x-dd; if(s<g.x+3||s>g.x+1200) return;
    texQuad(signTex(dd+'م','#e67e22','#ffffff',256,128),[gp(3.0,4.4,s),gp(5.2,4.4,s),gp(5.2,2.8,s),gp(3.0,2.8,s)],tint);
    D.box(3.95,4.1,0,4.4,s-.06,s+.06,'#eee'); });
}
function drawGlows(){
  if(!glows.length) return;
  gl.useProgram(PB.p); enableAttr(2);
  gl.uniformMatrix4fv(PB.u.uVP,false,cam.vp); gl.uniform3f(PB.u.uOff,0,0,0); gl.uniform1f(PB.u.uInt,1); gl.uniform1i(PB.u.uTex,0);
  gl.enable(gl.BLEND); gl.blendFunc(gl.SRC_ALPHA,gl.ONE); gl.depthMask(false);
  const k=Math.min(1,NV*1.4);
  glows.forEach(gw=>{
    const c=gp(gw.x,gw.y,gw.s), dist=Math.hypot(c[0],c[1],c[2]); if(dist<2||dist>520) return;
    const fwd=V3.dot(c,cam.f); if(fwd<1) return;
    const sz=gw.sz*(1+dist*.012), rx=V3.mul(cam.r,sz), uy=V3.mul(cam.u,sz);
    const q=[V3.add(c,V3.add(V3.mul(rx,-1),uy)),V3.add(c,V3.add(rx,uy)),V3.add(c,V3.sub(rx,uy)),V3.sub(c,V3.add(rx,uy))];
    texQuad(glowTex,q,[gw.c[0],gw.c[1],gw.c[2],gw.a*k*Math.min(1,520/dist-.0)*(dist>350?(520-dist)/170:1)],false);
  });
  gl.disable(gl.BLEND); gl.depthMask(true);
}
function drawCabParts(){
  gl.useProgram(PA.p); enableAttr(4); gl.uniformMatrix4fv(PA.u.uVP,false,cam.vp); setCommonA(PA,true); gl.uniform3f(PA.u.uOff,-cabLean,0,0);
  bindMesh(cabMesh.vbo); gl.drawArrays(gl.TRIANGLES,0,cabMesh.n);
  if(DC.n>0){ gl.bindBuffer(gl.ARRAY_BUFFER,buf.dyn); gl.bufferData(gl.ARRAY_BUFFER,DC.a.subarray(0,DC.n*10),gl.DYNAMIC_DRAW); bindMesh(buf.dyn); gl.drawArrays(gl.TRIANGLES,0,DC.n); }
  // لوحات
  drawDash(); drawLow(); drawDoor(); drawMap();
  gl.useProgram(PB.p); enableAttr(2); gl.uniformMatrix4fv(PB.u.uVP,false,cam.vp); gl.uniform3f(PB.u.uOff,0,0,0); gl.uniform1f(PB.u.uInt,1); gl.uniform1i(PB.u.uTex,0);
  const dl=1-NV*.35, tint=[dl,dl,dl,1];
  for(const k in PAN){ const P=PAN[k], c=V3.sub(V3.add(P.c,V3.mul(P.n,.004)),[cabLean,0,0]), hw=V3.mul(P.r,P.w/2), hh=V3.mul(P.u,P.h/2);
    texQuad(P.tex,[V3.add(V3.sub(c,hw),hh),V3.add(V3.add(c,hw),hh),V3.sub(V3.add(c,hw),hh),V3.sub(V3.sub(c,hw),hh)],tint,false); }
}
function resizeGL(){
  const dpr=Math.min(window.devicePixelRatio||1,2); const w=Math.floor(innerWidth*dpr),h=Math.floor(innerHeight*dpr);
  if(cvs.width!==w||cvs.height!==h){ cvs.width=w; cvs.height=h; }
  DPR=dpr; W=cvs.clientWidth||innerWidth; H=cvs.clientHeight||innerHeight;
}
function draw(){
  if(g.state==='lobby') return;
  resizeGL(); computeLight(); if(!cabMesh) buildCab();
  cam=makeCamera();
  gl.viewport(0,0,cvs.width,cvs.height);
  gl.clearColor(LT.bot[0],LT.bot[1],LT.bot[2],1); gl.clear(gl.COLOR_BUFFER_BIT|gl.DEPTH_BUFFER_BIT);
  gl.disable(gl.CULL_FACE); gl.enable(gl.DEPTH_TEST); gl.depthFunc(gl.LEQUAL);
  drawSky();
  ensureChunks(); buildDynamic();
  gl.useProgram(PA.p); enableAttr(4); gl.uniformMatrix4fv(PA.u.uVP,false,cam.vp); setCommonA(PA,false);
  // الأرض البعيدة والتلال (تتبع الكاميرا)
  gl.uniform3f(PA.u.uOff,0,-EY-.35,0); bindMesh(farGround.vbo); gl.drawArrays(gl.TRIANGLES,0,farGround.n);
  gl.uniform1f(PA.u.uFogD,LT.fogD*.34); gl.uniform3f(PA.u.uOff,0,-EY,0); bindMesh(hillMesh.vbo); gl.drawArrays(gl.TRIANGLES,0,hillMesh.n);
  gl.uniform1f(PA.u.uFogD,LT.fogD);
  // القطع
  chunks.forEach((c,i)=>{ const s0=i*CH; gl.uniform3f(PA.u.uOff,-EX,-EY,ES-s0); bindMesh(c.main.vbo); gl.drawArrays(gl.TRIANGLES,0,c.main.n); });
  gl.enable(gl.POLYGON_OFFSET_FILL); gl.polygonOffset(-2,-2);
  chunks.forEach((c,i)=>{ if(!c.dec.n) return; const s0=i*CH; gl.uniform3f(PA.u.uOff,-EX,-EY,ES-s0); bindMesh(c.dec.vbo); gl.drawArrays(gl.TRIANGLES,0,c.dec.n); });
  gl.disable(gl.POLYGON_OFFSET_FILL);
  // ديناميكي
  drawSigns(); // قد يضيف أعمدة إلى D
  gl.useProgram(PA.p); enableAttr(4); gl.uniform3f(PA.u.uOff,0,0,0);
  gl.bindBuffer(gl.ARRAY_BUFFER,buf.dyn); gl.bufferData(gl.ARRAY_BUFFER,D.a.subarray(0,D.n*10),gl.DYNAMIC_DRAW); bindMesh(buf.dyn); gl.drawArrays(gl.TRIANGLES,0,D.n);
  drawGlows();
  if(viewMode==='cab') drawCabParts();
}

/* =====================================================================
   الحلقة
   ===================================================================== */
let last=performance.now();
function loop(now){
  const dt=Math.min(0.05,(now-last)/1000); last=now;
  update(dt);
  try{ draw(); }catch(err){ console.error(err); }
  requestAnimationFrame(loop);
}
renderLobby();
requestAnimationFrame(loop);
</script>
</body>
</html>
