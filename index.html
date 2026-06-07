<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Casa Moneda Digital · Certificado + Pago Transbank</title>
<style>
  /* ─────────────────────────────────────────────
     VARIABLES Y RESET
  ───────────────────────────────────────────── */
  :root {
    --gold: #B8860B;
    --gold-lt: #D4A017;
    --dark: #1E1E1C;
    --dark2: #2C2C2A;
    --bg: #F8F7F4;
    --bg2: #EFEDE8;
    --text: #1E1E1C;
    --text2: #5F5E5A;
    --border: rgba(0,0,0,0.12);
    --border2: rgba(0,0,0,0.22);
    --radius: 10px;
    --radius-lg: 14px;
    --green-bg: #EAF3DE;
    --green-text: #3B6D11;
    --green-border: #97C459;
    --blue-bg: #E6F1FB;
    --blue-text: #185FA5;
    --blue-border: #85B7EB;
    --amber-bg: #FAEEDA;
    --amber-text: #633806;
    --amber-border: #FAC775;
  }

  @media (prefers-color-scheme: dark) {
    :root {
      --bg: #1A1A18;
      --bg2: #242422;
      --text: #F0EEE8;
      --text2: #888780;
      --border: rgba(255,255,255,0.10);
      --border2: rgba(255,255,255,0.22);
    }
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    padding: 2rem 1rem;
  }

  .app { width: 100%; max-width: 480px; }

  /* ─────────────────────────────────────────────
     PANTALLA ACTIVA
  ───────────────────────────────────────────── */
  .screen { display: none; }
  .screen.active { display: block; animation: fadeIn 0.2s ease; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: none; } }

  /* ─────────────────────────────────────────────
     TIPOGRAFÍA UTILITARIA
  ───────────────────────────────────────────── */
  .lbl {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: .07em;
    color: var(--text2);
    margin-bottom: 5px;
    display: block;
  }

  /* ─────────────────────────────────────────────
     BOTONES
  ───────────────────────────────────────────── */
  .btn-dark {
    background: var(--dark2);
    color: var(--gold-lt);
    border: 1px solid var(--gold-lt);
    padding: 11px 24px;
    border-radius: var(--radius);
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
    transition: opacity .15s;
    display: inline-flex;
    align-items: center;
    gap: 7px;
  }
  .btn-dark:hover { opacity: .82; }

  .btn-sec {
    flex: 1;
    min-width: 120px;
    padding: 10px 12px;
    border-radius: var(--radius);
    border: 1px solid var(--border2);
    background: var(--bg);
    font-size: 13px;
    cursor: pointer;
    color: var(--text);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    transition: background .15s;
  }
  .btn-sec:hover { background: var(--bg2); }

  .btn-gold {
    flex: 1;
    min-width: 120px;
    padding: 10px 12px;
    border-radius: var(--radius);
    border: 1px solid var(--gold-lt);
    background: var(--dark2);
    font-size: 13px;
    cursor: pointer;
    color: var(--gold-lt);
    font-weight: 500;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    transition: opacity .15s;
  }
  .btn-gold:hover { opacity: .82; }

  .confirm-btn {
    width: 100%;
    padding: 12px;
    border-radius: var(--radius);
    background: var(--dark2);
    color: var(--gold-lt);
    border: 1px solid var(--gold-lt);
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    transition: opacity .15s;
  }
  .confirm-btn:hover { opacity: .82; }

  /* ─────────────────────────────────────────────
     PANTALLA 1 — QR
  ───────────────────────────────────────────── */
  .qr-wrap {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    padding: 2.5rem 1.5rem;
    text-align: center;
  }

  .qr-frame {
    width: 160px;
    height: 160px;
    margin: 0 auto 1.5rem;
    background: #fff;
    border: 1px solid var(--border);
    border-radius: var(--radius);
    position: relative;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .qr-grid {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 3px;
    padding: 16px;
    width: 100%;
    height: 100%;
  }
  .qr-grid span { border-radius: 1px; background: #1E1E1C; }

  .scan-bar {
    position: absolute;
    left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, #D4A017, transparent);
    animation: scan 1.8s ease-in-out forwards;
  }
  @keyframes scan { 0% { top: 10%; } 60% { top: 85%; } 100% { top: 85%; opacity: 0; } }

  .qr-title { font-size: 18px; font-weight: 500; margin-bottom: .4rem; color: var(--text); }
  .qr-sub { font-size: 13px; color: var(--text2); margin-bottom: 1.5rem; }

  /* ─────────────────────────────────────────────
     PANTALLA 2 — VERIFICANDO
  ───────────────────────────────────────────── */
  .verify-wrap {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    padding: 3rem 1.5rem;
    text-align: center;
  }

  .spinner {
    width: 48px; height: 48px;
    border: 3px solid var(--border);
    border-top-color: var(--gold-lt);
    border-radius: 50%;
    margin: 0 auto 1.5rem;
    animation: spin .8s linear infinite;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  .vsteps { list-style: none; text-align: left; max-width: 280px; margin: 1.25rem auto 0; }
  .vsteps li {
    font-size: 13px; color: var(--text2); padding: 7px 0;
    display: flex; align-items: center; gap: 9px;
    border-bottom: 1px solid var(--border);
    transition: color .3s;
  }
  .vsteps li:last-child { border-bottom: none; }
  .vsteps li.done { color: var(--text); }
  .vsteps li .step-ico { width: 20px; text-align: center; }

  /* ─────────────────────────────────────────────
     PANTALLA 3 — CERTIFICADO
  ───────────────────────────────────────────── */
  .cert-head {
    background: var(--dark2);
    border-radius: var(--radius-lg) var(--radius-lg) 0 0;
    padding: 1rem 1.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .cert-badge { display: flex; align-items: center; gap: 7px; font-size: 11px; color: var(--gold-lt); text-transform: uppercase; letter-spacing: .08em; }
  .dot-live { width: 6px; height: 6px; border-radius: 50%; background: #4CAF50; animation: pulse 1.5s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.4} }
  .cert-inst { font-size: 11px; color: #888; }

  .cert-body {
    background: var(--bg);
    border: 1px solid var(--border);
    border-top: none;
    padding: 1.5rem;
  }

  .coin-row { display: flex; gap: 1.25rem; align-items: flex-start; margin-bottom: 1.25rem; }

  .coin-vis {
    width: 80px; height: 80px; border-radius: 50%;
    background: radial-gradient(circle at 33% 33%, #F5D68C, #B8860B 55%, #7A5800);
    border: 2px solid var(--gold-lt);
    flex-shrink: 0;
    display: flex; align-items: center; justify-content: center;
    font-size: 10px; font-weight: 600; color: #4A3800; text-align: center; line-height: 1.3;
  }

  .coin-info h2 { font-size: 16px; font-weight: 500; color: var(--text); margin-bottom: 4px; }
  .coin-info p  { font-size: 13px; color: var(--text2); margin-bottom: 8px; }

  .tag-ok {
    display: inline-flex; align-items: center; gap: 4px;
    font-size: 11px; padding: 3px 9px; border-radius: 20px;
    background: var(--green-bg); color: var(--green-text);
    border: 1px solid var(--green-border);
  }

  .divider { border: none; border-top: 1px solid var(--border); margin: 1rem 0; }

  .dgrid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 1rem; }
  .dcell {
    background: var(--bg2); border-radius: var(--radius); padding: 10px 12px;
    border: 1px solid var(--border);
  }
  .dcell .l { font-size: 10px; color: var(--text2); text-transform: uppercase; letter-spacing: .06em; margin-bottom: 4px; }
  .dcell .v { font-size: 13px; font-weight: 500; color: var(--text); }

  .hash-box {
    background: var(--bg2); border-radius: var(--radius); padding: 10px 12px;
    border: 1px solid var(--border); margin-bottom: 1rem;
  }
  .hash-code { font-family: 'Courier New', monospace; font-size: 10px; color: var(--text2); word-break: break-all; line-height: 1.6; }

  .owners .l { font-size: 10px; color: var(--text2); text-transform: uppercase; letter-spacing: .06em; margin-bottom: 8px; }
  .ow-item {
    display: flex; align-items: center; gap: 10px; padding: 7px 0;
    border-bottom: 1px solid var(--border); font-size: 12px;
  }
  .ow-item:last-child { border-bottom: none; }
  .av { width: 28px; height: 28px; border-radius: 50%; flex-shrink: 0; display: flex; align-items: center; justify-content: center; font-size: 10px; font-weight: 600; }
  .ow-name { flex: 1; color: var(--text); }
  .ow-dt   { color: var(--text2); font-size: 11px; }
  .ow-p    { font-weight: 500; color: var(--text); font-family: 'Courier New', monospace; }

  .tbk-note {
    font-size: 12px; background: var(--blue-bg); border: 1px solid var(--blue-border);
    border-radius: var(--radius); color: var(--blue-text);
    padding: 9px 12px; margin-bottom: 1rem;
    display: flex; align-items: flex-start; gap: 8px; line-height: 1.5;
  }

  .cert-foot {
    background: var(--bg2); border: 1px solid var(--border); border-top: none;
    border-radius: 0 0 var(--radius-lg) var(--radius-lg);
    padding: 1rem 1.5rem;
    display: flex; gap: 8px; flex-wrap: wrap;
  }

  /* ─────────────────────────────────────────────
     PANTALLA 4 — FORMULARIO DE PAGO
  ───────────────────────────────────────────── */
  .pay-wrap {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    overflow: hidden;
  }

  .pay-head {
    background: var(--dark2); padding: 1rem 1.5rem;
    display: flex; align-items: center; gap: 10px;
  }
  .pay-head h3 { font-size: 14px; font-weight: 500; color: var(--gold-lt); }
  .back-btn { background: none; border: none; color: #888; cursor: pointer; font-size: 20px; line-height: 1; padding: 0; }

  .pay-body { padding: 1.5rem; }

  .coin-mini-row {
    display: flex; align-items: center; gap: 12px;
    margin-bottom: 1.25rem; padding: 10px 12px;
    background: var(--bg2); border-radius: var(--radius);
    border: 1px solid var(--border);
  }
  .coin-mini {
    width: 40px; height: 40px; border-radius: 50%;
    background: radial-gradient(circle at 33% 33%, #F5D68C, #B8860B 55%, #7A5800);
    border: 1.5px solid var(--gold-lt); flex-shrink: 0;
  }
  .coin-mini-row p    { font-size: 13px; font-weight: 500; color: var(--text); }
  .coin-mini-row span { font-size: 11px; color: var(--text2); }

  /* Tabs método */
  .method-tabs { display: flex; gap: 7px; margin-bottom: 1.25rem; }
  .mtab {
    flex: 1; padding: 9px 6px; border-radius: var(--radius);
    border: 1px solid var(--border2); background: var(--bg2);
    font-size: 12px; cursor: pointer; color: var(--text2);
    text-align: center; transition: all .15s;
    display: flex; flex-direction: column; align-items: center; gap: 5px;
  }
  .mtab.active { border-color: var(--blue-text); background: var(--blue-bg); color: var(--blue-text); }
  .mtab svg { width: 18px; height: 18px; stroke: currentColor; fill: none; stroke-width: 1.8; }

  /* Inputs */
  .form-group { margin-bottom: 1rem; }
  .form-input {
    width: 100%; padding: 10px 12px; border-radius: var(--radius);
    border: 1px solid var(--border2);
    background: var(--bg); color: var(--text); font-size: 14px;
  }
  .form-input:focus { outline: none; border-color: var(--blue-text); box-shadow: 0 0 0 3px rgba(24,95,165,.15); }

  .card-row   { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
  .bank-list  { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-bottom: 1rem; }

  .bank-item {
    padding: 10px; border-radius: var(--radius);
    border: 1px solid var(--border2); background: var(--bg2);
    cursor: pointer; text-align: center; transition: all .15s;
  }
  .bank-item.sel { border-color: var(--blue-text); background: var(--blue-bg); }
  .bank-item .bn { font-size: 12px; font-weight: 500; color: var(--text); }
  .bank-item .bc { font-size: 10px; color: var(--text2); }
  .acct-row { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }

  /* Resumen */
  .pay-summary {
    background: var(--bg2); border-radius: var(--radius);
    border: 1px solid var(--border); padding: 1rem 1.25rem; margin-bottom: 1rem;
  }
  .pay-summary .ps-title { font-size: 10px; text-transform: uppercase; letter-spacing: .07em; color: var(--text2); margin-bottom: 9px; }
  .ps-row { display: flex; justify-content: space-between; font-size: 12px; padding: 4px 0; }
  .ps-row.total { border-top: 1px solid var(--border); margin-top: 4px; padding-top: 8px; font-weight: 600; font-size: 14px; }
  .ps-row span:last-child { font-family: 'Courier New', monospace; }
  .ps-muted { color: var(--text2); }

  .tbk-brand {
    display: flex; align-items: center; gap: 8px;
    font-size: 11px; color: var(--text2); margin-bottom: 1rem;
  }
  .tbk-logo {
    background: #E60012; color: #fff;
    font-size: 10px; font-weight: 700; padding: 3px 8px;
    border-radius: 4px; letter-spacing: .06em;
  }

  /* ─────────────────────────────────────────────
     PANTALLA 5 — PROCESANDO
  ───────────────────────────────────────────── */
  .proc-wrap {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: var(--radius-lg); padding: 3rem 1.5rem; text-align: center;
  }
  .tbk-logo-big {
    background: #E60012; color: #fff;
    font-size: 15px; font-weight: 700; padding: 7px 18px;
    border-radius: 6px; letter-spacing: .06em;
    display: inline-block; margin-bottom: 1.5rem;
  }
  .proc-steps { list-style: none; max-width: 270px; margin: 1.25rem auto 0; }
  .proc-steps li {
    font-size: 12px; color: var(--text2); padding: 6px 0;
    display: flex; align-items: center; gap: 8px;
    border-bottom: 1px solid var(--border); transition: color .3s;
  }
  .proc-steps li:last-child { border-bottom: none; }
  .proc-steps li.done { color: var(--text); }

  /* ─────────────────────────────────────────────
     PANTALLA 6 — ÉXITO
  ───────────────────────────────────────────── */
  .ok-wrap {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: var(--radius-lg); padding: 2.5rem 1.5rem; text-align: center;
  }
  .ok-icon {
    width: 64px; height: 64px; border-radius: 50%;
    background: var(--green-bg); border: 1px solid var(--green-border);
    margin: 0 auto 1.25rem;
    display: flex; align-items: center; justify-content: center;
  }
  .ok-icon svg { width: 28px; height: 28px; stroke: var(--green-text); fill: none; stroke-width: 2.5; }
  .ok-folio {
    font-family: 'Courier New', monospace; font-size: 11px; color: var(--text2);
    background: var(--bg); padding: 8px 12px;
    border-radius: var(--radius); border: 1px solid var(--border);
    margin: 1rem auto; max-width: 320px; word-break: break-all; line-height: 1.7;
  }
  .ok-actions { display: flex; gap: 8px; justify-content: center; margin-top: 1.5rem; flex-wrap: wrap; }
</style>
</head>
<body>

<div class="app" role="main">

  <!-- ═══════════════════════════════════════════
       PANTALLA 1 — ESCANEO QR
  ════════════════════════════════════════════ -->
  <div id="s1" class="screen active qr-wrap">
    <p class="lbl" style="text-align:center;margin-bottom:1.25rem">
      📱 Escanea tu moneda
    </p>
    <div class="qr-frame">
      <div class="scan-bar" id="scanBar"></div>
      <div class="qr-grid" id="qrGrid"></div>
    </div>
    <h2 class="qr-title">Moneda Bicentenario 2010</h2>
    <p class="qr-sub">Escanea el código QR grabado en la moneda<br>para ver su certificado y venderla</p>
    <button class="btn-dark" onclick="startVerify()">
      🔍 Simular escaneo
    </button>
  </div>

  <!-- ═══════════════════════════════════════════
       PANTALLA 2 — VERIFICANDO
  ════════════════════════════════════════════ -->
  <div id="s2" class="screen verify-wrap">
    <div class="spinner"></div>
    <p style="font-size:16px;font-weight:500;color:var(--text);margin-bottom:.4rem">Verificando autenticidad</p>
    <p style="font-size:13px;color:var(--text2)">Consultando registro oficial Casa Moneda...</p>
    <ul class="vsteps">
      <li id="v1"><span class="step-ico">⏳</span> Leyendo identificador único</li>
      <li id="v2"><span class="step-ico">⏳</span> Validando en registro oficial</li>
      <li id="v3"><span class="step-ico">⏳</span> Recuperando historial de propiedad</li>
      <li id="v4"><span class="step-ico">⏳</span> Generando certificado digital</li>
    </ul>
  </div>

  <!-- ═══════════════════════════════════════════
       PANTALLA 3 — CERTIFICADO DIGITAL
  ════════════════════════════════════════════ -->
  <div id="s3" class="screen">
    <!-- Cabecera oscura -->
    <div class="cert-head">
      <div class="cert-badge">
        <div class="dot-live"></div>
        Autenticidad verificada
      </div>
      <span class="cert-inst">Casa Moneda de Chile · oficial</span>
    </div>

    <!-- Cuerpo -->
    <div class="cert-body">
      <!-- Moneda + info -->
      <div class="coin-row">
        <div class="coin-vis">Chile<br>$200<br>2010</div>
        <div class="coin-info">
          <h2>Moneda Bicentenario 2010</h2>
          <p>$200 · Cobre-Níquel · Edición limitada</p>
          <span class="tag-ok">✓ Auténtica</span>
        </div>
      </div>

      <hr class="divider">

      <!-- Grid de datos -->
      <div class="dgrid">
        <div class="dcell">
          <div class="l">N° de serie</div>
          <div class="v" style="font-family:'Courier New',monospace;font-size:11px">CM-2010-00847</div>
        </div>
        <div class="dcell">
          <div class="l">Fecha acuñación</div>
          <div class="v">14 Sep 2010</div>
        </div>
        <div class="dcell">
          <div class="l">Composición</div>
          <div class="v">Cu 75% · Ni 25%</div>
        </div>
        <div class="dcell">
          <div class="l">Tirada total</div>
          <div class="v">50.000 unidades</div>
        </div>
        <div class="dcell">
          <div class="l">Valor de mercado</div>
          <div class="v">$38.500 CLP</div>
        </div>
        <div class="dcell">
          <div class="l">N° certificado</div>
          <div class="v" style="font-family:'Courier New',monospace;font-size:11px">CERT-4721</div>
        </div>
      </div>

      <!-- Hash -->
      <div class="hash-box">
        <div class="l">Código de autenticidad (registro oficial)</div>
        <div class="hash-code">CM2010-847-AUTH-3A7F8B2C1D9E4F6A0B5C8D2E7F1A3B6C9D0E2F</div>
      </div>

      <!-- Historial de propietarios -->
      <div class="owners" style="margin-bottom:1rem">
        <div class="l">Historial de propietarios</div>
        <div class="ow-item">
          <div class="av" style="background:#E6F1FB;color:#185FA5">CM</div>
          <span class="ow-name">Casa Moneda de Chile <span style="font-size:10px;color:var(--text2)">(origen)</span></span>
          <span class="ow-dt">Sep 2010</span>
        </div>
        <div class="ow-item">
          <div class="av" style="background:#EEEDFE;color:#534AB7">RP</div>
          <span class="ow-name">Roberto Pérez</span>
          <span class="ow-dt">Mar 2018</span>
          <span class="ow-p">$18.000</span>
        </div>
        <div class="ow-item">
          <div class="av" style="background:#E1F5EE;color:#0F6E56">TÚ</div>
          <span class="ow-name">Tú <span style="font-size:10px;color:var(--text2)">(propietario actual)</span></span>
          <span class="ow-dt">Ene 2024</span>
          <span class="ow-p">$25.000</span>
        </div>
      </div>

      <!-- Nota Transbank -->
      <div class="tbk-note">
        ℹ️
        <span>Al vender tu moneda, el cobro al comprador se procesa vía <strong>Webpay Plus (Transbank)</strong>. El pago llega directo a tu cuenta bancaria en 24–48 hrs hábiles.</span>
      </div>
    </div>

    <!-- Footer de acciones -->
    <div class="cert-foot">
      <button class="btn-sec" onclick="alert('En producción: enlace a documentación técnica de la integración.')">
        ❓ Cómo funciona
      </button>
      <button class="btn-gold" onclick="showPay()">
        💳 Vender mi moneda
      </button>
    </div>
  </div>

  <!-- ═══════════════════════════════════════════
       PANTALLA 4 — FORMULARIO DE PAGO
  ════════════════════════════════════════════ -->
  <div id="s4" class="screen pay-wrap">
    <div class="pay-head">
      <button class="back-btn" onclick="goBack()" aria-label="Volver">←</button>
      <h3>Vender moneda · Cobro al comprador</h3>
    </div>

    <div class="pay-body">
      <!-- Resumen de la pieza -->
      <div class="coin-mini-row">
        <div class="coin-mini"></div>
        <div>
          <p>Moneda Bicentenario 2010</p>
          <span>CM-2010-00847 · CERT-4721</span>
        </div>
      </div>

      <!-- Precio de venta -->
      <div class="form-group">
        <label class="lbl" for="sellPrice">Precio de venta (CLP)</label>
        <input id="sellPrice" class="form-input" type="number" value="38500" oninput="updateSummary()">
      </div>

      <!-- Selector de método de pago -->
      <label class="lbl">Método de pago del comprador</label>
      <div class="method-tabs">
        <div class="mtab active" id="tab-webpay" onclick="setMethod('webpay')">
          <svg viewBox="0 0 24 24"><rect x="2" y="5" width="20" height="14" rx="2"/><line x1="2" y1="10" x2="22" y2="10"/></svg>
          <span>Webpay / Débito</span>
        </div>
        <div class="mtab" id="tab-transfer" onclick="setMethod('transfer')">
          <svg viewBox="0 0 24 24"><line x1="3" y1="12" x2="21" y2="12"/><polyline points="8 8 3 12 8 16"/><path d="M21 12V7a2 2 0 0 0-2-2H5"/></svg>
          <span>Transferencia</span>
        </div>
        <div class="mtab" id="tab-mach" onclick="setMethod('mach')">
          <svg viewBox="0 0 24 24"><rect x="5" y="2" width="14" height="20" rx="2"/><line x1="12" y1="18" x2="12.01" y2="18" stroke-linecap="round"/></svg>
          <span>MACH / Prepago</span>
        </div>
      </div>

      <!-- ── FORM WEBPAY ── -->
      <div id="form-webpay">
        <div class="form-group">
          <label class="lbl" for="cardNum">Número de tarjeta</label>
          <input id="cardNum" class="form-input" type="text" placeholder="•••• •••• •••• ••••" maxlength="19" oninput="fmtCard(this)">
        </div>
        <div class="card-row">
          <div class="form-group">
            <label class="lbl" for="cardExp">Vencimiento</label>
            <input id="cardExp" class="form-input" type="text" placeholder="MM/AA" maxlength="5" oninput="fmtExp(this)">
          </div>
          <div class="form-group">
            <label class="lbl" for="cardCvv">CVV</label>
            <input id="cardCvv" class="form-input" type="text" placeholder="•••" maxlength="3">
          </div>
        </div>
        <div class="form-group">
          <label class="lbl" for="cardName">Nombre en la tarjeta</label>
          <input id="cardName" class="form-input" type="text" placeholder="NOMBRE APELLIDO">
        </div>
      </div>

      <!-- ── FORM TRANSFERENCIA ── -->
      <div id="form-transfer" style="display:none">
        <label class="lbl">Banco del comprador</label>
        <div class="bank-list" id="bankList">
          <div class="bank-item sel" onclick="selBank(this)"><div class="bn">Banco de Chile</div><div class="bc">Transferencia directa</div></div>
          <div class="bank-item" onclick="selBank(this)"><div class="bn">BancoEstado</div><div class="bc">Transferencia directa</div></div>
          <div class="bank-item" onclick="selBank(this)"><div class="bn">Santander</div><div class="bc">Transferencia directa</div></div>
          <div class="bank-item" onclick="selBank(this)"><div class="bn">BCI</div><div class="bc">Transferencia directa</div></div>
          <div class="bank-item" onclick="selBank(this)"><div class="bn">Scotiabank</div><div class="bc">Transferencia directa</div></div>
          <div class="bank-item" onclick="selBank(this)"><div class="bn">Itaú</div><div class="bc">Transferencia directa</div></div>
        </div>
        <div class="acct-row">
          <div class="form-group">
            <label class="lbl" for="rut">RUT del comprador</label>
            <input id="rut" class="form-input" type="text" placeholder="12.345.678-9" oninput="fmtRut(this)">
          </div>
          <div class="form-group">
            <label class="lbl" for="acctNum">N° de cuenta</label>
            <input id="acctNum" class="form-input" type="text" placeholder="000000000">
          </div>
        </div>
        <div class="form-group">
          <label class="lbl" for="email">Email del comprador</label>
          <input id="email" class="form-input" type="email" placeholder="comprador@email.com">
        </div>
      </div>

      <!-- ── FORM MACH ── -->
      <div id="form-mach" style="display:none">
        <div class="form-group">
          <label class="lbl" for="machPhone">Teléfono o alias MACH del comprador</label>
          <input id="machPhone" class="form-input" type="text" placeholder="+56 9 1234 5678 o @usuario">
        </div>
        <p style="font-size:12px;color:var(--text2);margin-top:-6px;margin-bottom:1rem;line-height:1.5">
          El comprador recibirá una notificación push en su app MACH / BancoEstado para confirmar el pago.
        </p>
      </div>

      <!-- Resumen de la transacción -->
      <div class="pay-summary">
        <p class="ps-title">📋 Resumen de la transacción</p>
        <div class="ps-row"><span>Precio de venta</span><span id="ps-total">$38.500</span></div>
        <div class="ps-row"><span class="ps-muted">Comisión Transbank (1,99%)</span><span id="ps-tbk" class="ps-muted">- $766</span></div>
        <div class="ps-row"><span class="ps-muted">Cargo plataforma Casa Moneda (2%)</span><span id="ps-cm" class="ps-muted">- $770</span></div>
        <div class="ps-row total"><span>Recibes en tu cuenta</span><span id="ps-you">$36.964</span></div>
      </div>

      <!-- Marca Transbank -->
      <div class="tbk-brand">
        <div class="tbk-logo">Transbank</div>
        <span>Pago procesado con seguridad por Transbank · SSL 256-bit · PCI DSS</span>
      </div>

      <button class="confirm-btn" onclick="procesar()">
        🔒 Confirmar y cobrar al comprador
      </button>
    </div>
  </div>

  <!-- ═══════════════════════════════════════════
       PANTALLA 5 — PROCESANDO
  ════════════════════════════════════════════ -->
  <div id="s5" class="screen proc-wrap">
    <div class="tbk-logo-big">Transbank</div>
    <div class="spinner"></div>
    <p style="font-size:16px;font-weight:500;color:var(--text);margin-bottom:.4rem">Procesando pago</p>
    <p style="font-size:12px;color:var(--text2)">Comunicando con servidor Transbank...</p>
    <ul class="proc-steps">
      <li id="p1"><span>⏳</span> Iniciando sesión de pago segura</li>
      <li id="p2"><span>⏳</span> Autorizando con el banco emisor</li>
      <li id="p3"><span>⏳</span> Generando orden de liquidación</li>
      <li id="p4"><span>⏳</span> Actualizando certificado digital</li>
    </ul>
  </div>

  <!-- ═══════════════════════════════════════════
       PANTALLA 6 — ÉXITO
  ════════════════════════════════════════════ -->
  <div id="s6" class="screen ok-wrap">
    <div class="ok-icon">
      <svg viewBox="0 0 24 24"><polyline points="20 6 9 17 4 12"/></svg>
    </div>
    <h2 style="font-size:18px;font-weight:500;color:var(--text);margin-bottom:.4rem">¡Venta completada!</h2>
    <p style="font-size:14px;color:var(--text2);margin-bottom:.25rem">El pago fue procesado por Transbank exitosamente.</p>
    <p style="font-size:13px;color:var(--text2)">
      Recibirás <strong id="ok-amount">$36.964</strong> en tu cuenta bancaria en <strong>24–48 hrs hábiles</strong>.
    </p>
    <div class="ok-folio" id="ok-folio">
      Folio Transbank: TBK-2024-00847-X<br>
      Código auth: 123456 · Webpay Plus
    </div>
    <p style="font-size:12px;color:var(--text2);margin-top:.75rem">
      El certificado digital de la moneda fue actualizado con el nuevo propietario.
    </p>
    <div class="ok-actions">
      <button class="btn-sec" onclick="restart()">🔄 Nueva consulta</button>
      <button class="btn-sec" onclick="alert('En producción: redirige a documentación de integración Transbank Webpay Plus.')">
        Integrar en producción
      </button>
    </div>
  </div>

</div><!-- /app -->

<!-- ═══════════════════════════════════════════════
     JAVASCRIPT
════════════════════════════════════════════════ -->
<script>
/* ── QR decorativo ── */
const QR_PAT = [
  1,1,1,0,1,1,1,
  1,0,1,0,0,0,1,
  1,1,1,0,1,1,1,
  1,0,0,1,0,0,0,
  0,1,1,0,1,1,1,
  0,0,0,1,0,1,1,
  1,0,1,1,0,1,0
];
(function buildQR() {
  const g = document.getElementById('qrGrid');
  QR_PAT.forEach(v => {
    const s = document.createElement('span');
    s.style.opacity = v ? '1' : '0';
    g.appendChild(s);
  });
})();

/* ── Navegación entre pantallas ── */
function show(id) {
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

/* ── Animación de pasos con íconos ── */
function animateSteps(prefix, count, base, cb) {
  for (let i = 1; i <= count; i++) {
    const delay = base + (i - 1) * 600;
    setTimeout(() => {
      const li = document.getElementById(prefix + i);
      if (!li) return;
      li.querySelector('span').textContent = '✓';
      li.classList.add('done');
      if (i === count && cb) cb();
    }, delay);
  }
}

/* ── S1 → S2 → S3 ── */
function startVerify() {
  show('s2');
  animateSteps('v', 4, 500, () => setTimeout(() => show('s3'), 500));
}

/* ── S3 → S4 ── */
function showPay() { show('s4'); }

/* ── S4 → S3 ── */
function goBack() { show('s3'); }

/* ── Formateo de moneda CLP ── */
function fmt(n) {
  return '$' + Math.round(n).toLocaleString('es-CL');
}

/* ── Actualiza resumen de precios ── */
function updateSummary() {
  const price = parseFloat(document.getElementById('sellPrice').value) || 0;
  const tbk   = price * 0.0199;
  const cm    = price * 0.02;
  const you   = price - tbk - cm;
  document.getElementById('ps-total').textContent = fmt(price);
  document.getElementById('ps-tbk').textContent   = '- ' + fmt(tbk);
  document.getElementById('ps-cm').textContent    = '- ' + fmt(cm);
  document.getElementById('ps-you').textContent   = fmt(you);
}

/* ── Tabs de método de pago ── */
let method = 'webpay';
const methodLabels = { webpay: 'Webpay Plus', transfer: 'Transferencia bancaria', mach: 'MACH / BancoEstado' };

function setMethod(m) {
  method = m;
  ['webpay', 'transfer', 'mach'].forEach(k => {
    document.getElementById('tab-' + k).classList.toggle('active', k === m);
    document.getElementById('form-' + k).style.display = k === m ? 'block' : 'none';
  });
}

/* ── Selección de banco ── */
function selBank(el) {
  document.querySelectorAll('.bank-item').forEach(b => b.classList.remove('sel'));
  el.classList.add('sel');
}

/* ── Formateo tarjeta ── */
function fmtCard(el) {
  let v = el.value.replace(/\D/g, '').substring(0, 16);
  el.value = v.replace(/(.{4})/g, '$1 ').trim();
}
function fmtExp(el) {
  let v = el.value.replace(/\D/g, '');
  if (v.length >= 2) v = v.substring(0, 2) + '/' + v.substring(2, 4);
  el.value = v;
}

/* ── Formateo RUT chileno ── */
function fmtRut(el) {
  let v = el.value.replace(/[^0-9kK]/g, '').toUpperCase();
  if (v.length > 1) {
    const dv   = v.slice(-1);
    let   body = v.slice(0, -1).replace(/\B(?=(\d{3})+(?!\d))/g, '.');
    v = body + '-' + dv;
  }
  el.value = v;
}

/* ── S4 → S5 → S6 ── */
function procesar() {
  show('s5');
  animateSteps('p', 4, 400, () => {
    setTimeout(() => {
      const price   = parseFloat(document.getElementById('sellPrice').value) || 38500;
      const you     = price - price * 0.0199 - price * 0.02;
      const folio   = 'TBK-2024-' + String(Math.floor(Math.random() * 99999)).padStart(5, '0') + '-X';
      const auth    = String(Math.floor(Math.random() * 900000) + 100000);
      document.getElementById('ok-amount').textContent = fmt(you);
      document.getElementById('ok-folio').innerHTML =
        'Folio Transbank: ' + folio + '<br>Código auth: ' + auth + ' · ' + methodLabels[method];
      show('s6');
    }, 400);
  });
}

/* ── Reiniciar ── */
function restart() { show('s1'); }
</script>

</body>
</html>
