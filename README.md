<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#6c63ff">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-title" content="SkillSwap">
<meta name="description" content="SkillSwap - Alwar mein Skills se Paise Kamao">
<title>SkillSwap — Alwar</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css">
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:sans-serif;background:#f0f4ff;color:#1a1a2e;min-height:100vh}
.hidden{display:none!important}
#installBanner{background:linear-gradient(135deg,#6c63ff,#48bfe3);color:white;padding:0.55rem 1rem;display:none;align-items:center;justify-content:space-between;gap:0.5rem;font-size:0.78rem}
#installBanner button{background:white;color:#6c63ff;border:none;padding:0.28rem 0.75rem;border-radius:20px;font-weight:700;cursor:pointer;font-size:0.74rem}
#installBanner .xb{background:none;border:none;color:white;cursor:pointer;font-size:1rem;padding:0 0.2rem;color:rgba(255,255,255,0.8)}
.auth-screen{display:flex;align-items:center;justify-content:center;min-height:100vh;background:linear-gradient(135deg,#6c63ff,#48bfe3);padding:1rem}
.auth-box{background:white;border-radius:20px;padding:1.8rem;width:100%;max-width:420px;box-shadow:0 8px 32px rgba(0,0,0,0.18)}
.auth-logo{text-align:center;margin-bottom:1.1rem}
.auth-logo h1{font-size:1.8rem;font-weight:800;color:#6c63ff}
.auth-logo p{font-size:0.8rem;color:#888;margin-top:3px}
.role-pick{display:grid;grid-template-columns:1fr 1fr;gap:0.6rem;margin-bottom:1.1rem}
.role-card{border:2px solid #e2e8f0;border-radius:12px;padding:0.85rem 0.5rem;text-align:center;cursor:pointer;transition:all 0.2s}
.role-card:hover,.role-card.sel{border-color:#6c63ff;background:#f5f3ff}
.role-card.sel.client-sel{border-color:#f97316;background:#fff7ed}
.role-card .ri{font-size:1.7rem;margin-bottom:0.25rem}
.role-card h4{font-size:0.8rem;font-weight:700}
.role-card p{font-size:0.68rem;color:#888;margin-top:2px}
.auth-tabs{display:flex;margin-bottom:1rem;border:1px solid #e2e8f0;border-radius:10px;overflow:hidden}
.auth-tab{flex:1;padding:0.52rem;background:none;border:none;cursor:pointer;font-weight:600;font-size:0.82rem;color:#888;transition:all 0.2s}
.auth-tab.active{background:#6c63ff;color:white}
.auth-tab.active.ct{background:#f97316}
.auth-input{width:100%;border:1px solid #ddd;border-radius:10px;padding:0.58rem 1rem;font-size:0.85rem;margin-bottom:0.7rem;outline:none;font-family:inherit;transition:border 0.2s}
.auth-input:focus{border-color:#6c63ff}
.auth-btn{width:100%;background:#6c63ff;color:white;border:none;padding:0.68rem;border-radius:10px;font-weight:700;font-size:0.88rem;cursor:pointer;transition:background 0.2s}
.auth-btn:hover{background:#574fd6}
.auth-btn.cb{background:linear-gradient(135deg,#f59e0b,#f97316)}
.auth-err{color:#ef4444;font-size:0.75rem;margin-bottom:0.4rem;text-align:center;min-height:1rem}
.demo-hint{background:#f8f9ff;border-radius:8px;padding:0.45rem 0.65rem;font-size:0.7rem;color:#666;margin-top:0.6rem;line-height:1.6;border-left:3px solid #6c63ff}
.app-header{color:white;padding:0.8rem 1.2rem;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:0.5rem}
.sh{background:linear-gradient(135deg,#6c63ff,#48bfe3)}
.ch{background:linear-gradient(135deg,#f59e0b,#f97316)}
.ah{background:linear-gradient(135deg,#ef4444,#dc2626)}
.app-header h1{font-size:1.2rem;font-weight:800}
.app-header p{font-size:0.7rem;opacity:0.88;margin-top:1px}
.hdr-right{display:flex;align-items:center;gap:0.4rem;flex-wrap:wrap}
.uchip{background:rgba(255,255,255,0.22);border-radius:20px;padding:0.23rem 0.65rem;font-size:0.71rem;display:flex;align-items:center;gap:0.28rem}
.hbtn{background:white;border:none;padding:0.35rem 0.8rem;border-radius:20px;font-weight:700;cursor:pointer;font-size:0.73rem}
.hbtn.s{color:#6c63ff}.hbtn.c{color:#f97316}.hbtn.a{color:#ef4444}
.lbtn{background:rgba(255,255,255,0.15);color:white;border:1px solid rgba(255,255,255,0.35);padding:0.28rem 0.65rem;border-radius:20px;font-size:0.7rem;cursor:pointer}
.loc-banner{background:linear-gradient(135deg,#10b981,#059669);color:white;padding:0.5rem 1rem;display:flex;align-items:center;gap:0.5rem;font-size:0.75rem;flex-wrap:wrap}
.loc-banner i{font-size:14px}
.loc-pill{background:rgba(255,255,255,0.2);border-radius:20px;padding:0.15rem 0.6rem;font-weight:700;font-size:0.7rem}
.main-tabs{background:white;border-bottom:1px solid #e2e8f0;display:flex;overflow-x:auto}
.mtab{padding:0.65rem 1.1rem;border:none;background:none;cursor:pointer;font-size:0.78rem;font-weight:600;color:#888;border-bottom:2px solid transparent;white-space:nowrap;transition:all 0.2s}
.mtab.active.s{color:#6c63ff;border-bottom-color:#6c63ff}
.mtab.active.c{color:#f97316;border-bottom-color:#f97316}
.mtab.active.a{color:#ef4444;border-bottom-color:#ef4444}
.filters{background:white;padding:0.55rem 1rem;display:flex;gap:0.3rem;flex-wrap:wrap;border-bottom:1px solid #e2e8f0;align-items:center}
.filters-row1{display:flex;gap:0.3rem;flex-wrap:wrap;align-items:center;width:100%}
.filters-row2{display:flex;gap:0.3rem;flex-wrap:wrap;align-items:center;width:100%;padding-top:0.4rem;border-top:1px solid #f0f0f0;margin-top:0.3rem}
.fbtn{background:none;border:1px solid #ddd;padding:0.26rem 0.65rem;border-radius:20px;cursor:pointer;font-size:0.71rem;color:#555;transition:all 0.2s;white-space:nowrap}
.fbtn.active{background:#6c63ff;color:white;border-color:#6c63ff}
.fbtn.active.cf{background:#f97316;border-color:#f97316}
.fbtn.loc-active{background:#10b981;color:white;border-color:#10b981}
.sw{margin-left:auto;display:flex;align-items:center;gap:0.3rem}
.sw input{border:1px solid #ddd;border-radius:20px;padding:0.26rem 0.75rem;font-size:0.72rem;outline:none;width:130px}
.sw input:focus{border-color:#6c63ff}
.filter-label{font-size:0.65rem;color:#aaa;font-weight:600;text-transform:uppercase;letter-spacing:0.03em;white-space:nowrap}
main{padding:0.9rem;max-width:1100px;margin:0 auto}
.srow{display:grid;grid-template-columns:repeat(auto-fit,minmax(90px,1fr));gap:0.55rem;margin-bottom:1rem}
.sc{background:white;border-radius:11px;padding:0.7rem;text-align:center;box-shadow:0 1px 4px rgba(0,0,0,0.06)}
.sc .n{font-size:1.25rem;font-weight:700;color:#6c63ff}
.sc .n.o{color:#f97316}.sc .n.g{color:#10b981}.sc .n.r{color:#ef4444}
.sc .l{font-size:0.63rem;color:#888;margin-top:1px}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(228px,1fr));gap:0.8rem;margin-bottom:5rem}
.stitle{font-size:0.92rem;font-weight:600;margin-bottom:0.75rem;color:#2d2d4e;display:flex;align-items:center;gap:0.4rem}
.stitle .loc-tag{background:#10b98122;color:#059669;font-size:0.68rem;padding:0.15rem 0.5rem;border-radius:20px;font-weight:600}
.card{background:white;border-radius:13px;padding:0.9rem;box-shadow:0 1px 5px rgba(0,0,0,0.07);transition:transform 0.14s,box-shadow 0.14s;position:relative}
.card:hover{transform:translateY(-2px);box-shadow:0 5px 15px rgba(0,0,0,0.1)}
.card.prem{border:2px solid #f59e0b}
.card.urgent{border:2px solid #ef4444}
.card.nearby{border:2px solid #10b981}
.ctop{display:flex;align-items:center;gap:0.55rem;margin-bottom:0.52rem}
.av{width:37px;height:37px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-weight:700;font-size:0.8rem;color:white;flex-shrink:0}
.card h3{font-size:0.83rem;font-weight:600;color:#1a1a2e;line-height:1.3}
.card .sub{font-size:0.68rem;color:#888}
.bdg{display:inline-block;padding:0.13rem 0.52rem;border-radius:20px;font-size:0.65rem;font-weight:600;margin:0.08rem 0.07rem 0 0}
.desc{font-size:0.74rem;color:#555;margin:0.38rem 0 0.65rem;line-height:1.5}
.cfoot{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:0.35rem}
.ptag{font-size:0.78rem;font-weight:700;color:#6c63ff}
.ptag.o{color:#f97316}
/* CONTACT BUTTONS — now 2 buttons */
.contact-btns{display:flex;gap:0.3rem;flex-wrap:wrap}
.abtn{border:none;padding:0.28rem 0.75rem;border-radius:20px;font-size:0.69rem;cursor:pointer;font-weight:600;transition:opacity 0.18s;color:white}
.abtn:hover{opacity:0.85}
.abtn.s{background:#6c63ff}.abtn.c{background:#f97316}.abtn.g{background:#10b981}
/* WhatsApp button */
.wabtn{border:none;padding:0.28rem 0.75rem;border-radius:20px;font-size:0.69rem;cursor:pointer;font-weight:600;color:white;background:#25D366;transition:opacity 0.18s;display:flex;align-items:center;gap:0.25rem}
.wabtn:hover{opacity:0.85}
.cbadge{position:absolute;top:0.52rem;right:0.52rem;font-size:0.6rem;padding:0.1rem 0.4rem;border-radius:20px;font-weight:700;color:white}
.cb-own{background:#10b981}.cb-p{background:#f59e0b}.cb-u{background:#ef4444}.cb-new{background:#6c63ff}.cb-near{background:#10b981}
.rrow{font-size:0.69rem;color:#f0a500;margin-bottom:0.1rem}
.nearby-strip{background:linear-gradient(135deg,#f0fff4,#ecfdf5);border:1px solid #a7f3d0;border-radius:13px;padding:0.9rem;margin-bottom:1rem}
.nearby-strip h3{font-size:0.82rem;font-weight:700;color:#065f46;margin-bottom:0.6rem;display:flex;align-items:center;gap:0.35rem}
.nearby-scroll{display:flex;gap:0.6rem;overflow-x:auto;padding-bottom:0.4rem}
.nearby-scroll::-webkit-scrollbar{height:4px}
.nearby-scroll::-webkit-scrollbar-track{background:#f0f4ff}
.nearby-scroll::-webkit-scrollbar-thumb{background:#10b981;border-radius:2px}
.ncard{background:white;border-radius:10px;padding:0.7rem;min-width:160px;flex-shrink:0;border:1.5px solid #d1fae5;cursor:pointer;transition:all 0.15s}
.ncard:hover{border-color:#10b981;transform:translateY(-1px)}
.ncard .nname{font-size:0.75rem;font-weight:700;color:#1a1a2e;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.ncard .nskill{font-size:0.67rem;color:#888;margin-top:1px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.ncard .ncity{font-size:0.65rem;color:#10b981;font-weight:600;margin-top:3px}
.ncard .nprice{font-size:0.7rem;font-weight:700;color:#6c63ff;margin-top:3px}
.admin-wrap{padding:0.9rem;max-width:1100px;margin:0 auto}
.adm-hdr{background:linear-gradient(135deg,#ef4444,#dc2626);color:white;border-radius:13px;padding:1.1rem;margin-bottom:1rem;display:flex;align-items:center;gap:0.7rem}
.adm-hdr h2{font-size:1rem;font-weight:700}
.adm-hdr p{font-size:0.74rem;opacity:0.85;margin-top:2px}
.adm-stats{display:grid;grid-template-columns:repeat(auto-fit,minmax(100px,1fr));gap:0.6rem;margin-bottom:1rem}
.adm-sc{background:white;border-radius:11px;padding:0.72rem;text-align:center;border-left:3px solid #6c63ff}
.adm-sc .n{font-size:1.2rem;font-weight:700;color:#6c63ff}
.adm-sc.r{border-color:#ef4444}.adm-sc.r .n{color:#ef4444}
.adm-sc.g{border-color:#10b981}.adm-sc.g .n{color:#10b981}
.adm-sc.o{border-color:#f97316}.adm-sc.o .n{color:#f97316}
.adm-sc .l{font-size:0.63rem;color:#888;margin-top:1px}
.adm-sec{background:white;border-radius:13px;padding:0.9rem;margin-bottom:0.9rem;box-shadow:0 1px 4px rgba(0,0,0,0.06)}
.adm-sec h3{font-size:0.86rem;font-weight:700;margin-bottom:0.8rem;color:#2d2d4e;display:flex;align-items:center;gap:0.4rem}
.atable{width:100%;border-collapse:collapse;font-size:0.74rem}
.atable th{text-align:left;padding:0.45rem 0.55rem;border-bottom:2px solid #f0f4ff;color:#888;font-weight:600;font-size:0.66rem;text-transform:uppercase}
.atable td{padding:0.45rem 0.55rem;border-bottom:1px solid #f8f9fa;vertical-align:middle}
.atable tr:last-child td{border:none}
.schip{padding:0.15rem 0.55rem;border-radius:20px;font-size:0.65rem;font-weight:700}
.s-active{background:#d1fae5;color:#065f46}
.s-banned{background:#fee2e2;color:#991b1b}
.s-prem{background:#ede9fe;color:#5b21b6}
.admbtn{border:none;padding:0.22rem 0.55rem;border-radius:7px;font-size:0.65rem;cursor:pointer;font-weight:600;margin-right:0.25rem}
.admbtn:hover{opacity:0.8}
.ab-ban{background:#fee2e2;color:#991b1b}
.ab-unban{background:#fef3c7;color:#92400e}
.ab-del{background:#fee2e2;color:#991b1b}
.ab-prem{background:#ede9fe;color:#5b21b6}
.rev-box{background:#f8f9ff;border-radius:10px;padding:0.75rem}
.rev-row{display:flex;justify-content:space-between;padding:0.3rem 0;border-bottom:1px solid #e2e8f0;font-size:0.77rem}
.rev-row:last-child{border:none;font-weight:700;color:#6c63ff;font-size:0.84rem}
/* MODAL */
.moverlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,0.45);z-index:200;align-items:center;justify-content:center;padding:1rem}
.moverlay.show{display:flex}
.modal{background:white;border-radius:16px;padding:1.4rem;width:100%;max-width:440px;position:relative;max-height:90vh;overflow-y:auto}
.modal h2{font-size:0.98rem;font-weight:700;margin-bottom:0.9rem;color:#2d2d4e}
.modal input,.modal textarea,.modal select{width:100%;border:1px solid #ddd;border-radius:8px;padding:0.53rem 0.85rem;font-size:0.83rem;margin-bottom:0.7rem;outline:none;font-family:inherit;transition:border 0.2s}
.modal input:focus,.modal textarea:focus,.modal select:focus{border-color:#6c63ff}
.modal textarea{height:70px;resize:vertical}
.mbtn{color:white;border:none;width:100%;padding:0.6rem;border-radius:10px;font-weight:700;font-size:0.88rem;cursor:pointer;margin-bottom:0.4rem}
.mbtn.s{background:#6c63ff}.mbtn.c{background:#f97316}.mbtn.wa{background:#25D366}
.xbtn{position:absolute;top:0.85rem;right:0.85rem;background:none;border:none;font-size:1.1rem;cursor:pointer;color:#888}
.empty{text-align:center;padding:2rem 1rem;color:#aaa;font-size:0.83rem;grid-column:1/-1}
.fab{position:fixed;bottom:1.2rem;right:1.2rem;color:white;border:none;border-radius:50%;width:48px;height:48px;font-size:1.35rem;cursor:pointer;display:flex;align-items:center;justify-content:center;z-index:50;box-shadow:0 4px 14px rgba(0,0,0,0.2);transition:transform 0.14s}
.fab:hover{transform:scale(1.08)}
.fab.s{background:#6c63ff}.fab.c{background:#f97316}
.toast{position:fixed;bottom:4.5rem;right:1rem;background:#1a1a2e;color:white;padding:0.58rem 0.95rem;border-radius:10px;font-size:0.78rem;opacity:0;transition:opacity 0.3s;pointer-events:none;z-index:300;max-width:260px}
.toast.show{opacity:1}
/* CONTACT MODAL UPGRADE */
.contact-options{display:grid;grid-template-columns:1fr 1fr;gap:0.6rem;margin-bottom:0.8rem}
.copt{border-radius:12px;padding:0.85rem 0.6rem;text-align:center;cursor:pointer;border:2px solid #e2e8f0;transition:all 0.2s}
.copt:hover{transform:translateY(-1px)}
.copt .ci{font-size:1.6rem;margin-bottom:0.2rem}
.copt .cl{font-size:0.75rem;font-weight:700;margin-bottom:0.1rem}
.copt .cs{font-size:0.65rem;color:#888}
.copt.wa-opt{border-color:#25D366;background:#f0fdf4}
.copt.msg-opt{border-color:#6c63ff;background:#f5f3ff}
/* PROFILE MODAL */
.profile-banner{background:linear-gradient(135deg,#6c63ff,#48bfe3);border-radius:12px;padding:1.2rem;text-align:center;color:white;margin-bottom:0.8rem}
.profile-av{width:60px;height:60px;border-radius:50%;background:rgba(255,255,255,0.3);display:flex;align-items:center;justify-content:center;font-size:1.4rem;font-weight:700;margin:0 auto 0.5rem}
.info-row{display:flex;justify-content:space-between;padding:0.4rem 0;border-bottom:1px solid #f0f0f0;font-size:0.78rem}
.info-row:last-child{border:none}
</style>
</head>
<body>

<div id="installBanner">
  <span>📱 SkillSwap install karo — bilkul app jaisa!</span>
  <div style="display:flex;gap:0.4rem;align-items:center">
    <button onclick="installPWA()">Install</button>
    <button class="xb" onclick="document.getElementById('installBanner').style.display='none'">✕</button>
  </div>
</div>

<!-- AUTH -->
<div class="auth-screen" id="authScreen">
  <div class="auth-box">
    <div class="auth-logo"><h1>🎓 SkillSwap</h1><p>Skills se paise kamao — Alwar, Rajasthan</p></div>
    <div class="role-pick">
      <div class="role-card sel" id="rcStudent" onclick="pickRole('student')">
        <div class="ri">🎓</div><h4>Student</h4><p>Skill offer karo, paise kamao</p>
      </div>
      <div class="role-card" id="rcClient" onclick="pickRole('client')">
        <div class="ri">💼</div><h4>Client</h4><p>Kaam post karo, talent dhundho</p>
      </div>
    </div>
    <div class="auth-tabs">
      <button class="auth-tab active" id="tabLogin" onclick="switchTab('login')">Login</button>
      <button class="auth-tab" id="tabSignup" onclick="switchTab('signup')">Sign Up</button>
    </div>
    <div id="authErr" class="auth-err"></div>
    <div id="loginForm">
      <input class="auth-input" id="lEmail" type="email" placeholder="Email address">
      <input class="auth-input" id="lPass" type="password" placeholder="Password">
      <button class="auth-btn" id="loginBtn" onclick="doLogin()">Login</button>
      <div class="demo-hint">
        🎓 Student: student@demo.com / demo123<br>
        💼 Client: client@demo.com / demo123<br>
        👑 Admin: admin@skillswap.com / admin123<br>
        📍 Alwar: alwar@demo.com / demo123<br>
        <span style="color:#10b981">✅ Naya account banao — Login turant kaam karega!</span>
      </div>
    </div>
    <div id="signupForm" style="display:none">
      <input class="auth-input" id="sName" placeholder="Full Name">
      <input class="auth-input" id="sEmail" type="email" placeholder="Email address">
      <input class="auth-input" id="sPass" type="password" placeholder="Password (min 6 chars)">
      <select class="auth-input" id="sCity" style="padding:0.52rem 1rem">
        <option value="">Apna Shehar Chuniye</option>
        <option value="Alwar">📍 Alwar (Rajasthan)</option>
        <option value="Bhiwadi">📍 Bhiwadi (Alwar)</option>
        <option value="Neemrana">📍 Neemrana (Alwar)</option>
        <option value="Rajgarh">📍 Rajgarh (Alwar)</option>
        <option value="Behror">📍 Behror (Alwar)</option>
        <option value="Tijara">📍 Tijara (Alwar)</option>
        <option value="Jaipur">Jaipur</option>
        <option value="Delhi">Delhi</option>
        <option value="Gurugram">Gurugram</option>
        <option value="Other">Other</option>
      </select>
      <input class="auth-input" id="sPhone" placeholder="WhatsApp Number (Required)">
      <button class="auth-btn" id="signupBtn" onclick="doSignup()">Account Banao</button>
    </div>
    <div style="text-align:center;font-size:0.7rem;color:#aaa;margin-top:0.7rem">Free to join · No fees · WhatsApp se direct contact</div>
  </div>
</div>

<!-- APP -->
<div id="appScreen" style="display:none">
  <div class="app-header sh" id="appHeader">
    <div><h1 id="headerTitle">🎓 SkillSwap</h1><p id="headerSub">Student Portal</p></div>
    <div class="hdr-right">
      <div class="uchip"><i class="ti ti-map-pin" style="font-size:11px"></i><span id="headerLoc">Alwar</span></div>
      <div class="uchip" style="cursor:pointer" onclick="openProfileModal()"><i class="ti ti-user" style="font-size:11px"></i><span id="headerUser"></span></div>
      <button class="hbtn s" id="postBtn" onclick="openPostModal()">+ Post</button>
      <button class="hbtn s" id="premBtn" onclick="openModal('premium')" style="background:#f59e0b;color:white">⭐ Premium</button>
      <button class="lbtn" onclick="doLogout()">Logout</button>
    </div>
  </div>

  <div class="loc-banner" id="locBanner">
    <i class="ti ti-map-pin"></i>
    <span>Aapki Location: <strong>Alwar, Rajasthan</strong> — Aas paas ke</span>
    <span class="loc-pill" id="nearbyCount">20 Students</span>
    <span>& </span>
    <span class="loc-pill" id="nearbyJobCount">15 Jobs</span>
    <span>available hain! <strong>WhatsApp se direct contact karo 📲</strong></span>
  </div>

  <div class="main-tabs" id="mainTabs"></div>

  <div class="filters" id="filtersBar">
    <div class="filters-row1">
      <span class="filter-label">Category:</span>
      <div id="filterBtns" style="display:flex;gap:0.3rem;flex-wrap:wrap"></div>
      <div class="sw"><i class="ti ti-search" style="color:#888;font-size:13px"></i><input type="text" placeholder="Search..." id="searchInput" oninput="renderCards()"></div>
    </div>
    <div class="filters-row2" id="locationFilterRow">
      <span class="filter-label">📍 Location:</span>
      <div id="locFilterBtns" style="display:flex;gap:0.3rem;flex-wrap:wrap"></div>
    </div>
  </div>

  <main id="mainContent">
    <div class="srow" id="statsRow"></div>
    <div class="nearby-strip" id="nearbyStrip" style="display:none">
      <h3>📍 Aapke Aas Paas — Alwar & Near Cities <span style="font-size:0.68rem;background:#25D36622;color:#065f46;padding:0.1rem 0.5rem;border-radius:20px;margin-left:0.3rem">WhatsApp se Contact</span></h3>
      <div class="nearby-scroll" id="nearbyScroll"></div>
    </div>
    <div class="stitle" id="gridTitle"></div>
    <div class="grid" id="cardsGrid"></div>
  </main>

  <div id="adminPanel" style="display:none"></div>
  <button class="fab s" id="fabBtn" onclick="openPostModal()"><i class="ti ti-plus"></i></button>
</div>

<!-- POST SKILL MODAL -->
<div class="moverlay" id="postSkillModal">
  <div class="modal">
    <button class="xbtn" onclick="closeModal('postSkill')">✕</button>
    <h2>🎓 Apni Skill Post Karo</h2>
    <input type="text" id="pSkill" placeholder="Skill Title (e.g. Math Tutoring, Logo Design)">
    <select id="pCat">
      <option value="">Category Select Karo</option>
      <option>Tuition</option><option>Online</option><option>Academic</option><option>Tech</option><option>Creative</option>
      <option>Language</option><option>Music</option><option>Fitness</option>
      <option>Business</option><option>Photography</option><option>Cooking</option><option>Other</option>
    </select>
    <textarea id="pDesc" placeholder="Apni service describe karo..."></textarea>
    <input type="text" id="pPrice" placeholder="Price (e.g. ₹200/hr ya Free)">
    <select id="pCitySkill" style="width:100%;border:1px solid #ddd;border-radius:8px;padding:0.53rem 0.85rem;font-size:0.83rem;margin-bottom:0.7rem;outline:none">
      <option value="Alwar">Alwar</option><option value="Bhiwadi">Bhiwadi</option>
      <option value="Neemrana">Neemrana</option><option value="Rajgarh">Rajgarh</option>
      <option value="Behror">Behror</option><option value="Tijara">Tijara</option>
      <option value="Jaipur">Jaipur</option><option value="Delhi">Delhi</option>
      <option value="Gurugram">Gurugram</option><option value="Other">Other</option>
    </select>
    <input type="text" id="pPhone" placeholder="WhatsApp Number (Contact ke liye zaruri)">
    <input type="text" id="pTags" placeholder="Tags (e.g. hindi, online, weekend)">
    <button class="mbtn s" onclick="postSkill()">Service Post Karo 🚀</button>
  </div>
</div>

<!-- POST JOB MODAL -->
<div class="moverlay" id="postJobModal">
  <div class="modal">
    <button class="xbtn" onclick="closeModal('postJob')">✕</button>
    <h2>💼 Kaam/Job Post Karo</h2>
    <input type="text" id="jTitle" placeholder="Kaam ka title (e.g. Logo Design Chahiye)">
    <select id="jCat">
      <option value="">Category Select Karo</option>
      <option>Tuition</option><option>Online</option><option>Academic</option><option>Tech</option><option>Creative</option>
      <option>Language</option><option>Music</option><option>Fitness</option>
      <option>Business</option><option>Photography</option><option>Cooking</option><option>Other</option>
    </select>
    <textarea id="jDesc" placeholder="Kaam detail mein describe karo..."></textarea>
    <input type="text" id="jBudget" placeholder="Budget (e.g. ₹500 ya Negotiable)">
    <select id="jUrgency">
      <option value="Normal">Normal</option>
      <option value="Urgent">Urgent</option>
      <option value="Flexible">Flexible</option>
    </select>
    <select id="jCityJob" style="width:100%;border:1px solid #ddd;border-radius:8px;padding:0.53rem 0.85rem;font-size:0.83rem;margin-bottom:0.7rem;outline:none">
      <option value="Alwar">Alwar</option><option value="Bhiwadi">Bhiwadi</option>
      <option value="Neemrana">Neemrana</option><option value="Rajgarh">Rajgarh</option>
      <option value="Behror">Behror</option><option value="Tijara">Tijara</option>
      <option value="Jaipur">Jaipur</option><option value="Delhi">Delhi</option>
      <option value="Gurugram">Gurugram</option><option value="Other">Other</option>
    </select>
    <input type="text" id="jPhone" placeholder="Aapka WhatsApp Number">
    <button class="mbtn c" onclick="postJob()">Job Post Karo 💼</button>
  </div>
</div>

<!-- CONTACT MODAL (UPGRADED) -->
<div class="moverlay" id="contactModal">
  <div class="modal">
    <button class="xbtn" onclick="closeModal('contact')">✕</button>
    <h2 id="contactTitle">Contact Karo</h2>
    
    <!-- Target info card -->
    <div id="contactCard" style="background:#f8f9ff;border-radius:11px;padding:0.8rem;margin-bottom:0.9rem;border-left:4px solid #6c63ff">
      <div style="font-size:0.78rem;font-weight:700;color:#2d2d4e" id="ctName"></div>
      <div style="font-size:0.72rem;color:#666;margin-top:0.2rem" id="ctSkill"></div>
      <div style="display:flex;gap:0.5rem;margin-top:0.4rem;flex-wrap:wrap">
        <span style="font-size:0.7rem;font-weight:700;color:#6c63ff" id="ctPrice"></span>
        <span style="font-size:0.7rem;color:#10b981" id="ctCity"></span>
        <span style="font-size:0.7rem;color:#f97316" id="ctRating"></span>
      </div>
    </div>

    <!-- CONTACT OPTIONS -->
    <div style="font-size:0.78rem;font-weight:700;color:#444;margin-bottom:0.5rem">Contact Karne Ka Tarika Chuniye:</div>
    <div class="contact-options">
      <div class="copt wa-opt" id="waOptBtn" onclick="chooseContactType('whatsapp')">
        <div class="ci">💬</div>
        <div class="cl" style="color:#128C7E">WhatsApp Direct</div>
        <div class="cs">Seedha chat khulega</div>
      </div>
      <div class="copt msg-opt" id="msgOptBtn" onclick="chooseContactType('message')">
        <div class="ci">📩</div>
        <div class="cl" style="color:#6c63ff">Site Message</div>
        <div class="cs">App ke andar message</div>
      </div>
    </div>

    <!-- WHATSAPP SECTION -->
    <div id="waSection" style="display:none">
      <div style="background:#f0fdf4;border:1px solid #bbf7d0;border-radius:11px;padding:0.8rem;margin-bottom:0.7rem">
        <div style="font-size:0.75rem;font-weight:700;color:#065f46;margin-bottom:0.4rem">📲 WhatsApp Contact Details</div>
        <div style="font-size:1.1rem;font-weight:800;color:#128C7E;margin-bottom:0.2rem" id="waNumber">Loading...</div>
        <div style="font-size:0.68rem;color:#555" id="waName"></div>
      </div>
      <textarea id="waMsg" placeholder="WhatsApp par bhejne wala message likhо..." style="width:100%;border:1px solid #ddd;border-radius:8px;padding:0.5rem;font-size:0.82rem;height:80px;outline:none;font-family:inherit;margin-bottom:0.6rem;resize:vertical"></textarea>
      <button class="mbtn wa" onclick="openWhatsApp()">📲 WhatsApp par Chat Karo →</button>
      <div style="font-size:0.68rem;color:#888;text-align:center;margin-top:0.3rem">WhatsApp app mein seedha chat khulega</div>
    </div>

    <!-- SITE MESSAGE SECTION -->
    <div id="msgSection" style="display:none">
      <textarea id="cMsg" placeholder="Apna message likhо..." style="width:100%;border:1px solid #ddd;border-radius:8px;padding:0.5rem;font-size:0.82rem;height:80px;outline:none;font-family:inherit;margin-bottom:0.6rem;resize:vertical"></textarea>
      <button class="mbtn s" id="contactSendBtn" onclick="sendMsg()">Message Bhejo ↗</button>
    </div>

    <!-- No phone warning -->
    <div id="noPhoneWarning" style="display:none;background:#fffbeb;border:1px solid #fde68a;border-radius:9px;padding:0.6rem;font-size:0.72rem;color:#92400e;margin-top:0.5rem">
      ⚠️ Is user ne WhatsApp number nahi diya. Site message use karo ya manually contact karo.
    </div>
  </div>
</div>

<!-- PROFILE MODAL -->
<div class="moverlay" id="profileModal">
  <div class="modal">
    <button class="xbtn" onclick="closeModal('profile')">✕</button>
    <h2>👤 Meri Profile</h2>
    <div class="profile-banner" id="profileBanner">
      <div class="profile-av" id="profileAv">AB</div>
      <div style="font-size:1rem;font-weight:700" id="profileName"></div>
      <div style="font-size:0.75rem;opacity:0.85" id="profileRole"></div>
    </div>
    <div id="profileInfo"></div>
    <div style="margin-top:0.8rem">
      <input type="text" id="editPhone" placeholder="WhatsApp Number update karo" style="width:100%;border:1px solid #ddd;border-radius:8px;padding:0.5rem 0.85rem;font-size:0.82rem;margin-bottom:0.5rem;outline:none">
      <button class="mbtn s" onclick="updatePhone()">📱 WhatsApp Number Save Karo</button>
    </div>
  </div>
</div>

<!-- PREMIUM MODAL -->
<div class="moverlay" id="premiumModal">
  <div class="modal" style="text-align:center">
    <button class="xbtn" onclick="closeModal('premium')">✕</button>
    <div style="font-size:2.2rem;margin-bottom:0.4rem">⭐</div>
    <h2 style="text-align:center;margin-bottom:0.4rem">Premium Membership</h2>
    <p style="font-size:0.78rem;color:#666;margin-bottom:0.8rem">Sabse upar dikhao, zyada clients pao!</p>
    <div style="background:#f8f9ff;border-radius:11px;padding:0.9rem;margin-bottom:0.9rem;text-align:left;font-size:0.78rem;line-height:1.9">
      ✅ Featured listing (sabse upar)<br>✅ Premium gold badge<br>✅ Unlimited listings<br>✅ Priority support<br>✅ Profile verified tick<br>✅ WhatsApp contact badge<br>✅ Alwar/Rajasthan Local Featured Section
    </div>
    <div style="font-size:1.5rem;font-weight:800;color:#6c63ff;margin-bottom:0.8rem">₹99 <span style="font-size:0.85rem;font-weight:400;color:#888">/month</span></div>

    <div id="pmStep1">
      <p style="font-size:0.77rem;font-weight:700;color:#444;margin-bottom:0.6rem">Payment Method Chuniye:</p>
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:0.5rem;margin-bottom:0.8rem">
        <div id="optPhonePe" onclick="selectPayMethod('phonepay')" style="border:2px solid #5f259f;border-radius:11px;padding:0.7rem;cursor:pointer;background:#faf5ff">
          <div style="font-size:1.5rem">📱</div>
          <div style="font-size:0.74rem;font-weight:700;color:#5f259f;margin-top:3px">PhonePe</div>
          <div style="font-size:0.65rem;color:#888">UPI / Wallet</div>
        </div>
        <div id="optUPI" onclick="selectPayMethod('upi')" style="border:2px solid #ddd;border-radius:11px;padding:0.7rem;cursor:pointer;background:#f9f9f9">
          <div style="font-size:1.5rem">💳</div>
          <div style="font-size:0.74rem;font-weight:700;color:#444;margin-top:3px">Any UPI App</div>
          <div style="font-size:0.65rem;color:#888">GPay / Paytm etc.</div>
        </div>
      </div>
      <button class="mbtn s" style="background:linear-gradient(135deg,#f59e0b,#f97316)" onclick="goToPayment()">Aage Badho →</button>
    </div>

    <div id="pmPhonePe" style="display:none">
      <div style="background:linear-gradient(135deg,#5f259f,#7b2ff7);border-radius:13px;padding:1rem;margin-bottom:0.8rem;color:white">
        <div style="font-size:0.8rem;font-weight:700;margin-bottom:0.3rem">📱 PhonePe se Payment Karo</div>
        <div style="font-size:1.4rem;font-weight:800;letter-spacing:2px;margin:0.4rem 0">7877353121</div>
        <div style="font-size:0.7rem;opacity:0.85">SkillSwap Premium · Alwar, Rajasthan</div>
      </div>
      <canvas id="qrCanvas" width="140" height="140" style="border-radius:8px;display:block;margin:0 auto 0.8rem"></canvas>
      <div style="background:#f0fdf4;border:1px solid #bbf7d0;border-radius:9px;padding:0.6rem;margin-bottom:0.8rem;font-size:0.72rem;color:#166534;text-align:left;line-height:1.7">
        1️⃣ PhonePe kholo → "Send Money"<br>
        2️⃣ Number: <strong>7877353121</strong><br>
        3️⃣ Amount: <strong>₹99</strong><br>
        4️⃣ Screenshot lo & confirm karo
      </div>
      <input type="text" id="ppTxnId" placeholder="Transaction ID ya UTR Number" style="width:100%;border:1px solid #ddd;border-radius:8px;padding:0.5rem;font-size:0.82rem;margin-bottom:0.5rem;outline:none">
      <button class="mbtn s" style="background:#5f259f" onclick="confirmPayment('phonepay')">✅ Payment Confirm Karo</button>
      <button onclick="document.getElementById('pmPhonePe').style.display='none';document.getElementById('pmStep1').style.display='block'" style="margin-top:0.4rem;background:none;border:none;color:#888;font-size:0.72rem;cursor:pointer;display:block;width:100%">← Wapas Jao</button>
    </div>

    <div id="pmUPI" style="display:none">
      <div style="background:linear-gradient(135deg,#1a73e8,#4285f4);border-radius:13px;padding:1rem;margin-bottom:0.8rem;color:white">
        <div style="font-size:0.8rem;font-weight:700;margin-bottom:0.3rem">💳 Kisi bhi UPI App se Pay Karo</div>
        <div style="font-size:1.1rem;font-weight:800;margin:0.4rem 0">7877353121@ybl</div>
      </div>
      <input type="text" id="upiTxnId" placeholder="Transaction ID ya UTR Number" style="width:100%;border:1px solid #ddd;border-radius:8px;padding:0.5rem;font-size:0.82rem;margin-bottom:0.5rem;outline:none">
      <button class="mbtn s" style="background:#1a73e8" onclick="confirmPayment('upi')">✅ Payment Confirm Karo</button>
      <button onclick="document.getElementById('pmUPI').style.display='none';document.getElementById('pmStep1').style.display='block'" style="margin-top:0.4rem;background:none;border:none;color:#888;font-size:0.72rem;cursor:pointer;display:block;width:100%">← Wapas Jao</button>
    </div>

    <div id="pmSuccess" style="display:none">
      <div style="font-size:3rem;margin-bottom:0.5rem">🎉</div>
      <h3 style="color:#10b981;margin-bottom:0.4rem">Payment Submit Ho Gayi!</h3>
      <p style="font-size:0.76rem;color:#666;margin-bottom:0.8rem">Admin 2-4 ghante mein aapka Premium activate kar dega.</p>
      <div style="background:#f0fdf4;border:1px solid #bbf7d0;border-radius:9px;padding:0.7rem;font-size:0.74rem;color:#166534;margin-bottom:0.8rem">
        📞 Koi problem? WhatsApp: <strong>7877353121</strong>
      </div>
      <button class="mbtn s" style="background:#10b981" onclick="closeModal('premium');document.getElementById('pmStep1').style.display='block';document.getElementById('pmSuccess').style.display='none'">Done ✓</button>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<script>
// PWA
let deferredPrompt=null;
window.addEventListener('beforeinstallprompt',e=>{
  e.preventDefault();deferredPrompt=e;
  document.getElementById('installBanner').style.display='flex';
});
function installPWA(){
  if(deferredPrompt){deferredPrompt.prompt();deferredPrompt.userChoice.then(()=>{deferredPrompt=null;document.getElementById('installBanner').style.display='none';});}
}

const USER_LOCATION='Alwar';
const NEARBY_CITIES=['Alwar','Bhiwadi','Neemrana','Rajgarh','Behror','Tijara','Alwar City','Kishangarh Bas','Ramgarh','Laxmangarh'];
const RAJASTHAN_CITIES=['Jaipur','Ajmer','Jodhpur','Kota','Bikaner','Udaipur','Bharatpur','Sikar','Pali','Tonk'];
const ALL_LOCATION_FILTERS=['Mere Paas','Alwar Zila','Rajasthan','Sabhi'];
const catColors={Tuition:'#06b6d4',Online:'#7c3aed',Academic:'#3b82f6',Tech:'#8b5cf6',Creative:'#f59e0b',Language:'#10b981',Music:'#ec4899',Fitness:'#ef4444',Business:'#0ea5e9',Photography:'#ec4899',Cooking:'#f97316',Other:'#64748b'};
const avColors=['#6c63ff','#48bfe3','#f59e0b','#10b981','#ec4899','#ef4444','#8b5cf6','#0ea5e9','#f97316','#14b8a6'];
const studentCats=['All','Tuition','Online','Academic','Tech','Creative','Language','Music','Fitness','Business','Photography','Cooking','Other'];

let users=[
  {email:'admin@skillswap.com',pass:'admin123',name:'Admin',city:'Alwar',role:'admin',premium:false,status:'active',phone:'7877353121'},
  {email:'student@demo.com',pass:'demo123',name:'Demo Student',city:'Delhi',role:'student',premium:true,status:'active',phone:'9876500000'},
  {email:'client@demo.com',pass:'demo123',name:'Demo Client',city:'Mumbai',role:'client',premium:false,status:'active',phone:'9876511111'},
  {email:'alwar@demo.com',pass:'demo123',name:'Alwar Student',city:'Alwar',role:'student',premium:false,status:'active',phone:'9414000001'},
];

// ─── ALWAR DATA ───
const alwarStudents=[
  {name:'Rahul Sharma',city:'Alwar',skill:'Math & Science Tutor (Class 6-12)',cat:'Academic',desc:'RBSE/CBSE Math, Science tutor. Alwar city mein ghar par aake padhata hoon. 5 saal ka experience.',price:'₹100/hr',rating:4.8,reviews:22,phone:'9414101001'},
  {name:'Priya Agarwal',city:'Alwar',skill:'Computer Basics & MS Office Training',cat:'Tech',desc:'Computer basics, MS Office, Tally sikhaati hoon. Alwar ke students ke liye offline classes.',price:'₹120/hr',rating:4.6,reviews:15,phone:'9414102002'},
  {name:'Deepak Gurjar',city:'Bhiwadi',skill:'English Speaking & Personality Dev',cat:'Language',desc:'Bhiwadi industrial area ke workers & students ke liye English communication classes.',price:'₹80/hr',rating:4.5,reviews:18,phone:'9414103003'},
  {name:'Sunita Meena',city:'Alwar',skill:'Mehndi Design & Art Classes',cat:'Creative',desc:'Bridal mehndi, traditional Rajasthani art. Alwar mein ghar par seekhiye. Ladies only.',price:'₹500/event',rating:4.9,reviews:31,phone:'9414104004'},
  {name:'Arjun Yadav',city:'Neemrana',skill:'Mobile Repair & Electronics',cat:'Tech',desc:'Mobile screen repair, battery, software issues. Neemrana & Bhiwadi area mein service.',price:'₹200/repair',rating:4.7,reviews:40,phone:'9414105005'},
  {name:'Kavita Sharma',city:'Alwar',skill:'Tailoring & Stitching Classes',cat:'Creative',desc:'Ladies suit, blouse, kurti stitching. Alwar mein ghar par classes. Beginner se advance.',price:'₹1500/month',rating:4.8,reviews:25,phone:'9414106006'},
  {name:'Mohit Kumar',city:'Rajgarh',skill:'Driving Instructor (2-Wheeler)',cat:'Fitness',desc:'Scooter, motorcycle sikhata hoon. Rajgarh & aas paas area. Sabr se sikhata hoon.',price:'₹500/week',rating:4.4,reviews:12,phone:'9414107007'},
  {name:'Pooja Bansal',city:'Alwar',skill:'Yoga & Aerobics (Ladies Group)',cat:'Fitness',desc:'Subah 6 baje Alwar mein ladies yoga classes. Weight loss, flexibility, meditation.',price:'₹600/month',rating:4.9,reviews:45,phone:'9414108008'},
  {name:'Nisha Jain',city:'Alwar',skill:'Tiffin & Home Food Service',cat:'Cooking',desc:'Ghar ka khana — Rajasthani thali, dal baati. Alwar city delivery available. Pure veg.',price:'₹70/meal',rating:4.9,reviews:67,phone:'9414109009'},
  {name:'Rohit Meena',city:'Alwar',skill:'Photography (Events & Portraits)',cat:'Photography',desc:'Wedding, birthday, function photography. Alwar & nearby. Canon DSLR. Editing included.',price:'₹2000/event',rating:4.6,reviews:19,phone:'9414110010'},
  {name:'Pawan Verma',city:'Bhiwadi',skill:'Electrical Wiring & Fittings',cat:'Other',desc:'Ghar ki wiring, switchboard, fan fitting. Bhiwadi & Alwar. Licensed electrician.',price:'₹300/visit',rating:4.8,reviews:55,phone:'9414111011'},
  {name:'Manisha Agarwal',city:'Alwar',skill:'Rajasthani & North Indian Cooking',cat:'Cooking',desc:'Dal baati churma, gatte ki sabzi, ker sangri. Cooking classes & tiffin service Alwar.',price:'₹400/class',rating:4.9,reviews:28,phone:'9414112012'},
  {name:'Kapil Dev',city:'Neemrana',skill:'Guitar & Harmonium Classes',cat:'Music',desc:'Bollywood songs guitar & harmonium. Neemrana & Bhiwadi. Beginner friendly.',price:'₹200/hr',rating:4.5,reviews:9,phone:'9414113013'},
  {name:'Savita Yadav',city:'Alwar',skill:'Nursery & KG Home Tutor',cat:'Academic',desc:'Nursery se Class 2 tak ghar par tuition. Alwar. English medium & Hindi medium both.',price:'₹800/month',rating:4.9,reviews:38,phone:'9414114014'},
  {name:'Harish Bairwa',city:'Alwar',skill:'REET & Government Exam Coaching',cat:'Academic',desc:'Rajasthan REET, Patwari, Police exam guidance. Group study bhi karta hoon Alwar.',price:'₹200/hr',rating:4.8,reviews:44,phone:'9414115015'},
  {name:'Rahul Jangid',city:'Bhiwadi',skill:'AC & Refrigerator Repair',cat:'Other',desc:'AC servicing, ghar par aakar repair. Bhiwadi, Neemrana, Alwar. Same day service.',price:'₹400/visit',rating:4.7,reviews:88,phone:'9414116016'},
  {name:'Monika Bansal',city:'Alwar',skill:'Online Math Tutor (Google Meet)',cat:'Academic',desc:'Online Math tutoring for Class 6-12. Daily live classes. Google Meet par. Poore India ke liye.',price:'₹500/month',rating:4.8,reviews:67,phone:'9414117017'},
  {name:'Vishal Gupta',city:'Alwar',skill:'Online Python & Coding Classes',cat:'Tech',desc:'Online live coding classes. Beginner to intermediate. Python, HTML, CSS. Sabhi ke liye.',price:'₹800/month',rating:4.7,reviews:31,phone:'9414118018'},
  {name:'Kajal Singh',city:'Alwar',skill:'Online English Speaking (Live)',cat:'Language',desc:'Daily 1 hour online English practice sessions. Small batch (5 log). Zoom/Google Meet.',price:'₹400/month',rating:4.8,reviews:55,phone:'9414119019'},
  {name:'Shilpa Sharma',city:'Alwar',skill:'Online Yoga (Morning Batch)',cat:'Fitness',desc:'Roz subah 6am online yoga. Zoom par. Weight loss, flexibility. Ladies only batch bhi.',price:'₹300/month',rating:4.9,reviews:88,phone:'9414120020'},
  {name:'Anil Saini',city:'Neemrana',skill:'Online Tally & Accounting',cat:'Business',desc:'Tally ERP, GST online sikhao. Working professionals ke liye evening batch. Certificate bhi.',price:'₹700/month',rating:4.7,reviews:41,phone:'9414121021'},
  {name:'Divya Meena',city:'Rajgarh',skill:'Spoken English for Interviews',cat:'Language',desc:'Job interviews ke liye English. Mock interviews, vocabulary, confidence building. Online.',price:'₹500/month',rating:4.7,reviews:36,phone:'9414122022'},
  {name:'Sumit Yadav',city:'Alwar',skill:'Class 9-10 Science Tutor',cat:'Academic',desc:'RBSE Science (Physics + Chemistry + Biology). Diagrams, notes, past papers. Alwar city.',price:'₹1000/month',rating:4.8,reviews:23,phone:'9414123023'},
  {name:'Seema Agarwal',city:'Alwar',skill:'Digital Marketing (Online)',cat:'Business',desc:'Facebook ads, Instagram marketing, YouTube SEO. Live classes. Freelance work bhi dilao.',price:'₹800/month',rating:4.7,reviews:45,phone:'9414124024'},
  {name:'Asha Yadav',city:'Alwar',skill:'Cooking Classes (Online + Offline)',cat:'Cooking',desc:'Rajasthani, Punjabi, Chinese cooking. Online WhatsApp video ya offline Alwar mein.',price:'₹400/month',rating:4.9,reviews:62,phone:'9414125025'},
];

const alwarJobs=[
  {name:'Alwar Public School',city:'Alwar',title:'Math & Science Tutor Chahiye',cat:'Academic',desc:'Class 8-10 ke students ke liye ghar par tutor chahiye. Alwar city area. Immediately required.',budget:'₹3000/month',urgency:'Urgent',phone:'9413101001'},
  {name:'Sharma Medical Store',city:'Alwar',title:'Computer Operator Chahiye',cat:'Tech',desc:'Medical store ke liye billing software & computer operator. Alwar sadar bazar.',budget:'₹8000/month',urgency:'Normal',phone:'9413102002'},
  {name:'Hotel Sariska Palace',city:'Alwar',title:'Photographer for Events',cat:'Photography',desc:'Hotel events, weddings, corporate functions ke liye photographer. Alwar & Sariska.',budget:'₹3000/event',urgency:'Flexible',phone:'9413103003'},
  {name:'Alwar Cooperative',city:'Bhiwadi',title:'Tally & Accounts Expert',cat:'Business',desc:'GST filing, daily accounts, Tally ERP 9. Bhiwadi office. Full time preferred.',budget:'₹12000/month',urgency:'Normal',phone:'9413104004'},
  {name:'Neemrana Factory Owner',city:'Neemrana',title:'Industrial English Trainer',cat:'Language',desc:'Factory workers ke liye basic English & communication training. Batch classes.',budget:'₹5000/batch',urgency:'Normal',phone:'9413105005'},
  {name:'Alwar Mahila Mandal',city:'Alwar',title:'Yoga Instructor for Ladies',cat:'Fitness',desc:'Mahila mandal ke liye weekly 3 din yoga classes. Morning slot. Alwar city.',budget:'₹4000/month',urgency:'Normal',phone:'9413106006'},
  {name:'Local Caterer Alwar',city:'Alwar',title:'Cooking Help for Events',cat:'Cooking',desc:'Shaadi, birthday functions ke liye cooking help chahiye. Rajasthani khana expertise.',budget:'₹500/day',urgency:'Urgent',phone:'9413107007'},
  {name:'Bhiwadi Textile Mill',city:'Bhiwadi',title:'Logo & Branding Design',cat:'Creative',desc:'Naye textile brand ke liye logo, visiting card, letterhead design.',budget:'₹2000',urgency:'Urgent',phone:'9413108008'},
  {name:'Coaching Center Alwar',city:'Alwar',title:'REET Hindi Teacher',cat:'Academic',desc:'REET & Patwari Hindi preparation ke liye teacher chahiye. Evening batch. Alwar.',budget:'₹8000/month',urgency:'Normal',phone:'9413109009'},
  {name:'Wedding Planner Alwar',city:'Alwar',title:'Mehndi Artist Required',cat:'Creative',desc:'Shaadi season mein mehndi artist chahiye. Alwar & surrounding villages. Multiple events.',budget:'₹1500/event',urgency:'Urgent',phone:'9413110010'},
  {name:'Alwar Dairy',city:'Alwar',title:'Social Media Manager',cat:'Business',desc:'Facebook & WhatsApp par daily updates, promotions. Alwar local dairy brand.',budget:'₹2000/month',urgency:'Normal',phone:'9413111011'},
  {name:'Raj Driving School',city:'Alwar',title:'Driving Instructor Required',cat:'Fitness',desc:'4-wheeler driving instructor chahiye. Alwar mein license training center.',budget:'₹15000/month',urgency:'Normal',phone:'9413112012'},
];

let skills=[],jobs=[],nextSkillId=1,nextJobId=1;

alwarStudents.forEach((s,i)=>{
  const email=`alwar${i+1}@skillswap.com`;
  skills.push({id:nextSkillId++,name:s.name,email,city:s.city,skill:s.skill,cat:s.cat,desc:s.desc,price:s.price,rating:s.rating,reviews:s.reviews,status:'active',premium:i<5,tags:['alwar','local'],createdAt:Date.now()-i*1800000,isLocal:true,phone:s.phone});
  if(!users.find(u=>u.email===email))users.push({email,pass:'pass123',name:s.name,city:s.city,role:'student',premium:i<5,status:'active',phone:s.phone});
});

const sNames=['Aarav Sharma','Priya Singh','Rohan Verma','Ananya Gupta','Vikram Patel','Sneha Joshi','Arjun Mehta','Kavya Reddy','Dev Kumar','Meera Nair','Ishaan Tyagi','Pooja Menon','Rahul Bose','Divya Iyer','Sameer Khan','Riya Desai','Aditya Tiwari','Nisha Pillai','Karan Malhotra','Simran Kaur'];
const sCities=['Delhi','Mumbai','Bangalore','Hyderabad','Chennai','Pune','Kolkata','Jaipur','Ahmedabad','Noida'];
const sSkills=[
  {skill:'Math Tutoring (Class 9-12)',cat:'Academic',desc:'Board exam prep, CBSE/ICSE Math.',price:'₹150/hr'},
  {skill:'Python Programming Help',cat:'Tech',desc:'Python basics to advanced, Django, Flask.',price:'₹200/hr'},
  {skill:'Logo & Brand Design',cat:'Creative',desc:'Professional logos using Adobe & Canva.',price:'₹350/project'},
  {skill:'English Speaking Coach',cat:'Language',desc:'Spoken English, pronunciation, IELTS prep.',price:'₹120/hr'},
  {skill:'Guitar Lessons',cat:'Music',desc:'Beginner to intermediate. Bollywood songs.',price:'₹250/hr'},
  {skill:'Yoga & Meditation',cat:'Fitness',desc:'Morning yoga, breathing & mindfulness.',price:'₹100/session'},
  {skill:'Social Media Marketing',cat:'Business',desc:'Instagram, YouTube growth strategy.',price:'₹500/month'},
  {skill:'Wedding Photography',cat:'Photography',desc:'Event & portrait photography. DSLR.',price:'₹3000/event'},
  {skill:'Home-made Tiffin Service',cat:'Cooking',desc:'Healthy homemade lunch tiffin.',price:'₹80/meal'},
  {skill:'Web Development',cat:'Tech',desc:'React, HTML, CSS, Node.js websites.',price:'₹5000/site'},
];
for(let i=0;i<200;i++){
  const name=sNames[i%sNames.length]+(i>=sNames.length?' '+(Math.floor(i/sNames.length)+1):'');
  const city=sCities[i%sCities.length];
  const sk=sSkills[i%sSkills.length];
  const email=`student${i+1}@skillswap.com`;
  skills.push({id:nextSkillId++,name,email,city,skill:sk.skill,cat:sk.cat,desc:sk.desc,price:sk.price,rating:(4.2+(Math.random()*0.8)).toFixed(1)*1,reviews:Math.floor(Math.random()*30)+1,status:'active',premium:i<10,tags:['online'],createdAt:Date.now()-(i+25)*3600000,isLocal:false,phone:'98765'+String(i).padStart(5,'0')});
}

alwarJobs.forEach((j,i)=>{
  const email=`alwarjob${i+1}@skillswap.com`;
  jobs.push({id:nextJobId++,name:j.name,email,city:j.city,title:j.title,cat:j.cat,desc:j.desc,budget:j.budget,urgency:j.urgency,status:'active',premium:i<3,postedAt:Date.now()-i*3600000,isLocal:true,phone:j.phone});
  if(!users.find(u=>u.email===email))users.push({email,pass:'pass123',name:j.name,city:j.city,role:'client',premium:i<3,status:'active',phone:j.phone});
});

const cJobs=[
  {title:'Math Tutor Chahiye Class 10',cat:'Academic',desc:'Meri beti ke liye Class 10 Math tutor chahiye.',budget:'₹150/hr',urgency:'Normal'},
  {title:'Website Design Karni Hai',cat:'Tech',desc:'Small business ke liye 5 page website.',budget:'₹5000',urgency:'Urgent'},
  {title:'Logo Design Chahiye',cat:'Creative',desc:'Naye restaurant ke liye professional logo.',budget:'₹500',urgency:'Normal'},
  {title:'English Tutor for Interview Prep',cat:'Language',desc:'Job interview ke liye spoken English.',budget:'₹120/hr',urgency:'Urgent'},
  {title:'Yoga Instructor Chahiye',cat:'Fitness',desc:'Office mein weekly yoga sessions.',budget:'₹2000/session',urgency:'Normal'},
];
const cNames=['Rahul Enterprises','Tech Solutions','Sharma Coaching','Mumbai Digital','Delhi Startups'];
for(let i=0;i<100;i++){
  const jb=cJobs[i%cJobs.length];
  const email=`client${i+1}@skillswap.com`;
  jobs.push({id:nextJobId++,name:cNames[i%cNames.length],email,city:sCities[i%sCities.length],title:jb.title,cat:jb.cat,desc:jb.desc,budget:jb.budget,urgency:jb.urgency,status:'active',premium:i<5,postedAt:Date.now()-(i+15)*7200000,isLocal:false,phone:'98764'+String(i).padStart(5,'0')});
}

let currentUser=null,currentRole='student',currentCat='All',currentLocFilter='Sabhi',contactTarget=null,contactType='skill',activeTab='browse',currentContactMethod='whatsapp';
let applications=[];
let selectedPayMethod='phonepay';

// ─── AUTH ───
let selectedRole='student';
function pickRole(r){
  selectedRole=r;
  document.getElementById('rcStudent').className='role-card'+(r==='student'?' sel':'');
  document.getElementById('rcClient').className='role-card'+(r==='client'?' sel client-sel':'');
  const isC=r==='client';
  document.getElementById('loginBtn').className='auth-btn'+(isC?' cb':'');
  document.getElementById('signupBtn').className='auth-btn'+(isC?' cb':'');
  document.getElementById('tabLogin').className='auth-tab active'+(isC?' ct':'');
}
function switchTab(t){
  document.getElementById('loginForm').style.display=t==='login'?'block':'none';
  document.getElementById('signupForm').style.display=t==='signup'?'block':'none';
  document.getElementById('tabLogin').className='auth-tab'+(t==='login'?' active'+(selectedRole==='client'?' ct':''):'');
  document.getElementById('tabSignup').className='auth-tab'+(t==='signup'?' active'+(selectedRole==='client'?' ct':''):'');
  document.getElementById('authErr').textContent='';
}
function loadSavedUsers(){
  try{const saved=JSON.parse(localStorage.getItem('ss_users')||'[]');saved.forEach(u=>{if(!users.find(x=>x.email.toLowerCase()===u.email.toLowerCase()))users.push(u);});}catch(e){}
}
function saveNewUser(u){
  try{let saved=JSON.parse(localStorage.getItem('ss_users')||'[]');saved.push(u);localStorage.setItem('ss_users',JSON.stringify(saved));}catch(e){}
}
function doLogin(){
  const e=v('lEmail'),p=v('lPass');
  if(!e||!p){setErr('Sab fields bharo');return;}
  loadSavedUsers();
  const u=users.find(x=>x.email.toLowerCase()===e.toLowerCase()&&x.pass===p);
  if(!u){setErr('Email ya password galat hai');return;}
  if(u.status==='banned'){setErr('Account banned hai.');return;}
  currentUser=u;currentRole=u.role;showApp();
}
function doSignup(){
  const n=v('sName'),e=v('sEmail'),p=v('sPass'),ph=v('sPhone');
  const cityEl=document.getElementById('sCity');
  const c=cityEl?cityEl.value:'';
  if(!n||!e||!p||!c){setErr('Sab fields bharo');return;}
  if(p.length<6){setErr('Password 6+ characters');return;}
  loadSavedUsers();
  if(users.find(x=>x.email.toLowerCase()===e.toLowerCase())){setErr('Email pehle se registered hai');return;}
  const u={email:e.toLowerCase(),pass:p,name:n,city:c,phone:ph,role:selectedRole,premium:false,status:'active',joined:new Date().toLocaleDateString('en-IN')};
  users.push(u);saveNewUser(u);currentUser=u;currentRole=selectedRole;showApp();
}
function doLogout(){currentUser=null;document.getElementById('appScreen').style.display='none';document.getElementById('authScreen').style.display='flex';}
function setErr(m){document.getElementById('authErr').textContent=m;}
function isNearby(city){return NEARBY_CITIES.includes(city);}
function isRajasthan(city){return NEARBY_CITIES.includes(city)||RAJASTHAN_CITIES.includes(city);}

function showApp(){
  document.getElementById('authScreen').style.display='none';
  document.getElementById('appScreen').style.display='block';
  const isAdmin=currentRole==='admin',isClient=currentRole==='client';
  const hdr=document.getElementById('appHeader');
  hdr.className='app-header '+(isAdmin?'ah':isClient?'ch':'sh');
  document.getElementById('headerTitle').textContent=isAdmin?'👑 SkillSwap Admin':isClient?'💼 SkillSwap Client':'🎓 SkillSwap Student';
  document.getElementById('headerSub').textContent=isAdmin?'Platform Control Panel':isClient?'Kaam Post Karo, Talent Dhundho':'Skills Offer Karo, Paise Kamao';
  document.getElementById('headerUser').textContent=currentUser.name.split(' ')[0]+(currentUser.premium?' ⭐':'')+(isAdmin?' 👑':'');
  document.getElementById('headerLoc').textContent=currentUser.city||'Alwar';
  document.getElementById('postBtn').textContent=isClient?'+ Job Post':'+ Skill Post';
  document.getElementById('postBtn').className='hbtn '+(isClient?'c':'s');
  document.getElementById('premBtn').style.display=isAdmin?'none':'inline-block';
  document.getElementById('fabBtn').className='fab '+(isClient?'c':'s');
  const nbSkills=skills.filter(s=>isNearby(s.city)&&s.status==='active').length;
  const nbJobs=jobs.filter(j=>isNearby(j.city)&&j.status==='active').length;
  document.getElementById('nearbyCount').textContent=nbSkills+' Students';
  document.getElementById('nearbyJobCount').textContent=nbJobs+' Jobs';
  document.getElementById('locBanner').style.display=isAdmin?'none':'flex';
  buildTabs();activeTab='browse';currentLocFilter='Mere Paas';renderPage();
}

function buildTabs(){
  const isAdmin=currentRole==='admin',isClient=currentRole==='client';
  const cls=isAdmin?'a':isClient?'c':'s';
  let tabs=[];
  if(isAdmin)tabs=[{id:'users',label:'👥 Users'},{id:'skills',label:'🎓 Skills'},{id:'jobs',label:'💼 Jobs'},{id:'revenue',label:'💰 Revenue'}];
  else if(isClient)tabs=[{id:'browse',label:'🔍 Students Dhundho'},{id:'myjobs',label:'📋 Meri Jobs'},{id:'received',label:'📩 Applications'},{id:'post',label:'➕ Job Post'}];
  else tabs=[{id:'browse',label:'🔍 Skills Browse'},{id:'myskills',label:'📋 Meri Skills'},{id:'jobs',label:'💼 Jobs Board'},{id:'applied',label:'📩 Applications'},{id:'post',label:'➕ Skill Post'}];
  document.getElementById('mainTabs').innerHTML=tabs.map(t=>`<button class="mtab" id="tab_${t.id}" onclick="switchMainTab('${t.id}')">${t.label}</button>`).join('');
  setActiveTab(activeTab||tabs[0].id);
}
function switchMainTab(id){
  if(id==='post'){openPostModal();return;}
  activeTab=id;setActiveTab(id);buildLocationFilters();renderPage();
}
function setActiveTab(id){
  const cls=currentRole==='admin'?'a':currentRole==='client'?'c':'s';
  document.querySelectorAll('.mtab').forEach(b=>b.className='mtab');
  const el=document.getElementById('tab_'+id);
  if(el)el.className=`mtab active ${cls}`;
}
function renderPage(){
  const isAdmin=currentRole==='admin';
  document.getElementById('mainContent').style.display=isAdmin?'none':'block';
  document.getElementById('adminPanel').style.display=isAdmin?'block':'none';
  document.getElementById('filtersBar').style.display=isAdmin?'none':'flex';
  document.getElementById('fabBtn').style.display=isAdmin?'none':'flex';
  if(isAdmin){renderAdmin();return;}
  buildFilters();buildLocationFilters();renderCards();
}
function buildFilters(){
  const isClient=currentRole==='client',cls=isClient?'cf':'';
  document.getElementById('filterBtns').innerHTML=studentCats.map(c=>`<button class="fbtn${c===currentCat?' active '+cls:''}" onclick="filterCat('${c}',this)">${c}</button>`).join('');
}
function buildLocationFilters(){
  const showLoc=(activeTab==='browse'||activeTab==='jobs');
  document.getElementById('locationFilterRow').style.display=showLoc?'flex':'none';
  if(!showLoc)return;
  document.getElementById('locFilterBtns').innerHTML=ALL_LOCATION_FILTERS.map(l=>`<button class="fbtn${l===currentLocFilter?' loc-active':''}" onclick="filterLoc('${l}',this)">📍 ${l}</button>`).join('');
}
function filterCat(cat,btn){
  currentCat=cat;
  document.querySelectorAll('.fbtn:not([onclick*="filterLoc"])').forEach(b=>{b.classList.remove('active','cf');});
  btn.classList.add('active');if(currentRole==='client')btn.classList.add('cf');renderCards();
}
function filterLoc(loc,btn){
  currentLocFilter=loc;
  document.querySelectorAll('#locFilterBtns .fbtn').forEach(b=>b.classList.remove('loc-active'));
  btn.classList.add('loc-active');renderCards();
}
function applyLocFilter(items,cityKey){
  if(currentLocFilter==='Mere Paas')return items.filter(x=>isNearby(x[cityKey]));
  if(currentLocFilter==='Alwar Zila')return items.filter(x=>NEARBY_CITIES.includes(x[cityKey]));
  if(currentLocFilter==='Rajasthan')return items.filter(x=>isRajasthan(x[cityKey]));
  return items;
}
function initials(n){return n.split(' ').map(w=>w[0]).join('').toUpperCase().slice(0,2);}
function stars(r){return'★'.repeat(Math.round(r))+'☆'.repeat(5-Math.round(r));}
function locLabel(city){return NEARBY_CITIES.includes(city)?'📍 '+city:city;}
function cleanPhone(p){if(!p)return '';return p.replace(/\D/g,'');}
function makeWALink(phone,msg){const p=cleanPhone(phone);if(!p)return null;return`https://wa.me/91${p}?text=${encodeURIComponent(msg)}`;}

function renderCards(){
  const q=(document.getElementById('searchInput')||{}).value||'',ql=q.toLowerCase();
  const grid=document.getElementById('cardsGrid');
  const isClient=currentRole==='client',tab=activeTab;
  const nearbyStrip=document.getElementById('nearbyStrip');

  function contactBtns(type,id,name,phone,isOwn){
    if(isOwn)return '<span style="font-size:0.69rem;color:#10b981;font-weight:600">✓ Yours</span>';
    const hasPhone=phone&&cleanPhone(phone);
    return`<div class="contact-btns">
      ${hasPhone?`<button class="wabtn" onclick="openContact('${type}',${id})"><i class="ti ti-brand-whatsapp" style="font-size:13px"></i> WhatsApp</button>`:''}
      <button class="abtn ${isClient?'c':'s'}" onclick="openContact('${type}',${id})">Contact</button>
    </div>`;
  }

  if(tab==='browse'){
    nearbyStrip.style.display='block';
    const nearbyData=skills.filter(s=>s.status==='active'&&isNearby(s.city)).slice(0,12);
    document.getElementById('nearbyScroll').innerHTML=nearbyData.map((s,i)=>`
      <div class="ncard" onclick="openContact('skill',${s.id})">
        <div style="display:flex;align-items:center;gap:0.4rem;margin-bottom:0.3rem">
          <div class="av" style="background:${avColors[i%avColors.length]};width:26px;height:26px;font-size:0.65rem">${initials(s.name)}</div>
          <div class="nname">${s.name}</div>
        </div>
        <div class="nskill">${s.skill}</div>
        <div class="ncity">📍 ${s.city}</div>
        <div class="nprice">${s.price}</div>
        ${s.phone?`<div style="font-size:0.62rem;color:#25D366;font-weight:600;margin-top:2px">💬 WhatsApp Available</div>`:''}
      </div>`).join('');

    document.getElementById('statsRow').innerHTML=`
      <div class="sc"><div class="n">${skills.filter(s=>s.status==='active').length}</div><div class="l">Total Skills</div></div>
      <div class="sc"><div class="n g">${skills.filter(s=>s.status==='active'&&isNearby(s.city)).length}</div><div class="l">📍 Aas Paas</div></div>
      <div class="sc"><div class="n" style="color:#25D366">${skills.filter(s=>s.phone).length}</div><div class="l">WhatsApp</div></div>
      <div class="sc"><div class="n" style="color:#06b6d4">${skills.filter(s=>s.skill.toLowerCase().includes('online')||s.desc.toLowerCase().includes('online')).length}</div><div class="l">Online</div></div>`;

    let locTitle='Sabhi Skills';
    if(currentLocFilter==='Mere Paas')locTitle='Alwar & Aas Paas ke Skills';
    else if(currentLocFilter==='Alwar Zila')locTitle='Alwar Zile ke Skills';
    else if(currentLocFilter==='Rajasthan')locTitle='Rajasthan ke Skills';
    document.getElementById('gridTitle').innerHTML=`${locTitle} <span class="loc-tag">📍 ${currentLocFilter}</span>`;

    let data=skills.filter(s=>{
      if(s.status!=='active')return false;
      if(currentCat!=='All'){
        if(currentCat==='Tuition'){if(!s.skill.toLowerCase().includes('tutor')&&!s.skill.toLowerCase().includes('tuition')&&!s.skill.toLowerCase().includes('coaching')&&!s.skill.toLowerCase().includes('class')&&!s.skill.toLowerCase().includes('teacher'))return false;}
        else if(currentCat==='Online'){if(!s.skill.toLowerCase().includes('online')&&!s.desc.toLowerCase().includes('online'))return false;}
        else if(s.cat!==currentCat)return false;
      }
      if(ql&&!s.skill.toLowerCase().includes(ql)&&!s.name.toLowerCase().includes(ql)&&!s.city.toLowerCase().includes(ql)&&!s.desc.toLowerCase().includes(ql))return false;
      return true;
    });
    data=applyLocFilter(data,'city');
    data.sort((a,b)=>(b.isLocal?2:0)+(b.premium?1:0)-(a.isLocal?2:0)-(a.premium?1:0));
    const own=currentUser;
    grid.innerHTML=data.slice(0,60).map((s,i)=>{
      const cc=catColors[s.cat]||'#888',nearby=isNearby(s.city),isOwn=own&&s.email===own.email;
      return`<div class="card${s.premium?' prem':nearby?' nearby':''}">
        ${isOwn?'<span class="cbadge cb-own">Your Post</span>':nearby?'<span class="cbadge cb-near">📍 Near</span>':s.premium?'<span class="cbadge cb-p">⭐ Premium</span>':''}
        <div class="ctop">
          <div class="av" style="background:${avColors[i%avColors.length]}">${initials(s.name)}</div>
          <div><div class="rrow">${stars(s.rating)} ${s.rating} (${s.reviews})</div><h3>${s.skill}</h3><div class="sub">${s.name} · ${locLabel(s.city)}</div></div>
        </div>
        <span class="bdg" style="background:${cc}22;color:${cc}">${s.cat}</span>
        ${nearby?'<span class="bdg" style="background:#d1fae5;color:#065f46">Alwar Area</span>':''}
        ${s.phone?'<span class="bdg" style="background:#dcfce7;color:#166534">💬 WhatsApp</span>':''}
        <p class="desc">${s.desc}</p>
        <div class="cfoot"><span class="ptag">${s.price}</span>${contactBtns('skill',s.id,s.name,s.phone,isOwn)}</div>
      </div>`;
    }).join('')||'<div class="empty">Koi skill nahi mili 🔍<br><small>Filter change karein ya "Sabhi" select karein</small></div>';
  }

  else if(tab==='myskills'){
    nearbyStrip.style.display='none';
    document.getElementById('statsRow').innerHTML='';
    document.getElementById('gridTitle').innerHTML='Meri Skills & Services';
    let data=skills.filter(s=>s.email===currentUser.email);
    grid.innerHTML=data.length?data.map((s,i)=>{
      const cc=catColors[s.cat]||'#888';
      return`<div class="card${s.premium?' prem':''}">
        <span class="cbadge cb-own">Your Post</span>
        <div class="ctop"><div class="av" style="background:${avColors[i%avColors.length]}">${initials(s.name)}</div>
        <div><h3>${s.skill}</h3><div class="sub">${s.city}</div></div></div>
        <span class="bdg" style="background:${cc}22;color:${cc}">${s.cat}</span>
        <p class="desc">${s.desc}</p>
        <div class="cfoot"><span class="ptag">${s.price}</span><button class="abtn" style="background:#ef4444;color:white" onclick="deleteSkill(${s.id})">Delete</button></div>
      </div>`;
    }).join(''):'<div class="empty">Abhi koi skill post nahi ki. + Post Skill karo! 🚀</div>';
  }

  else if(tab==='jobs'){
    nearbyStrip.style.display='none';
    document.getElementById('statsRow').innerHTML=`
      <div class="sc"><div class="n o">${jobs.filter(j=>j.status==='active').length}</div><div class="l">Total Jobs</div></div>
      <div class="sc"><div class="n g">${jobs.filter(j=>j.status==='active'&&isNearby(j.city)).length}</div><div class="l">Alwar Area</div></div>
      <div class="sc"><div class="n r">${jobs.filter(j=>j.urgency==='Urgent'&&j.status==='active').length}</div><div class="l">Urgent Jobs</div></div>
      <div class="sc"><div class="n" style="color:#25D366">${jobs.filter(j=>j.phone).length}</div><div class="l">WhatsApp</div></div>`;
    let locTitle='Sabhi Jobs';
    if(currentLocFilter==='Mere Paas')locTitle='Alwar Area Jobs';
    else if(currentLocFilter==='Alwar Zila')locTitle='Alwar Zila Jobs';
    else if(currentLocFilter==='Rajasthan')locTitle='Rajasthan Jobs';
    document.getElementById('gridTitle').innerHTML=`${locTitle} — Apply Karo! <span class="loc-tag">📍 ${currentLocFilter}</span>`;
    let data=jobs.filter(j=>j.status==='active'&&(currentCat==='All'||j.cat===currentCat)&&(!ql||j.title.toLowerCase().includes(ql)||j.name.toLowerCase().includes(ql)||j.city.toLowerCase().includes(ql)));
    data=applyLocFilter(data,'city');
    data.sort((a,b)=>(b.isLocal?2:0)+(b.urgency==='Urgent'?1:0)-(a.isLocal?2:0)-(a.urgency==='Urgent'?1:0));
    grid.innerHTML=data.slice(0,60).map((j,i)=>{
      const cc=catColors[j.cat]||'#888',nearby=isNearby(j.city);
      const isOwn=currentUser&&j.email===currentUser.email;
      return`<div class="card${j.urgency==='Urgent'?' urgent':nearby?' nearby':''}">
        ${j.urgency==='Urgent'?'<span class="cbadge cb-u">🔥 Urgent</span>':nearby?'<span class="cbadge cb-near">📍 Near</span>':j.premium?'<span class="cbadge cb-p">⭐ Featured</span>':''}
        <div class="ctop"><div class="av" style="background:${avColors[i%avColors.length]}">${initials(j.name)}</div>
        <div><h3>${j.title}</h3><div class="sub">${j.name} · ${locLabel(j.city)}</div></div></div>
        <span class="bdg" style="background:${cc}22;color:${cc}">${j.cat}</span>
        <span class="bdg" style="background:#f0f4ff;color:#6c63ff">${j.urgency}</span>
        ${nearby?'<span class="bdg" style="background:#d1fae5;color:#065f46">Alwar Area</span>':''}
        ${j.phone?'<span class="bdg" style="background:#dcfce7;color:#166534">💬 WhatsApp</span>':''}
        <p class="desc">${j.desc}</p>
        <div class="cfoot"><span class="ptag o">${j.budget}</span>${contactBtns('job',j.id,j.name,j.phone,isOwn)}</div>
      </div>`;
    }).join('')||'<div class="empty">Koi job nahi mili</div>';
  }

  else if(tab==='myjobs'){
    nearbyStrip.style.display='none';
    document.getElementById('statsRow').innerHTML='';
    document.getElementById('gridTitle').innerHTML='Meri Posted Jobs';
    let data=jobs.filter(j=>j.email===currentUser.email);
    grid.innerHTML=data.length?data.map((j,i)=>{
      const cc=catColors[j.cat]||'#888';
      return`<div class="card${j.urgency==='Urgent'?' urgent':''}">
        ${j.urgency==='Urgent'?'<span class="cbadge cb-u">🔥 Urgent</span>':''}
        <div class="ctop"><div class="av" style="background:${avColors[i%avColors.length]}">${initials(j.name)}</div>
        <div><h3>${j.title}</h3><div class="sub">${j.city} · ${j.urgency}</div></div></div>
        <span class="bdg" style="background:${cc}22;color:${cc}">${j.cat}</span>
        <p class="desc">${j.desc}</p>
        <div class="cfoot"><span class="ptag o">${j.budget}</span><button class="abtn" style="background:#ef4444;color:white" onclick="deleteJob(${j.id})">Delete</button></div>
      </div>`;
    }).join(''):'<div class="empty">Abhi koi job post nahi ki. 💼</div>';
  }

  else if(tab==='applied'){
    nearbyStrip.style.display='none';
    document.getElementById('statsRow').innerHTML=`
      <div class="sc"><div class="n">${applications.length}</div><div class="l">Total</div></div>
      <div class="sc"><div class="n g">${applications.filter(a=>a.type==='job').length}</div><div class="l">Jobs Apply</div></div>
      <div class="sc"><div class="n" style="color:#25D366">${applications.filter(a=>a.method==='whatsapp').length}</div><div class="l">WhatsApp</div></div>
      <div class="sc"><div class="n o">${applications.filter(a=>a.type==='skill').length}</div><div class="l">Skill Contact</div></div>`;
    document.getElementById('gridTitle').innerHTML='📩 Meri Applications & Contacts';
    if(!applications.length){
      grid.innerHTML='<div class="empty">Abhi koi application nahi di.<br><small>Jobs ya Skills mein Contact/Apply karo!</small></div>';
    } else {
      grid.innerHTML=applications.slice().reverse().map((a,i)=>{
        const bc=a.type==='job'?'#f97316':'#6c63ff';
        const methodBadge=a.method==='whatsapp'?'<span class="bdg" style="background:#dcfce7;color:#166534">💬 WhatsApp</span>':'<span class="bdg" style="background:#f0f4ff;color:#6c63ff">📩 Site Msg</span>';
        return`<div class="card" style="border-left:3px solid ${bc}">
          <div class="ctop">
            <div class="av" style="background:${bc}">${a.type==='job'?'💼':'🎓'}</div>
            <div><h3>${a.targetTitle}</h3><div class="sub">${a.targetName} · 📍 ${a.targetCity}</div></div>
          </div>
          ${methodBadge}
          <span class="bdg" style="background:#d1fae5;color:#065f46">✅ ${a.status}</span>
          <p class="desc" style="background:#f8f9ff;border-radius:8px;padding:0.5rem;border-left:3px solid ${bc}22">"${a.message}"</p>
          <div class="cfoot">
            <span class="ptag" style="color:${bc}">${a.targetPrice}</span>
            <span style="font-size:0.65rem;color:#aaa">${a.appliedAt}</span>
          </div>
        </div>`;
      }).join('');
    }
  }

  else if(tab==='received'){
    nearbyStrip.style.display='none';
    document.getElementById('statsRow').innerHTML=`
      <div class="sc"><div class="n o">12</div><div class="l">Applications</div></div>
      <div class="sc"><div class="n g">5</div><div class="l">New Today</div></div>
      <div class="sc"><div class="n" style="color:#25D366">8</div><div class="l">WhatsApp</div></div>
      <div class="sc"><div class="n">3</div><div class="l">Shortlisted</div></div>`;
    document.getElementById('gridTitle').innerHTML='📩 Aapke Jobs Par Aayi Applications';
    const demoApps=[
      {name:'Rahul Sharma',city:'Alwar',skill:'Math & Science Tutor',msg:'Main aapke bachon ko padhane mein interested hoon.',time:'2 ghante pehle',phone:'9414101001'},
      {name:'Priya Agarwal',city:'Bhiwadi',skill:'English Speaking Coach',msg:'Trial class free mein de sakti hoon.',time:'4 ghante pehle',phone:'9414102002'},
      {name:'Deepak Gurjar',city:'Alwar',skill:'Computer Basics Trainer',msg:'Ghar par aake tuition de sakta hoon.',time:'Kal',phone:'9414103003'},
    ];
    grid.innerHTML=demoApps.map((a,i)=>`
      <div class="card" style="border-left:3px solid #6c63ff">
        <span class="cbadge cb-new">New</span>
        <div class="ctop">
          <div class="av" style="background:${avColors[i%avColors.length]}">${initials(a.name)}</div>
          <div><h3>${a.name}</h3><div class="sub">${a.skill} · 📍 ${a.city}</div></div>
        </div>
        <p class="desc" style="background:#f8f9ff;border-radius:8px;padding:0.5rem">"${a.msg}"</p>
        <div class="cfoot">
          <span style="font-size:0.65rem;color:#aaa">${a.time}</span>
          <div style="display:flex;gap:0.3rem">
            <button class="wabtn" onclick="directWhatsApp('${a.phone}','Namaste, aapki application dekhi. Kya aap available hain?')"><i class="ti ti-brand-whatsapp" style="font-size:13px"></i> WhatsApp</button>
            <button class="abtn" style="background:#ef4444" onclick="showToast('Reject kar diya')">✕</button>
          </div>
        </div>
      </div>`).join('');
  }
}

// ─── POST ───
function openPostModal(){
  if(currentRole==='client')openModal('postJob');
  else openModal('postSkill');
}
function postSkill(){
  const sk=v('pSkill'),cat=v('pCat'),desc=v('pDesc'),price=v('pPrice'),phone=v('pPhone');
  const city=document.getElementById('pCitySkill').value||currentUser.city;
  if(!sk||!cat||!desc||!price){showToast('Sab fields bharo!');return;}
  const finalPhone=phone||currentUser.phone||'';
  const isLoc=NEARBY_CITIES.includes(city);
  skills.unshift({id:nextSkillId++,name:currentUser.name,email:currentUser.email,city,skill:sk,cat,desc,price,rating:5.0,reviews:0,status:'active',premium:currentUser.premium,tags:[],createdAt:Date.now(),isLocal:isLoc,phone:finalPhone});
  // update user phone
  if(phone){currentUser.phone=phone;const u=users.find(x=>x.email===currentUser.email);if(u)u.phone=phone;}
  closeModal('postSkill');
  ['pSkill','pDesc','pPrice','pTags','pPhone'].forEach(id=>{const el=document.getElementById(id);if(el)el.value='';});
  document.getElementById('pCat').value='';
  activeTab='myskills';setActiveTab('myskills');renderPage();
  showToast('🎉 Skill live ho gayi!');
}
function postJob(){
  const t=v('jTitle'),cat=v('jCat'),desc=v('jDesc'),budget=v('jBudget'),urg=v('jUrgency')||'Normal',phone=v('jPhone');
  const city=document.getElementById('jCityJob').value||currentUser.city;
  if(!t||!cat||!desc||!budget){showToast('Sab fields bharo!');return;}
  const finalPhone=phone||currentUser.phone||'';
  const isLoc=NEARBY_CITIES.includes(city);
  jobs.unshift({id:nextJobId++,name:currentUser.name,email:currentUser.email,city,title:t,cat,desc,budget,urgency:urg,status:'active',premium:currentUser.premium,postedAt:Date.now(),isLocal:isLoc,phone:finalPhone});
  if(phone){currentUser.phone=phone;const u=users.find(x=>x.email===currentUser.email);if(u)u.phone=phone;}
  closeModal('postJob');
  ['jTitle','jDesc','jBudget','jPhone'].forEach(id=>{const el=document.getElementById(id);if(el)el.value='';});
  document.getElementById('jCat').value='';
  activeTab='myjobs';setActiveTab('myjobs');renderPage();
  showToast('💼 Job live ho gayi!');
}
function deleteSkill(id){skills=skills.filter(s=>s.id!==id);renderCards();showToast('Skill delete ho gayi');}
function deleteJob(id){jobs=jobs.filter(j=>j.id!==id);renderCards();showToast('Job delete ho gayi');}

// ─── CONTACT (UPGRADED WITH WHATSAPP) ───
function openContact(type,id){
  contactType=type;
  if(type==='skill'){
    contactTarget=skills.find(s=>s.id===id);
    if(!contactTarget)return;
    document.getElementById('contactTitle').textContent='Contact Karo';
    document.getElementById('contactCard').style.borderColor='#6c63ff';
    document.getElementById('ctName').textContent=contactTarget.name;
    document.getElementById('ctSkill').textContent=contactTarget.skill;
    document.getElementById('ctPrice').textContent=contactTarget.price;
    document.getElementById('ctCity').textContent='📍 '+contactTarget.city;
    document.getElementById('ctRating').textContent=stars(contactTarget.rating)+' '+contactTarget.rating;
    document.getElementById('contactSendBtn').className='mbtn s';
  } else {
    contactTarget=jobs.find(j=>j.id===id);
    if(!contactTarget)return;
    document.getElementById('contactTitle').textContent='Apply Karo';
    document.getElementById('contactCard').style.borderColor='#f97316';
    document.getElementById('ctName').textContent=contactTarget.name;
    document.getElementById('ctSkill').textContent=contactTarget.title;
    document.getElementById('ctPrice').textContent=contactTarget.budget;
    document.getElementById('ctCity').textContent='📍 '+contactTarget.city;
    document.getElementById('ctRating').textContent=contactTarget.urgency;
    document.getElementById('contactSendBtn').className='mbtn c';
  }
  // Reset sections
  document.getElementById('waSection').style.display='none';
  document.getElementById('msgSection').style.display='none';
  document.getElementById('noPhoneWarning').style.display='none';
  document.getElementById('waOptBtn').style.border='2px solid #e2e8f0';
  document.getElementById('msgOptBtn').style.border='2px solid #e2e8f0';

  // Set WhatsApp details
  const phone=contactTarget.phone;
  const hasPhone=phone&&cleanPhone(phone);
  if(!hasPhone){
    document.getElementById('waOptBtn').style.opacity='0.5';
    document.getElementById('noPhoneWarning').style.display='block';
  } else {
    document.getElementById('waOptBtn').style.opacity='1';
  }
  document.getElementById('cMsg').value='';
  document.getElementById('waMsg').value=type==='skill'
    ?`Namaste ${contactTarget.name} ji! 🙏\nAapki skill "${contactTarget.skill}" dekhi — ${contactTarget.price}. Kya aap available hain?\n\nSkillSwap par mila!`
    :`Namaste! 🙏\nAapka job post "${contactTarget.title}" dekha — Budget: ${contactTarget.budget}.\nMain interested hoon. Kya baat kar sakte hain?\n\nSkillSwap par mila!`;
  openModal('contact');
}

function chooseContactType(method){
  currentContactMethod=method;
  document.getElementById('waOptBtn').style.border=method==='whatsapp'?'2px solid #25D366':'2px solid #e2e8f0';
  document.getElementById('msgOptBtn').style.border=method==='message'?'2px solid #6c63ff':'2px solid #e2e8f0';

  const phone=contactTarget?contactTarget.phone:'';
  const hasPhone=phone&&cleanPhone(phone);

  if(method==='whatsapp'){
    if(!hasPhone){
      document.getElementById('noPhoneWarning').style.display='block';
      document.getElementById('waSection').style.display='none';
      document.getElementById('msgSection').style.display='none';
      return;
    }
    document.getElementById('waNumber').textContent=phone;
    document.getElementById('waName').textContent=contactTarget.name;
    document.getElementById('waSection').style.display='block';
    document.getElementById('msgSection').style.display='none';
    document.getElementById('noPhoneWarning').style.display='none';
  } else {
    document.getElementById('msgSection').style.display='block';
    document.getElementById('waSection').style.display='none';
    document.getElementById('noPhoneWarning').style.display='none';
  }
}

function openWhatsApp(){
  const phone=contactTarget.phone;
  const msg=document.getElementById('waMsg').value;
  if(!msg.trim()){showToast('Message likhо!');return;}
  const link=makeWALink(phone,msg);
  if(!link){showToast('WhatsApp number nahi hai');return;}
  // Log application
  applications.push({id:Date.now(),type:contactType,targetId:contactTarget.id,targetName:contactTarget.name,targetTitle:contactType==='skill'?contactTarget.skill:contactTarget.title,targetCity:contactTarget.city,targetPrice:contactType==='skill'?contactTarget.price:contactTarget.budget,message:msg,appliedAt:new Date().toLocaleString('en-IN'),status:'WhatsApp Sent',method:'whatsapp'});
  window.open(link,'_blank');
  closeModal('contact');
  showToast('💬 WhatsApp khul raha hai '+contactTarget.name+' ke liye!');
}

function directWhatsApp(phone,msg){
  const link=makeWALink(phone,msg);
  if(!link){showToast('Number nahi mila');return;}
  window.open(link,'_blank');
}

function sendMsg(){
  if(!v('cMsg')){showToast('Message likhо!');return;}
  const msg=v('cMsg');
  applications.push({id:Date.now(),type:contactType,targetId:contactTarget.id,targetName:contactTarget.name,targetTitle:contactType==='skill'?contactTarget.skill:contactTarget.title,targetCity:contactTarget.city,targetPrice:contactType==='skill'?contactTarget.price:contactTarget.budget,message:msg,appliedAt:new Date().toLocaleString('en-IN'),status:'Sent',method:'site'});
  closeModal('contact');
  showToast('✅ Message bhej diya '+contactTarget.name+' ko!');
}

// ─── PROFILE ───
function openProfileModal(){
  if(!currentUser)return;
  const isClient=currentRole==='client';
  const banner=document.getElementById('profileBanner');
  banner.style.background=isClient?'linear-gradient(135deg,#f59e0b,#f97316)':'linear-gradient(135deg,#6c63ff,#48bfe3)';
  document.getElementById('profileAv').textContent=initials(currentUser.name);
  document.getElementById('profileName').textContent=currentUser.name+(currentUser.premium?' ⭐':'');
  document.getElementById('profileRole').textContent=isClient?'💼 Client':'🎓 Student';
  const mySkillCount=skills.filter(s=>s.email===currentUser.email).length;
  const myJobCount=jobs.filter(j=>j.email===currentUser.email).length;
  document.getElementById('profileInfo').innerHTML=`
    <div class="info-row"><span style="color:#888">📍 City</span><span style="font-weight:600">${currentUser.city||'—'}</span></div>
    <div class="info-row"><span style="color:#888">📱 WhatsApp</span><span style="font-weight:600;color:${currentUser.phone?'#25D366':'#ef4444'}">${currentUser.phone||'Number nahi diya — Add karo!'}</span></div>
    <div class="info-row"><span style="color:#888">💎 Account</span><span style="font-weight:600;color:${currentUser.premium?'#f59e0b':'#888'}">${currentUser.premium?'⭐ Premium':'Free'}</span></div>
    ${!isClient?`<div class="info-row"><span style="color:#888">🎓 My Skills</span><span style="font-weight:600">${mySkillCount} posted</span></div>`:`<div class="info-row"><span style="color:#888">💼 My Jobs</span><span style="font-weight:600">${myJobCount} posted</span></div>`}
    <div class="info-row"><span style="color:#888">📩 Applications</span><span style="font-weight:600">${applications.length}</span></div>`;
  document.getElementById('editPhone').value=currentUser.phone||'';
  openModal('profile');
}
function updatePhone(){
  const ph=v('editPhone');
  if(!ph){showToast('Number daalo!');return;}
  currentUser.phone=ph;
  const u=users.find(x=>x.email===currentUser.email);
  if(u)u.phone=ph;
  // Also update any skills/jobs by this user
  skills.filter(s=>s.email===currentUser.email).forEach(s=>s.phone=ph);
  jobs.filter(j=>j.email===currentUser.email).forEach(j=>j.phone=ph);
  closeModal('profile');
  showToast('📱 WhatsApp number save ho gaya!');
  renderCards();
}

// ─── PREMIUM ───
function openModal(id){
  document.getElementById(id+'Modal').classList.add('show');
  if(id==='premium'){
    document.getElementById('pmStep1').style.display='block';
    ['pmPhonePe','pmUPI','pmSuccess'].forEach(x=>document.getElementById(x).style.display='none');
    setTimeout(drawPhonePeQR,100);
  }
}
function selectPayMethod(m){
  selectedPayMethod=m;
  document.getElementById('optPhonePe').style.borderColor=m==='phonepay'?'#5f259f':'#ddd';
  document.getElementById('optPhonePe').style.background=m==='phonepay'?'#faf5ff':'#f9f9f9';
  document.getElementById('optUPI').style.borderColor=m==='upi'?'#1a73e8':'#ddd';
  document.getElementById('optUPI').style.background=m==='upi'?'#f0f4ff':'#f9f9f9';
}
function goToPayment(){
  document.getElementById('pmStep1').style.display='none';
  if(selectedPayMethod==='phonepay'){document.getElementById('pmPhonePe').style.display='block';setTimeout(drawPhonePeQR,50);}
  else document.getElementById('pmUPI').style.display='block';
}
function drawPhonePeQR(){
  const canvas=document.getElementById('qrCanvas');if(!canvas)return;
  const ctx=canvas.getContext('2d'),size=140;
  ctx.fillStyle='#ffffff';ctx.fillRect(0,0,size,size);
  ctx.fillStyle='#5f259f';
  [[4,4],[size-24,4],[4,size-24]].forEach(([x,y])=>{
    ctx.fillRect(x,y,20,20);ctx.fillStyle='#fff';ctx.fillRect(x+3,y+3,14,14);ctx.fillStyle='#5f259f';ctx.fillRect(x+6,y+6,8,8);
  });
  for(let r=0;r<17;r++)for(let c=0;c<17;c++){
    if((r<4&&c<4)||(r<4&&c>12)||(r>12&&c<4))continue;
    if((7877353121*r*13+c*7+r+c)%3===0){ctx.fillStyle='#5f259f';ctx.fillRect(8+c*7,8+r*7,6,6);}
  }
  ctx.fillStyle='#fff';ctx.fillRect(55,55,30,30);
  ctx.fillStyle='#5f259f';ctx.font='bold 9px sans-serif';ctx.textAlign='center';
  ctx.fillText('PhonePe',70,70);ctx.font='7px sans-serif';ctx.fillText('7877...',70,80);
}
function confirmPayment(method){
  const txnId=method==='phonepay'?document.getElementById('ppTxnId').value.trim():document.getElementById('upiTxnId').value.trim();
  if(!txnId){showToast('Transaction ID daalna zaroori hai!');return;}
  document.getElementById(method==='phonepay'?'pmPhonePe':'pmUPI').style.display='none';
  document.getElementById('pmSuccess').style.display='block';
  showToast('✅ Payment request submit! Admin verify karega.');
}

// ─── ADMIN ───
function renderAdmin(){
  const totalRev=users.filter(u=>u.premium).length*99;
  const alwarUsers=users.filter(u=>u.city&&NEARBY_CITIES.includes(u.city)).length;
  document.getElementById('adminPanel').innerHTML=`
  <div style="padding:0.9rem;max-width:1100px;margin:0 auto">
  <div class="adm-hdr">
    <div style="font-size:1.8rem">👑</div>
    <div><h2>Admin Dashboard</h2><p>SkillSwap ka poora control · Alwar</p></div>
  </div>
  <div class="adm-stats">
    <div class="adm-sc"><div class="n">${users.filter(u=>u.role==='student').length}</div><div class="l">Students</div></div>
    <div class="adm-sc o"><div class="n o">${users.filter(u=>u.role==='client').length}</div><div class="l">Clients</div></div>
    <div class="adm-sc g"><div class="n g">${skills.filter(s=>s.isLocal).length}</div><div class="l">Alwar Skills</div></div>
    <div class="adm-sc o"><div class="n o">${jobs.filter(j=>j.isLocal).length}</div><div class="l">Alwar Jobs</div></div>
    <div class="adm-sc r"><div class="n r">₹${totalRev}</div><div class="l">Revenue</div></div>
    <div class="adm-sc g"><div class="n g">${alwarUsers}</div><div class="l">Local Users</div></div>
  </div>
  <div class="adm-sec">
    <h3>👥 Users (${users.filter(u=>u.role!=='admin').length})</h3>
    <div style="overflow-x:auto">
    <table class="atable">
      <thead><tr><th>Name</th><th>Role</th><th>City</th><th>WhatsApp</th><th>Status</th><th>Actions</th></tr></thead>
      <tbody>${users.filter(u=>u.role!=='admin').slice(0,25).map(u=>`
        <tr>
          <td><strong>${u.name}</strong><br><span style="color:#aaa;font-size:0.67rem">${u.email}</span></td>
          <td><span class="bdg" style="background:${u.role==='client'?'#fff7ed':'#f5f3ff'};color:${u.role==='client'?'#f97316':'#6c63ff'}">${u.role==='client'?'💼':'🎓'} ${u.role}</span></td>
          <td>${NEARBY_CITIES.includes(u.city)?'📍 ':''}<strong>${u.city}</strong></td>
          <td>${u.phone?`<a href="https://wa.me/91${cleanPhone(u.phone)}" target="_blank" style="color:#25D366;text-decoration:none;font-size:0.72rem;font-weight:600">💬 ${u.phone}</a>`:'<span style="color:#ccc;font-size:0.68rem">—</span>'}</td>
          <td><span class="schip ${u.status==='banned'?'s-banned':u.premium?'s-prem':'s-active'}">${u.status==='banned'?'Banned':u.premium?'⭐ Premium':'Active'}</span></td>
          <td>
            ${u.status!=='banned'?`<button class="admbtn ab-ban" onclick="adminBan('${u.email}')">Ban</button>`:`<button class="admbtn ab-unban" onclick="adminUnban('${u.email}')">Unban</button>`}
            ${!u.premium?`<button class="admbtn ab-prem" onclick="adminPremium('${u.email}')">⭐ Prem</button>`:''}
          </td>
        </tr>`).join('')}
      </tbody>
    </table></div>
  </div>
  <div class="adm-sec">
    <h3>💰 Revenue</h3>
    <div class="rev-box">
      <div class="rev-row"><span>Premium Students</span><span>${users.filter(u=>u.premium&&u.role==='student').length} × ₹99</span></div>
      <div class="rev-row"><span>Premium Clients</span><span>${users.filter(u=>u.premium&&u.role==='client').length} × ₹99</span></div>
      <div class="rev-row"><span>Total Revenue</span><span>₹${totalRev}</span></div>
    </div>
  </div>
  </div>`;
}
function adminBan(email){const u=users.find(x=>x.email===email);if(u){u.status='banned';renderAdmin();showToast('User banned');}}
function adminUnban(email){const u=users.find(x=>x.email===email);if(u){u.status='active';renderAdmin();showToast('User unbanned');}}
function adminPremium(email){const u=users.find(x=>x.email===email);if(u){u.premium=true;renderAdmin();showToast('⭐ Premium diya');}}

function closeModal(id){document.getElementById(id+'Modal').classList.remove('show');}
function v(id){const el=document.getElementById(id);return el?el.value.trim():'';}
function showToast(msg){const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');setTimeout(()=>t.classList.remove('show'),3000);}
</script>
</body>
</html>
