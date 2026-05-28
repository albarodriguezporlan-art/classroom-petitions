[classroom_messenger_publish.html](https://github.com/user-attachments/files/28342595/classroom_messenger_publish.html)
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Classroom Messenger</title>
<style>
*{box-sizing:border-box;margin:0;padding:0;font-family:'Segoe UI',Arial,sans-serif}
:root{--r:#ec4e63;--t:#6ebcbc;--o:#d9783b;--p:#db87a6;--g:#a0bb7f;--d:#272525}
body{background:#f0ede8;display:flex;align-items:center;justify-content:center;min-height:100vh;padding:12px}
.wrap{width:100%;max-width:960px}
.app{display:flex;height:640px;border-radius:18px;overflow:hidden;box-shadow:0 6px 36px rgba(0,0,0,.13);border:1px solid rgba(0,0,0,.08)}
.sidebar{width:220px;flex-shrink:0;background:var(--d);color:#fff;display:flex;flex-direction:column}
.sh{padding:16px 14px 12px;border-bottom:1px solid rgba(255,255,255,.1)}
.sh-title{font-size:13px;font-weight:700;color:rgba(255,255,255,.9);letter-spacing:.2px}
.sh-sub{font-size:10px;color:rgba(255,255,255,.35);letter-spacing:.5px;text-transform:uppercase;margin-top:3px}
.alist{flex:1;overflow-y:auto;padding:5px 0}
.alist::-webkit-scrollbar{width:3px}.alist::-webkit-scrollbar-thumb{background:rgba(255,255,255,.15);border-radius:3px}
.ai{padding:8px 13px;cursor:pointer;display:flex;align-items:center;gap:9px;transition:background .15s;border-left:3px solid transparent}
.ai:hover{background:rgba(255,255,255,.07)}
.ai.active{background:rgba(255,255,255,.11);border-left-color:var(--t)}
.ab{width:32px;height:32px;border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:800;flex-shrink:0}
.ainf{flex:1;min-width:0}
.al{font-size:12px;font-weight:700}
.at{font-size:10px;color:rgba(255,255,255,.4);white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.uc{background:var(--r);color:#fff;border-radius:10px;font-size:10px;font-weight:800;padding:1px 6px;flex-shrink:0}
.main{flex:1;display:flex;flex-direction:column;background:#f7f5f2;min-width:0}
.vt{display:flex;background:#fff;border-bottom:1px solid rgba(0,0,0,.07);flex-shrink:0}
.vtb{flex:1;padding:11px 6px;font-size:12px;font-weight:700;border:none;cursor:pointer;background:transparent;color:#aaa;border-bottom:3px solid transparent;transition:all .15s}
.vtb:hover{color:#666}.vtb.active{color:var(--r);border-bottom-color:var(--r);background:#fff8f9}
#tv{display:flex;flex-direction:column;flex:1;overflow:hidden}
.mh{background:#fff;padding:12px 16px;border-bottom:1px solid rgba(0,0,0,.07);display:flex;align-items:center;gap:11px;flex-shrink:0}
.mb{width:42px;height:42px;border-radius:11px;display:flex;align-items:center;justify-content:center;font-size:14px;font-weight:800;flex-shrink:0}
.nw{flex:1;min-width:0}
.nr{display:flex;align-items:center;gap:6px}
.nd{font-size:15px;font-weight:700;color:var(--d);cursor:pointer;border-bottom:1.5px dashed #ddd;padding-bottom:1px}
.nd:hover{border-bottom-color:var(--t)}
.ni{font-size:15px;font-weight:700;color:var(--d);border:none;border-bottom:2px solid var(--t);outline:none;background:transparent;font-family:inherit;width:160px;padding-bottom:1px;display:none}
.neb{font-size:13px;cursor:pointer;color:#ccc;background:none;border:none;padding:0;transition:color .15s}
.neb:hover{color:var(--t)}
.nh{font-size:11px;color:#bbb;margin-top:2px}
.msgs{flex:1;overflow-y:auto;padding:13px 16px;display:flex;flex-direction:column;gap:8px}
.msgs::-webkit-scrollbar{width:4px}.msgs::-webkit-scrollbar-thumb{background:#ddd;border-radius:4px}
.mr{display:flex;flex-direction:column;align-items:flex-start}
.mbub{max-width:80%;padding:9px 13px;border-radius:15px 15px 15px 4px;font-size:13px;line-height:1.5;background:#fff;border:1px solid rgba(0,0,0,.07);color:var(--d)}
.mm{font-size:10px;color:#bbb;margin-top:3px;margin-left:2px}
.cp{display:inline-block;border-radius:20px;font-size:10px;font-weight:700;padding:2px 8px;margin-bottom:5px;letter-spacing:.3px}
.ca{background:#fff;border-top:1px solid rgba(0,0,0,.07);padding:12px 16px;flex-shrink:0}
.cc{display:flex;gap:6px;margin-bottom:9px;flex-wrap:wrap}
.cb{border:1.5px solid;border-radius:20px;padding:4px 12px;font-size:11px;font-weight:700;cursor:pointer;background:transparent;transition:all .15s}
.cb:hover{opacity:.8}.cb.selected{color:#fff!important}
.cm2{border-color:var(--o);color:var(--o)}.cm2.selected{background:var(--o)}
.cu{border-color:var(--r);color:var(--r)}.cu.selected{background:var(--r)}
.ci{border-color:var(--t);color:var(--t)}.ci.selected{background:var(--t)}
.cay{border-color:var(--g);color:var(--g)}.cay.selected{background:var(--g)}
.crow{display:flex;gap:7px;align-items:flex-end}
.cin{flex:1;border:1.5px solid #e0dcd8;border-radius:11px;padding:9px 13px;font-size:13px;resize:none;outline:none;font-family:inherit;line-height:1.4;background:#faf9f7;color:var(--d);transition:border-color .15s;min-height:40px;max-height:85px}
.cin:focus{border-color:var(--t);background:#fff}.cin::placeholder{color:#bbb}
.sb{width:40px;height:40px;border-radius:11px;border:none;cursor:pointer;background:var(--r);color:#fff;font-size:17px;transition:background .15s;flex-shrink:0;display:flex;align-items:center;justify-content:center}
.sb:hover{background:#d43e54}
#dv{display:none;flex-direction:column;flex:1;overflow:hidden}
.dtb{background:#fff;padding:10px 14px;border-bottom:1px solid rgba(0,0,0,.07);display:flex;align-items:center;justify-content:space-between;gap:8px;flex-wrap:wrap;flex-shrink:0}
.dt{font-size:13px;font-weight:700;color:var(--d);white-space:nowrap}
.fps{display:flex;gap:4px;flex-wrap:wrap}
.fp{font-size:11px;font-weight:600;padding:3px 10px;border-radius:20px;border:1px solid #e0dcd8;cursor:pointer;background:#fff;color:#888;transition:all .15s}
.fp:hover{border-color:#bbb;color:#555}.fp.active{background:var(--d);color:#fff;border-color:var(--d)}
.board{flex:1;overflow-y:auto;padding:10px 12px;display:flex;flex-direction:column;gap:7px}
.board::-webkit-scrollbar{width:4px}.board::-webkit-scrollbar-thumb{background:#ddd;border-radius:4px}
.bm{background:#fff;border-radius:13px;padding:11px 13px;border:1px solid rgba(0,0,0,.07);display:flex;gap:11px;align-items:flex-start;transition:box-shadow .15s}
.bm:hover{box-shadow:0 2px 10px rgba(0,0,0,.07)}.bm.done{opacity:.55}
.bab{width:34px;height:34px;border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:800;flex-shrink:0}
.bb{flex:1;min-width:0}
.bh{display:flex;align-items:center;gap:6px;margin-bottom:4px;flex-wrap:wrap}
.ban{font-size:13px;font-weight:800;color:var(--d)}
.bwho{font-size:11px;color:#aaa}
.bt{font-size:13px;color:#444;line-height:1.5;word-break:break-word}
.btime{font-size:10px;color:#bbb;margin-top:3px}
.bact{display:flex;gap:6px;margin-top:8px;flex-wrap:wrap}
.abtn{font-size:11px;font-weight:700;padding:4px 11px;border-radius:7px;border:1.5px solid;cursor:pointer;background:transparent;transition:all .15s}
.abtn:hover{opacity:.75}
.aok{border-color:var(--g);color:var(--g)}.aok:hover{background:var(--g);color:#fff}
.arep{border-color:var(--t);color:var(--t)}.arep:hover{background:var(--t);color:#fff}
.dtag{font-size:11px;font-weight:700;color:var(--g)}
.es{flex:1;display:flex;flex-direction:column;align-items:center;justify-content:center;color:#ccc;font-size:13px;text-align:center;padding:24px;gap:10px}
.ei{font-size:36px}
.mo{display:none;position:fixed;inset:0;background:rgba(0,0,0,.4);z-index:1000;align-items:center;justify-content:center}
.mo.open{display:flex}
.md{background:#fff;border-radius:16px;padding:22px 24px;width:380px;max-width:90vw;box-shadow:0 8px 36px rgba(0,0,0,.18)}
.md h3{font-size:15px;font-weight:700;color:var(--d);margin-bottom:4px}
.md p{font-size:12px;color:#999;margin-bottom:12px}
.md textarea{width:100%;border:1.5px solid #e0dcd8;border-radius:9px;padding:9px 12px;font-size:13px;font-family:inherit;resize:none;outline:none;line-height:1.5;height:76px;color:var(--d);background:#faf9f7}
.md textarea:focus{border-color:var(--t);background:#fff}
.mda{display:flex;gap:7px;margin-top:11px;justify-content:flex-end}
.mcan{padding:7px 16px;border-radius:9px;border:1.5px solid #e0dcd8;background:transparent;color:#888;font-size:13px;font-weight:600;cursor:pointer}
.msnd{padding:7px 18px;border-radius:9px;border:none;background:var(--t);color:#fff;font-size:13px;font-weight:700;cursor:pointer}
.msnd:hover{background:#5aa8a8}
.toast{position:fixed;bottom:24px;left:50%;transform:translateX(-50%) translateY(70px);background:var(--d);color:#fff;border-radius:11px;padding:10px 20px;font-size:13px;font-weight:600;box-shadow:0 4px 18px rgba(0,0,0,.2);transition:transform .3s ease;pointer-events:none;white-space:nowrap;z-index:9999}
.toast.show{transform:translateX(-50%) translateY(0)}
@media(max-width:600px){.sidebar{width:180px}.app{height:98vh;border-radius:12px}}
</style>
</head>
<body>
<div class="wrap">
  <div class="app">
    <div class="sidebar">
      <div class="sh">
        <div class="sh-title">Classroom Messenger</div>
        <div class="sh-sub">Selecciona tu aula</div>
      </div>
      <div class="alist" id="aulaList"></div>
    </div>
    <div class="main">
      <div class="vt">
        <button class="vtb active" id="btnT" onclick="sv('teacher')">✏️ Teacher — Enviar aviso</button>
        <button class="vtb" id="btnD" onclick="sv('director')">📋 Directora — Muro</button>
      </div>
      <div id="tv">
        <div class="mh">
          <div class="mb" id="mainBadge"></div>
          <div class="nw">
            <div class="nr">
              <span class="nd" id="nd" onclick="startEdit()" title="Clic para editar">Escribe tu nombre</span>
              <input class="ni" id="ni" type="text" maxlength="30" placeholder="Tu nombre…" onblur="saveName()" onkeydown="nkey(event)">
              <button class="neb" onclick="startEdit()">✏️</button>
            </div>
            <div class="nh" id="nh"></div>
          </div>
        </div>
        <div class="msgs" id="msgs"></div>
        <div class="ca">
          <div class="cc">
            <button class="cb cm2 selected" id="cat-material" onclick="sc('material')">📦 Material</button>
            <button class="cb cu" id="cat-urgente" onclick="sc('urgente')">🚨 Urgente</button>
            <button class="cb ci" id="cat-info" onclick="sc('info')">💬 Info</button>
            <button class="cb cay" id="cat-ayuda" onclick="sc('ayuda')">🙋 Ayuda</button>
          </div>
          <div class="crow">
            <textarea class="cin" id="cin" placeholder="Escribe tu aviso… (Enter para enviar)" rows="1" onkeydown="hkey(event)"></textarea>
            <button class="sb" onclick="send()">➤</button>
          </div>
        </div>
      </div>
      <div id="dv">
        <div class="dtb">
          <div class="dt">🗂️ Muro de avisos</div>
          <div class="fps">
            <button class="fp active" onclick="fb('all',this)">Todos</button>
            <button class="fp" onclick="fb('material',this)">📦 Material</button>
            <button class="fp" onclick="fb('urgente',this)">🚨 Urgente</button>
            <button class="fp" onclick="fb('info',this)">💬 Info</button>
            <button class="fp" onclick="fb('ayuda',this)">🙋 Ayuda</button>
          </div>
        </div>
        <div class="board" id="board"></div>
      </div>
    </div>
  </div>
</div>
<div class="mo" id="modal">
  <div class="md">
    <h3 id="mt">Responder</h3>
    <p id="ms"></p>
    <textarea id="mta" placeholder="Escribe tu respuesta…"></textarea>
    <div class="mda">
      <button class="mcan" onclick="closeM()">Cancelar</button>
      <button class="msnd" onclick="cr()">Enviar ➤</button>
    </div>
  </div>
</div>
<div class="toast" id="toast"></div>
<script>
const aulas=[
  {id:'K1',label:'K1',c:'#fde8eb',t:'#ec4e63'},
  {id:'K2',label:'K2',c:'#fff0e8',t:'#d9783b'},
  {id:'K3',label:'K3',c:'#e8f5f5',t:'#3a9494'},
  {id:'K4',label:'K4',c:'#edf5e6',t:'#5a8a40'},
  {id:'K5',label:'K5',c:'#fef0f5',t:'#db87a6'},
  {id:'K6',label:'K6',c:'#fff8e0',t:'#b08a00'},
  {id:'K7',label:'K7',c:'#f0eeff',t:'#7c6de0'},
  {id:'K8',label:'K8',c:'#e8f0ff',t:'#4a6fd4'},
  {id:'K9',label:'K9',c:'#fde8f5',t:'#b8459a'},
  {id:'K10',label:'K10',c:'#e8fdf0',t:'#2a9a60'},
  {id:'POL',label:'Pol',c:'#f0f0f0',t:'#555'},
];
const cats={
  material:{label:'Material',icon:'📦',bg:'#fff0e8',col:'#d9783b'},
  urgente:{label:'Urgente',icon:'🚨',bg:'#fde8eb',col:'#ec4e63'},
  info:{label:'Info',icon:'💬',bg:'#e8f5f5',col:'#3a9494'},
  ayuda:{label:'Ayuda',icon:'🙋',bg:'#edf5e6',col:'#5a8a40'},
};
let aid='K1',selCat='material',view='teacher',filt='all',rid=null,mid=0;
function ld(){try{const d=localStorage.getItem('cm_v4');if(d)return JSON.parse(d);}catch(e){}return{names:{},msgs:[]};}
let S=ld();
if(S.msgs.length)mid=Math.max(...S.msgs.map(m=>m.id));
function save(){try{localStorage.setItem('cm_v4',JSON.stringify(S));}catch(e){}}
function gn(id){return S.names[id]||'';}
function sn(id,n){S.names[id]=n.trim();save();}
function lbl(id){return id==='POL'?'Polivalente':'Aula '+id;}
function rSidebar(){
  document.getElementById('aulaList').innerHTML=aulas.map(a=>{
    const p=S.msgs.filter(m=>m.aid===a.id&&!m.done).length;
    return`<div class="ai ${a.id===aid?'active':''}" onclick="selAula('${a.id}')">
      <div class="ab" style="background:${a.c};color:${a.t};">${a.label}</div>
      <div class="ainf"><div class="al">${lbl(a.id)}</div><div class="at">${gn(a.id)||'—'}</div></div>
      ${p>0?`<span class="uc">${p}</span>`:''}
    </div>`;
  }).join('');
}
function selAula(id){aid=id;rSidebar();rHead();rMsgs();if(view==='director')rBoard();}
function rHead(){
  const a=aulas.find(x=>x.id===aid);
  const b=document.getElementById('mainBadge');
  b.textContent=a.label;b.style.background=a.c;b.style.color=a.t;
  const n=gn(aid),nd=document.getElementById('nd');
  nd.textContent=n||'Escribe tu nombre';nd.style.color=n?'var(--d)':'#bbb';
  document.getElementById('nh').textContent=lbl(aid)+' · Toca el nombre para editarlo';
}
function startEdit(){
  const nd=document.getElementById('nd'),ni=document.getElementById('ni');
  ni.value=gn(aid);nd.style.display='none';ni.style.display='inline-block';
  document.querySelector('.neb').style.display='none';ni.focus();ni.select();
}
function saveName(){
  const ni=document.getElementById('ni'),nd=document.getElementById('nd');
  const v=ni.value.trim();sn(aid,v);
  nd.textContent=v||'Escribe tu nombre';nd.style.color=v?'var(--d)':'#bbb';
  nd.style.display='';ni.style.display='none';
  document.querySelector('.neb').style.display='';
  rSidebar();if(view==='director')rBoard();if(v)toast('✅ Nombre: '+v);
}
function nkey(e){if(e.key==='Enter'){e.preventDefault();saveName();}if(e.key==='Escape'){document.getElementById('ni').value=gn(aid);saveName();}}
function rMsgs(){
  const el=document.getElementById('msgs');
  const ms=S.msgs.filter(m=>m.aid===aid);
  if(!ms.length){el.innerHTML='<div class="es"><div class="ei">💬</div><div>No hay avisos desde esta aula.<br>¡Escribe el primero!</div></div>';return;}
  el.innerHTML=ms.map(m=>{const c=cats[m.cat];return`<div class="mr"><div class="mbub">
    <span class="cp" style="background:${c.bg};color:${c.col};">${c.icon} ${c.label}</span><br>${esc(m.txt)}
    ${m.done?'<div style="color:#a0bb7f;font-size:11px;font-weight:700;margin-top:5px;">✅ Gestionado</div>':''}
  </div><div class="mm">${m.t}${m.who?' · '+esc(m.who):''}</div></div>`;}).join('');
  el.scrollTop=el.scrollHeight;
}
function sc(cat){selCat=cat;['material','urgente','info','ayuda'].forEach(c=>document.getElementById('cat-'+c).classList.toggle('selected',c===cat));}
function hkey(e){if(e.key==='Enter'&&!e.shiftKey){e.preventDefault();send();}}
function send(){
  const inp=document.getElementById('cin'),txt=inp.value.trim();
  if(!txt){toast('✏️ Escribe un mensaje');return;}
  const now=new Date(),t=now.getHours().toString().padStart(2,'0')+':'+now.getMinutes().toString().padStart(2,'0');
  S.msgs.push({id:++mid,aid,who:gn(aid),cat:selCat,txt,t,done:false});
  save();inp.value='';rMsgs();rSidebar();if(view==='director')rBoard();toast('✅ Aviso enviado');
}
function sv(v){
  view=v;
  document.getElementById('tv').style.display=v==='teacher'?'flex':'none';
  document.getElementById('dv').style.display=v==='director'?'flex':'none';
  document.getElementById('btnT').classList.toggle('active',v==='teacher');
  document.getElementById('btnD').classList.toggle('active',v==='director');
  if(v==='director')rBoard();
}
function fb(cat,btn){filt=cat;document.querySelectorAll('.fp').forEach(p=>p.classList.remove('active'));btn.classList.add('active');rBoard();}
function rBoard(){
  const el=document.getElementById('board');
  let ms=filt==='all'?S.msgs:S.msgs.filter(m=>m.cat===filt);
  ms=[...ms].reverse();
  if(!ms.length){el.innerHTML='<div class="es"><div class="ei">🎉</div><div>El muro está vacío.<br>Los avisos aparecerán aquí.</div></div>';return;}
  el.innerHTML=ms.map(m=>{
    const a=aulas.find(x=>x.id===m.aid),c=cats[m.cat];
    return`<div class="bm ${m.done?'done':''}">
      <div class="bab" style="background:${a.c};color:${a.t};">${a.label}</div>
      <div class="bb">
        <div class="bh">
          <span class="ban">${lbl(m.aid)}</span>
          ${m.who?`<span class="bwho">${esc(m.who)}</span>`:''}
          <span class="cp" style="background:${c.bg};color:${c.col};">${c.icon} ${c.label}</span>
          ${m.done?'<span class="dtag">✅ Gestionado</span>':''}
        </div>
        <div class="bt">${esc(m.txt)}</div>
        <div class="btime">${m.t}</div>
        <div class="bact">
          ${!m.done?`<button class="abtn aok" onclick="mkDone(${m.id})">✅ Gestionado</button>`:''}
          <button class="abtn arep" onclick="openRep(${m.id})">💬 Responder</button>
        </div>
      </div>
    </div>`;
  }).join('');
}
function mkDone(id){const m=S.msgs.find(x=>x.id===id);if(m){m.done=true;save();}rBoard();rSidebar();rMsgs();toast('✅ Marcado como gestionado');}
function openRep(id){
  rid=id;const m=S.msgs.find(x=>x.id===id);
  document.getElementById('mt').textContent='Responder · '+lbl(m.aid);
  document.getElementById('ms').textContent=m.who||'Sin nombre';
  document.getElementById('mta').value='';
  document.getElementById('modal').classList.add('open');
  setTimeout(()=>document.getElementById('mta').focus(),80);
}
function closeM(){document.getElementById('modal').classList.remove('open');rid=null;}
function cr(){
  const txt=document.getElementById('mta').value.trim();if(!txt)return;
  const m=S.msgs.find(x=>x.id===rid);closeM();toast('💬 Respuesta enviada a '+lbl(m.aid));
}
document.getElementById('modal').addEventListener('click',e=>{if(e.target===document.getElementById('modal'))closeM();});
function esc(s){return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');}
function toast(msg){const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');clearTimeout(t._x);t._x=setTimeout(()=>t.classList.remove('show'),2600);}
rSidebar();rHead();rMsgs();
</script>
</body>
</html>
