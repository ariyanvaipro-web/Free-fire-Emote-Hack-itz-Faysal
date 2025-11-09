
<html lang="bn">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>B25 CHEATS — Demo (Safe Simulation)</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
  :root{
    --bg1:#071324; --bg2:#0b1b2b; --card:#071b2a;
    --accent:#4f46e5; --accent2:#8b5cf6;
    --muted:#98a8b8; --ok:#22c55e; --err:#ef4444; --white:#fff;
  }
  *{box-sizing:border-box}
  html,body{height:100%;margin:0;font-family:Inter, "Segoe UI", Roboto, Arial, sans-serif;background:
    radial-gradient(600px 300px at 10% 10%, rgba(79,70,229,0.12), transparent),
    linear-gradient(180deg,var(--bg1),var(--bg2)); color:var(--white);-webkit-font-smoothing:antialiased}
  .wrap{max-width:1100px;margin:28px auto;padding:18px;display:grid;grid-template-columns:360px 1fr;gap:18px}
  .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:14px;padding:18px;box-shadow:0 10px 30px rgba(2,6,23,0.6)}
  /* left column: auth + profile */
  .left .brand{display:flex;gap:12px;align-items:center;margin-bottom:10px}
  .shield{width:54px;height:54;border-radius:12px;background:linear-gradient(135deg,var(--accent),var(--accent2));display:flex;align-items:center;justify-content:center;font-size:20px;box-shadow:0 8px 30px rgba(79,70,229,0.14)}
  h1{font-size:18px;margin:0}
  p.muted{color:var(--muted);font-size:13px;margin-top:6px}
  .tabs{display:flex;gap:8px;margin:12px 0}
  .tab{flex:1;padding:10px;border-radius:10px;text-align:center;cursor:pointer;background:rgba(255,255,255,0.02);font-weight:700;color:var(--muted)}
  .tab.active{background:linear-gradient(90deg,var(--accent),var(--accent2));color:white;box-shadow:0 8px 20px rgba(79,70,229,0.12)}
  label{display:block;font-size:13px;color:var(--muted);margin-bottom:6px}
  input.input{width:100%;padding:10px;border-radius:10px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:var(--white);outline:none}
  .btn{width:100%;padding:10px;border-radius:10px;border:0;font-weight:800;cursor:pointer;margin-top:8px}
  .btn.primary{background:linear-gradient(90deg,var(--accent),var(--accent2));color:white}
  .btn.ghost{background:transparent;border:1px solid rgba(255,255,255,0.04);color:var(--white)}
  .note{font-size:12px;color:var(--muted);text-align:center;margin-top:10px}
  .message{display:none;padding:10px;border-radius:8px;margin:8px 0;font-weight:700;text-align:center}
  .message.error{display:block;background:rgba(239,68,68,0.08);color:var(--err);border:1px solid rgba(239,68,68,0.14)}
  .message.success{display:block;background:rgba(34,197,94,0.08);color:var(--ok);border:1px solid rgba(34,197,94,0.12)}
  /* right column: dashboard & simulated overlay */
  .controls{display:flex;gap:12px;margin-bottom:12px;align-items:center}
  .big-card{padding:18px;border-radius:12px}
  .status-row{display:flex;gap:12px;align-items:center}
  .status-pill{padding:8px 12px;border-radius:999px;background:rgba(255,255,255,0.03);font-weight:700;color:var(--muted)}
  .status-pill.ok{background:rgba(34,197,94,0.12);color:var(--ok)}
  .status-pill.off{background:rgba(239,68,68,0.08);color:var(--err)}
  .panel-grid{display:grid;grid-template-columns:1fr 360px;gap:12px}
  .log{height:220px;overflow:auto;background:rgba(0,0,0,0.25);padding:12px;border-radius:10px;font-family:monospace;font-size:13px}
  .progress{height:12px;background:rgba(255,255,255,0.04);border-radius:8px;overflow:hidden;margin-top:8px}
  .progress > i{display:block;height:100%;background:linear-gradient(90deg,var(--accent),var(--accent2));width:0%}
  .feature-list{display:flex;flex-direction:column;gap:8px}
  .feature{display:flex;justify-content:space-between;align-items:center;padding:8px 10px;border-radius:8px;background:rgba(255,255,255,0.02)}
  .feature input[type=checkbox]{transform:scale(1.25)}
  /* draggable in-game overlay (simulated) */
  .overlay{
    position:fixed; right:20px; bottom:20px; width:320px; max-width:80%;
    background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius:10px;padding:10px;box-shadow:0 20px 60px rgba(2,6,23,0.6);z-index:9999;
    cursor:move;
  }
  .overlay .head{display:flex;align-items:center;justify-content:space-between;gap:8px}
  .overlay h4{margin:0;font-size:14px}
  .overlay .mini-log{height:100px;overflow:auto;font-family:monospace;font-size:12px;padding-top:8px}
  .overlay.hidden{display:none}
  /* small screens */
  @media (max-width:980px){ .wrap{grid-template-columns:1fr; padding:12px} .panel-grid{grid-template-columns:1fr} .overlay{right:10px;left:10px;width:auto} }
</style>
</head>
<body>
  <div class="wrap">
    <!-- LEFT: Auth -->
    <div class="card left">
      <div class="brand">
        <div class="shield"><i class="fas fa-shield-alt"></i></div>
        <div>
          <h1>B25 CHEATS — Demo</h1>
          <div style="font-size:13px;color:var(--muted)">Safe simulation only — কোনো বাস্তব চিট নয়</div>
        </div>
      </div>

      <div class="tabs" role="tablist">
        <div class="tab active" data-tab="login" onclick="switchAuth(event)">Login</div>
        <div class="tab" data-tab="register" onclick="switchAuth(event)">Register</div>
      </div>

      <!-- login form -->
      <div id="login-box">
        <div id="login-msg" class="message"></div>
        <label for="l-identifier">Username or Email</label>
        <input id="l-identifier" class="input" placeholder="username or email">
        <label for="l-password" style="margin-top:8px">Password</label>
        <input id="l-password" class="input" type="password" placeholder="password">
        <button class="btn primary" onclick="doLogin()">Login</button>
        <button class="btn ghost" onclick="fillDemo()">Use demo account</button>
        <div class="note">এই ডেমোতে ডাটা লোকালি ব্রাউজারে সংরক্ষিত হয় (localStorage)</div>
      </div>

      <!-- register form -->
      <div id="register-box" style="display:none">
        <div id="register-msg" class="message"></div>
        <label for="r-username">Username (min 6)</label>
        <input id="r-username" class="input" placeholder="username">
        <label for="r-email" style="margin-top:8px">Gmail Address</label>
        <input id="r-email" class="input" placeholder="your.email@gmail.com">
        <label for="r-pass" style="margin-top:8px">Password</label>
        <input id="r-pass" class="input" type="password" placeholder="password">
        <label for="r-passc" style="margin-top:8px">Confirm Password</label>
        <input id="r-passc" class="input" type="password" placeholder="confirm">
        <button class="btn primary" onclick="doRegister()">Register</button>
      </div>
    </div>

    <!-- RIGHT: Dashboard -->
    <div class="card big-card">
      <div class="controls">
        <div style="flex:1">
          <div style="font-weight:800;font-size:14px">Dashboard</div>
          <div style="color:var(--muted);font-size:13px">Login হলে আপনি এখানে সিমুলেশন কন্ট্রোল দেখতে পাবেন</div>
        </div>
        <div class="status-row">
          <div id="connect-pill" class="status-pill off">Not Connected</div>
        </div>
      </div>

      <div class="panel-grid">
        <div>
          <div style="display:flex;gap:8px;align-items:center;margin-bottom:8px">
            <button id="inject-btn" class="btn primary" onclick="startInject()" disabled><i class="fas fa-bolt"></i> Inject (Simulated)</button>
            <button class="btn ghost" onclick="toggleOverlay()" id="overlay-toggle" disabled><i class="fas fa-window-maximize"></i> Toggle Overlay</button>
          </div>

          <div class="feature-list">
            <div class="feature"><div>ESP (Enemy Info)</div><div><input id="f-esp" type="checkbox" disabled></div></div>
            <div class="feature"><div>Aimbot</div><div><input id="f-aim" type="checkbox" disabled></div></div>
            <div class="feature"><div>Wallhack</div><div><input id="f-wall" type="checkbox" disabled></div></div>
            <div class="feature"><div>Speed</div><div><input id="f-speed" type="checkbox" disabled></div></div>
          </div>

          <div style="margin-top:12px">
            <div style="font-weight:800;margin-bottom:6px">Actions & Logs</div>
            <div id="log" class="log" aria-live="polite"></div>
          </div>
        </div>

        <div>
          <div style="font-weight:800;margin-bottom:8px">System Status</div>
          <div style="background:rgba(255,255,255,0.02);padding:12px;border-radius:10px">
            <div>Process: <span id="proc-name">—</span></div>
            <div style="margin-top:6px">Memory: <span id="proc-mem">—</span></div>
            <div style="margin-top:8px">Progress</div>
            <div class="progress"><i id="progress-bar"></i></div>
            <div style="margin-top:10px;color:var(--muted);font-size:13px">এইসব তথ্য কেবল সিমুলেটেড; বাস্তব প্রক্রিয়া দেখা/পরিবর্তন করে না।</div>
          </div>

          <div style="margin-top:12px">
            <button class="btn ghost" onclick="clearLogs()">Clear Logs</button>
            <button class="btn ghost" style="margin-top:8px" onclick="resetDemo()">Reset Demo</button>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Simulated draggable overlay -->
  <div id="overlay" class="overlay hidden" aria-hidden="true">
    <div class="head">
      <h4>In-Game Overlay</h4>
      <div style="display:flex;gap:6px;align-items:center">
        <button class="btn ghost" style="padding:6px 8px;font-size:12px" onclick="toggleOverlay()">Close</button>
      </div>
    </div>
    <div style="margin-top:8px;font-size:13px;color:var(--muted)">Live logs (simulated)</div>
    <div id="overlay-log" class="mini-log"></div>
  </div>

<script>
/* ---------------------
   Simple localStorage mock "auth"
   --------------------- */
const LS_USERS_KEY = 'demo_users_v1';
const LS_SESSION = 'demo_session_v1';

// helper: load users (object username -> {email, pass})
function loadUsers(){
  try{ return JSON.parse(localStorage.getItem(LS_USERS_KEY) || '{}') } catch(e){ return {} }
}
function saveUsers(u){ localStorage.setItem(LS_USERS_KEY, JSON.stringify(u)) }

function setSession(username){ localStorage.setItem(LS_SESSION, username); updateUIForAuth() }
function getSession(){ return localStorage.getItem(LS_SESSION) }
function clearSession(){ localStorage.removeItem(LS_SESSION); updateUIForAuth() }

/* UI switching for login/register */
function switchAuth(e){
  document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
  e.currentTarget.classList.add('active');
  const tab = e.currentTarget.dataset.tab;
  document.getElementById('login-box').style.display = tab==='login' ? '' : 'none';
  document.getElementById('register-box').style.display = tab==='register' ? '' : 'none';
  // clear messages
  document.getElementById('login-msg').className='message';
  document.getElementById('register-msg').className='message';
}

/* register */
function doRegister(){
  const u = document.getElementById('r-username').value.trim();
  const email = document.getElementById('r-email').value.trim().toLowerCase();
  const p = document.getElementById('r-pass').value;
  const pc = document.getElementById('r-passc').value;

  if(u.length < 6){ showMsg('register','Username must be at least 6 characters','error'); return }
  if(!email.endsWith('@gmail.com')){ showMsg('register','Please use a Gmail address (@gmail.com)','error'); return }
  if(p.length < 6){ showMsg('register','Password must be at least 6 characters','error'); return }
  if(p !== pc){ showMsg('register','Passwords do not match','error'); return }

  const users = loadUsers();
  if(users[u]){ showMsg('register','Username already taken','error'); return }

  users[u] = { email, pass: p, created: new Date().toISOString() };
  saveUsers(users);
  showMsg('register','Registration successful — You can login now','success');

  // clear inputs
  document.getElementById('r-username').value='';
  document.getElementById('r-email').value='';
  document.getElementById('r-pass').value='';
  document.getElementById('r-passc').value='';

  // switch to login after 1s
  setTimeout(()=> { document.querySelector('[data-tab="login"]').click(); }, 1000);
}

/* login */
function doLogin(){
  const id = document.getElementById('l-identifier').value.trim();
  const p = document.getElementById('l-password').value;
  if(!id || !p){ showMsg('login','Please fill in all fields','error'); return }

  const users = loadUsers();
  // check by username or email
  let found = null;
  for(const uname in users){
    if(uname === id || users[uname].email === id) { found = { uname, ...users[uname] }; break }
  }
  if(!found){ showMsg('login','User not found','error'); return }
  if(found.pass !== p){ showMsg('login','Incorrect password','error'); return }

  // success
  setSession(found.uname);
  showMsg('login','Login successful — Welcome '+found.uname,'success');
}

/* demo helper */
function fillDemo(){
  // create demo account if not exists
  const users = loadUsers();
  if(!users['demo_user']){
    users['demo_user'] = { email:'demo@gmail.com', pass:'demo123', created: new Date().toISOString() };
    saveUsers(users);
  }
  document.getElementById('l-identifier').value = 'demo_user';
  document.getElementById('l-password').value = 'demo123';
  doLogin();
}

/* messages */
function showMsg(area, msg, type='error'){
  const el = document.getElementById(area+'-msg');
  if(!el) return;
  el.textContent = msg;
  el.className = 'message ' + (type==='error' ? 'error' : 'success');
  setTimeout(()=> { el.className = 'message'; }, 5500);
}

/* update UI depending on auth */
function updateUIForAuth(){
  const user = getSession();
  const pill = document.getElementById('connect-pill');
  const injectBtn = document.getElementById('inject-btn');
  const overlayToggle = document.getElementById('overlay-toggle');
  // features toggles
  const features = ['f-esp','f-aim','f-wall','f-speed'];
  if(user){
    pill.textContent = 'Connected: '+user;
    pill.className = 'status-pill ok';
    injectBtn.disabled = false;
    overlayToggle.disabled = false;
    features.forEach(id=> document.getElementById(id).disabled = false);
  } else {
    pill.textContent = 'Not Connected';
    pill.className = 'status-pill off';
    injectBtn.disabled = true;
    overlayToggle.disabled = true;
    features.forEach(id=> { const el = document.getElementById(id); el.checked=false; el.disabled=true; });
    hideOverlay();
  }
  // show process info
  document.getElementById('proc-name').textContent = user ? 'game.exe (simulated)' : '—';
  document.getElementById('proc-mem').textContent = user ? '245 MB (simulated)' : '—';
}

/* ---------------------
   Simulated "Inject" flow
   --------------------- */
let injectInProgress = false;
function startInject(){
  if(injectInProgress) return;
  injectInProgress = true;
  log('Starting simulated injector...');
  setProgress(0);
  const steps = [
    {t:800, msg:'Scanning game process...'},
    {t:900, msg:'Bypassing integrity checks (simulated)...'},
    {t:700, msg:'Allocating memory (simulated)...'},
    {t:900, msg:'Patching modules (simulated)...'},
    {t:700, msg:'Applying features: ESP, Aimbot, Wallhack...'},
    {t:500, msg:'Finalizing...'}
  ];
  let acc = 0;
  let total = steps.length;
  (async function run(){
    for(let i=0;i<steps.length;i++){
      const s = steps[i];
      log(s.msg);
      await sleep(s.t);
      acc++;
      setProgress(Math.round((acc/total)*100));
    }
    log('Injection complete — features active (simulated).');
    injectInProgress = false;
    // enable feature checkboxes as 'active'
    ['f-esp','f-aim','f-wall','f-speed'].forEach(id=>{
      document.getElementById(id).checked = true;
    });
    // also write to overlay log
    overlayLog('Features enabled: ESP, Aimbot, Wallhack, Speed (simulated).');
  })();
}

/* helpers: logging & progress */
function log(msg){
  const el = document.getElementById('log');
  const time = new Date().toLocaleTimeString();
  el.innerText = `[${time}] ${msg}\n` + el.innerText;
}
function overlayLog(msg){
  const el = document.getElementById('overlay-log');
  const time = new Date().toLocaleTimeString();
  el.innerText = `[${time}] ${msg}\n` + el.innerText;
}
function setProgress(p){
  document.getElementById('progress-bar').style.width = p+'%';
}

/* simple sleep */
function sleep(ms){ return new Promise(res=>setTimeout(res, ms)) }

/* clear logs */
function clearLogs(){ document.getElementById('log').innerText=''; document.getElementById('overlay-log').innerText=''; }

/* reset demo */
function resetDemo(){
  clearLogs();
  setProgress(0);
  ['f-esp','f-aim','f-wall','f-speed'].forEach(id=>{ const el=document.getElementById(id); el.checked=false; el.disabled=true; });
  clearSession();
  showMsg('login','Demo reset','success');
}

/* ---------------------
   Overlay toggle & draggable behavior
   --------------------- */
function toggleOverlay(){
  const ov = document.getElementById('overlay');
  if(ov.classList.contains('hidden')){
    ov.classList.remove('hidden');
    ov.setAttribute('aria-hidden','false');
  } else {
    ov.classList.add('hidden');
    ov.setAttribute('aria-hidden','true');
  }
}

/* hide overlay */
function hideOverlay(){ const ov=document.getElementById('overlay'); ov.classList.add('hidden'); ov.setAttribute('aria-hidden','true') }

/* simple drag for overlay */
(function makeOverlayDraggable(){
  const ov = document.getElementById('overlay');
  let dragging = false, ox=0, oy=0, sx=0, sy=0;
  function mdown(e){
    dragging = true;
    const rect = ov.getBoundingClientRect();
    sx = e.clientX; sy = e.clientY;
    ox = rect.left; oy = rect.top;
    ov.style.transition = 'none';
  }
  function mup(){ dragging = false; ov.style.transition=''; }
  function mmove(e){
    if(!dragging) return;
    const dx = e.clientX - sx;
    const dy = e.clientY - sy;
    ov.style.left = (ox + dx) + 'px';
    ov.style.top = (oy + dy) + 'px';
    ov.style.right = 'auto';
    ov.style.bottom = 'auto';
    ov.style.position = 'fixed';
  }
  ov.addEventListener('mousedown', mdown);
  document.addEventListener('mouseup', mup);
  document.addEventListener('mousemove', mmove);
})();

/* ---------------------
   Session on load
   --------------------- */
window.addEventListener('load', ()=>{
  updateUIForAuth();
  // restore overlay position if previously set (optional)
  // show a quick welcome if session exists
  const u = getSession();
  if(u){ log('Welcome back, '+u+' (session restored)'); }
});
</script>
</body>
</html>
