<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MonedaViva · Casa Moneda de Chile</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --navy:       #0B1F3A;
  --navy2:      #122847;
  --navy3:      #1A3A5C;
  --navy-light: #2E6DA4;
  --white:      #FFFFFF;
  --off-white:  #F4F7FB;
  --soft:       #E8EEF6;
  --soft2:      #D4E1F0;
  --gold:       #C9A84C;
  --gold-lt:    #E2C06A;
  --text:       #0B1F3A;
  --text2:      #3A5070;
  --text3:      #6B87A8;
  --radius:      10px;
  --radius-lg:  16px;
  --green-bg:#EAF3DE;--green-text:#2E6B0F;
  --tag-new-bg:#E6F1FB;--tag-new-text:#0C447C;--tag-new-border:#85B7EB;
}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',Helvetica,sans-serif;background:var(--off-white);color:var(--text);line-height:1.65}

/* NAV TAB */
.site-header{background:var(--navy);position:sticky;top:0;z-index:100;border-bottom:3px solid var(--gold)}
.nav-inner{max-width:1140px;margin:0 auto;padding:0 1.5rem;display:flex;align-items:center;justify-content:space-between;height:66px}
.logo-wrap{display:flex;align-items:center;gap:13px}
.logo-coin{width:40px;height:40px;border-radius:50%;background:radial-gradient(circle at 35% 35%,#F7E48A,var(--gold) 55%,#7A5800);border:2px solid var(--gold-lt);display:flex;align-items:center;justify-content:center;font-size:9px;font-weight:800;color:#3A2800;text-align:center}
.logo-text strong{display:block;font-size:18px;font-weight:800;color:var(--white)}
.logo-text span{font-size:10px;color:var(--gold-lt);text-transform:uppercase;letter-spacing:.1em}

.main-nav-tabs{display:flex;justify-content:center;background:var(--navy2);border-bottom:2px solid var(--gold)}
.main-tab{padding:12px 24px;color:rgba(255,255,255,0.7);font-weight:700;font-size:14px;cursor:pointer}
.main-tab.active{color:var(--gold-lt);border-bottom:3px solid var(--gold-lt);background:var(--navy3)}

/* HERO & SECCIONES */
.hero{background:var(--navy);padding:3rem 1.5rem 1.5rem;text-align:center;color:var(--white)}
.hero h1{font-size:2.2rem;font-weight:800;margin-bottom:0.5rem}
.hero p{color:rgba(255,255,255,0.6);font-size:14px}

.view-section{display:none;padding:2rem 1.5rem;max-width:1140px;margin:0 auto}
.view-section.active{display:block}

/* CATÁLOGO */
.prod-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(310px,1fr));gap:2rem}
.prod-card{background:var(--white);border:1.5px solid var(--soft2);border-radius:var(--radius-lg);overflow:hidden;cursor:pointer;display:flex;flex-direction:column;transition:transform .2s,box-shadow .2s}
.prod-card:hover{transform:translateY(-4px);box-shadow:0 12px 32px rgba(11,31,58,0.12)}
.prod-img{height:240px;background:var(--soft);display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden}
.prod-img img{width:100%;height:100%;object-fit:contain;background:#000}
.prod-tag{position:absolute;top:12px;right:12px;font-size:10px;padding:4px 10px;border-radius:20px;font-weight:700;z-index:10;background:var(--tag-new-bg);color:var(--tag-new-text);border:1px solid var(--tag-new-border)}
.prod-info{padding:1.5rem;flex-grow:1}
.prod-info h3{font-size:17px;font-weight:700;color:var(--navy);margin-bottom:6px}
.prod-info p{font-size:13px;color:var(--text2);margin-bottom:1rem;height:45px;overflow:hidden}
.prod-qr-status{font-size:11px;font-weight:700;color:var(--green-text);background:var(--green-bg);padding:5px 10px;border-radius:6px;display:inline-flex;align-items:center;gap:6px;margin-bottom:1rem}
.prod-footer{display:flex;align-items:center;justify-content:space-between;border-top:1px solid var(--soft);padding-top:1rem}
.prod-price{font-size:20px;font-weight:800;color:var(--navy)}
.btn-ver{font-size:13px;font-weight:700;color:var(--navy-light);border:1.5px solid var(--soft2);background:transparent;border-radius:var(--radius);padding:8px 16px}

/* FORMULARIOS VENDER */
.form-card{background:var(--white);border:1.5px solid var(--soft2);border-radius:var(--radius-lg);padding:2rem;max-width:600px;margin:0 auto}
.f-lbl{font-size:11.5px;text-transform:uppercase;color:var(--navy);font-weight:700;display:block;margin-bottom:6px}
.f-inp{width:100%;padding:11px 13px;border-radius:var(--radius);border:1.5px solid var(--soft2);font-size:13.5px;margin-bottom:1.2rem;color:var(--navy)}
.f-txt{width:100%;height:80px;padding:11px 13px;border-radius:var(--radius);border:1.5px solid var(--soft2);font-size:13.5px;margin-bottom:1.2rem;font-family:inherit}

/* TRAZABILIDAD QR SCAN */
.scan-container{max-width:700px;margin:0 auto;background:var(--white);border:1.5px solid var(--soft2);border-radius:var(--radius-lg);overflow:hidden}
.scan-header{background:var(--green-bg);color:var(--green-text);padding:1rem 1.5rem;font-weight:700;display:flex;justify-content:space-between;align-items:center}
.scan-body{padding:2rem}
.timeline{margin-top:1.5rem;padding-left:1rem;border-left:2px solid var(--soft2)}
.timeline-item{position:relative;margin-bottom:1.5rem}
.timeline-item::before{content:'';position:absolute;left:-15px;top:4px;width:8px;height:8px;border-radius:50%;background:var(--navy-light)}
.timeline-title{font-size:13.5px;font-weight:700;color:var(--navy)}
.timeline-date{font-size:11px;color:var(--text3)}
.timeline-desc{font-size:12.5px;color:var(--text2)}

/* MODAL INTERACTIVO */
.modal-overlay{display:none;position:fixed;inset:0;z-index:200;background:rgba(5,15,30,0.85);align-items:flex-start;justify-content:center;padding:2rem 1rem;overflow-y:auto}
.modal-overlay.open{display:flex}
.modal-box{background:var(--white);border-radius:var(--radius-lg);width:100%;max-width:520px;box-shadow:0 24px 80px rgba(0,0,0,0.3);overflow:hidden;margin:auto}
.proto-screen{display:none;padding:1.5rem}
.proto-screen.active{display:block}
.m-head{background:var(--navy);padding:1.25rem;display:flex;align-items:center;justify-content:space-between;color:var(--white)}
.m-badge{font-size:11px;color:var(--gold-lt);font-weight:700;text-transform:uppercase;display:flex;align-items:center;gap:6px}
.live-dot{width:8px;height:8px;border-radius:50%;background:#4CAF50}
.m-close{background:none;border:none;color:white;font-size:24px;cursor:pointer}
.coin-row{display:flex;gap:1.2rem;align-items:center;margin-bottom:1rem}
.cert-vis-img{width:110px;height:75px;border-radius:4px;overflow:hidden;border:1px solid var(--soft2);background:#000}
.cert-vis-img img{width:100%;height:100%;object-fit:contain}
.cert-info h2{font-size:16px;font-weight:700}
.tag-auth{font-size:11px;background:var(--green-bg);color:var(--green-text);padding:3px 10px;border-radius:20px;font-weight:700;display:inline-block;margin-top:4px}
.divider{border:none;border-top:1px solid var(--soft);margin:1rem 0}
.dgrid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:1rem}
.dcell{background:var(--off-white);padding:10px;border-radius:var(--radius);border:1px solid var(--soft2)}
.dcell .l{color:var(--text3);font-size:10px;text-transform:uppercase;font-weight:600}
.dcell .v{font-weight:700;color:var(--navy);font-size:13px}
.radio-group{display:flex;flex-direction:column;gap:10px;margin-bottom:1.5rem}
.radio-box{border:1.5px solid var(--soft2);border-radius:var(--radius);padding:12px;display:flex;gap:12px;cursor:pointer;background:var(--off-white)}
.radio-box.active{border-color:var(--navy);background:var(--white)}
.radio-txt h4{font-size:13px;font-weight:700;color:var(--navy)}
.radio-txt p{font-size:11.5px;color:var(--text3)}
.mtabs{display:flex;gap:6px;margin-bottom:1.2rem}
.mtab{flex:1;padding:11px 6px;border-radius:var(--radius);border:1.5px solid var(--soft2);background:var(--off-white);font-size:12px;font-weight:700;cursor:pointer;text-align:center}
.mtab.active{border-color:var(--navy);background:var(--navy);color:var(--gold-lt)}
.card-wrapper{background:#F0F4F9;border:1.5px solid var(--soft2);border-radius:var(--radius);padding:1.25rem;margin-bottom:1.2rem}
.card-row{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.method-desc{font-size:12.5px;color:var(--text2);background:#F0F4F9;padding:12px;border-radius:var(--radius);margin-bottom:1.2rem;display:none}
.method-desc.active{display:block}
.btn-confirm{width:100%;padding:13px;border-radius:var(--radius);background:var(--navy);color:var(--gold-lt);border:none;font-size:14.5px;font-weight:800;cursor:pointer}
.proc-wrap{padding:4rem 1.5rem;text-align:center}
.spinner{width:48px;height:48px;border:4px solid var(--soft2);border-top-color:var(--navy);border-radius:50%;margin:0 auto 1.5rem;animation:spin .8s linear infinite}
@keyframes spin{to{transform:rotate(360deg)}}
.ok-wrap{padding:3rem 1.5rem;text-align:center}
.ok-circle{width:64px;height:64px;border-radius:50%;background:var(--green-bg);margin:0 auto 1.5rem;display:flex;align-items:center;justify-content:center;color:var(--green-text);font-size:24px;font-weight:bold}
.ok-folio{font-family:monospace;font-size:12px;background:var(--off-white);padding:10px;border-radius:var(--radius);border:1px solid var(--soft2);margin:1rem auto;max-width:300px}
.btn-pdf{padding:13px 26px;border-radius:var(--radius);background:var(--navy);color:var(--gold-lt);font-size:14.5px;font-weight:800;border:none;cursor:pointer;margin-top:1rem}
.pdf-toast{position:fixed;bottom:2rem;left:50%;transform:translateX(-50%);background:var(--navy);color:var(--gold-lt);padding:11px 22px;border-radius:var(--radius);font-size:13px;z-index:999;opacity:0;transition:opacity .3s;pointer-events:none}
.pdf-toast.show{opacity:1}

.success-banner{background:#EAF3DE;color:#2E6B0F;padding:12px;border-radius:8px;border:1px solid #8CBF50;margin-bottom:1.5rem;font-size:13px;display:none}
.qr-box-mock{background:#1A2332;color:#FFF;padding:1.5rem;border-radius:8px;text-align:center;margin-top:1rem;font-family:monospace;font-size:12px}
</style>
</head>
<body>

<header class="site-header">
  <div class="nav-inner">
    <div class="logo-wrap">
      <div class="logo-coin">MV</div>
      <div class="logo-text"><strong>MonedaViva</strong><span>Casa Moneda de Chile</span></div>
    </div>
  </div>
</header>

<nav class="main-nav-tabs">
  <div class="main-tab active" id="tabLinkCatalog" onclick="switchMainView('catalog')">🏪 Catálogo / Comprar</div>
  <div class="main-tab" id="tabLinkSell" onclick="switchMainView('sell')">📦 Vende tu Colección</div>
  <div class="main-tab" id="tabLinkVerify" onclick="switchMainView('verify')">🔍 Escanear y Validar QR</div>
</nav>

<section class="view-section active" id="viewCatalog">
  <div class="hero">
    <h1>Portal de Certificación QR Oficial</h1>
    <p>Verifica la autenticidad institucional e inicia la transferencia regulada de dominio.</p>
  </div>
  <div class="prod-grid" id="catalogGrid">
    <div class="prod-card" onclick="openPrototype('Impreso Conmemorativo: Margot Duhalde', '$12.990', 'Ana María Prado', 'Papel de Seguridad')">
      <div class="prod-img">
        <img src="image_129428.jpg" alt="Margot Duhalde">
        <span class="prod-tag">Colección Privada</span>
      </div>
      <div class="prod-info">
        <h3>Impreso Conmemorativo: Margot Duhalde</h3>
        <p>Propietario original vende esta pieza con dístico oficial ilustrado y trazabilidad integrada.</p>
        <div class="prod-qr-status">📱 QR Verificado: Certificación de Origen Activa</div>
        <div class="prod-footer">
          <div class="prod-price">$12.990 <span>CLP</span></div>
          <button class="btn-ver">Ver y Adquirir</button>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="view-section" id="viewSell">
  <div class="hero">
    <h1>Publica y Certifica tu Pieza</h1>
    <p>Sube tu coleccionable al marketplace. El sistema le asignará una firma y un QR inalterable.</p>
  </div>
  <div class="form-card">
    <div class="success-banner" id="sellSuccessBanner">✓ ¡Tu pieza se ha registrado con éxito! El ítem ya está visible en el Catálogo.</div>
    
    <label class="f-lbl">Nombre de tu Coleccionable</label>
    <input type="text" id="formTitle" class="f-inp" placeholder="Ej: Billete Conmemorativo Margot Duhalde Especial">

    <label class="f-lbl">Precio de Venta (CLP)</label>
    <input type="number" id="formPrice" class="f-inp" placeholder="12990">

    <label class="f-lbl">Tu Nombre Completo (Vendedor)</label>
    <input type="text" id="formSeller" class="f-inp" value="Carlos Mendoza Fuentes">

    <label class="f-lbl">Estado Físico de la Pieza</label>
    <input type="text" id="formCondition" class="f-inp" value="Perfecto Estado (Mint)">

    <label class="f-lbl">Descripción Adicional</label>
    <textarea id="formDesc" class="f-txt" placeholder="Describe el estado de conservación..."></textarea>

    <button class="btn-confirm" onclick="executePublish()">Generar Firma y Publicar en Marketplace</button>

    <div id="qrOutputBlock" style="display:none; margin-top:1.5rem;">
      <label class="f-lbl">Etiqueta QR Antifraude generado:</label>
      <div class="qr-box-mock">
        ■■■■■■■■■■■■■■■■■<br>
        ■■  MONEDAVIVA  ■■<br>
        ■■  CERT-TRACE  ■■<br>
        ■■■■■■■■■■■■■■■■■<br>
        <span style="font-size:10px; color:var(--gold-lt);" id="lblNewId">ID: ITEM-49122</span>
      </div>
    </div>
  </div>
</section>

<section class="view-section" id="viewVerify">
  <div class="hero">
    <h1>Módulo de Escaneo e Historial</h1>
    <p>Audita la autenticidad real de la pieza. Contrasta que los datos coincidan.</p>
  </div>
  <div class="scan-container">
    <div class="scan-header">
      <span id="scanStatusBadge">🛡️ CERTIFICADO DE AUTENTICIDAD ACTIVO</span>
      <span style="font-size:12px; font-family:monospace;" id="scanCertCode">ID: CERT-2026-X992</span>
    </div>
    <div class="scan-body">
      <div class="coin-row">
        <div class="cert-vis-img"><img src="image_129428.jpg" alt="Duhalde"></div>
        <div>
          <h2 id="scanTitle">Impreso Conmemorativo: Margot Duhalde</h2>
          <p style="font-size:13px; color:var(--text2)">Propietario / Vendedor Actual: <strong id="scanSellerName">Ana María Prado</strong></p>
          <span class="tag-auth" style="margin-top:5px;">✓ Integridad de Datos Validada en Blockchain</span>
        </div>
      </div>
      <div class="divider"></div>
      <div class="dgrid">
        <div class="dcell"><div class="l">Precio Transacción</div><div class="v" id="scanPrice">$12.990 CLP</div></div>
        <div class="dcell"><div class="l">Estado de Conservación</div><div class="v" id="scanCondition">Papel de Seguridad</div></div>
      </div>
      <h3 style="font-size:14px; margin-top:1.5rem; color:var(--navy);">📜 Trazabilidad e Historial Inmutable:</h3>
      <div class="timeline" id="scanTimeline"></div>
    </div>
  </div>
</section>

<div class="modal-overlay" id="modalPrototype">
  <div class="modal-box">
    <div class="m-head">
      <div class="m-badge"><div class="live-dot"></div> MonedaViva Blockchain QR</div>
      <button class="m-close" onclick="closeModal()">&times;</button>
    </div>

    <div class="proto-screen active" id="screenDetail">
      <div class="coin-row">
        <div class="cert-vis-img"><img src="image_129428.jpg" alt="Duhalde"></div>
        <div class="cert-info">
          <h2 id="modalTitle">Impreso Conmemorativo: Margot Duhalde</h2>
          <p>Vendedor: <strong id="modalSeller">Ana María Prado</strong></p>
          <span class="tag-auth">✓ Firma Criptográfica Verificada</span>
        </div>
      </div>
      <div class="divider"></div>
      <div class="dgrid">
        <div class="dcell"><div class="l">Soporte Material</div><div class="v" id="modalCondition">Papel de Seguridad</div></div>
        <div class="dcell"><div class="l">Entidad Emisora</div><div class="v">Casa de Moneda S.A.</div></div>
      </div>
      <button class="btn-confirm" id="btnDetailAction" onclick="changeScreen('screenPayment')">Iniciar Adquisición ($12.990)</button>
    </div>

    <div class="proto-screen" id="screenPayment">
      <label class="f-lbl">Nombre del adquirente</label>
      <input type="text" id="buyerName" class="f-inp" value="Ana María Prado">
      <label class="f-lbl">RUT Identificador</label>
      <input type="text" id="buyerRut" class="f-inp" value="15.662.341-K">

      <label class="f-lbl">Logística y Custodia Física</label>
      <div class="radio-group">
        <div class="radio-box active" id="rBox1" onclick="setShipping('owner')">
          <input type="radio" id="shipOwner" name="shippingMethod" checked>
          <div class="radio-txt">
            <h4>El dueño anterior realiza el envío</h4>
            <p>Acuerdo de logística directo, privado y descentralizado.</p>
          </div>
        </div>
        <div class="radio-box" id="rBox2" onclick="setShipping('casamoneda')">
          <input type="radio" id="shipCasa" name="shippingMethod">
          <div class="radio-txt">
            <h4>Delegar custodia a Casa de Moneda</h4>
            <p>La institución centraliza la entrega cobrando coste base técnico.</p>
          </div>
        </div>
      </div>

      <label class="f-lbl">Medio de Pago Seguro</label>
      <div class="mtabs">
        <div class="mtab active" id="tab-tbk" onclick="selectMethod('tbk')">Transbank</div>
        <div class="mtab" id="tab-transfer" onclick="selectMethod('transfer')">Transferencia</div>
      </div>

      <div id="panel-tbk" class="card-wrapper">
        <label class="f-lbl" style="font-size:10px;">Número de Tarjeta</label>
        <input type="text" class="f-inp" value="4513 9982 4115 6320" style="margin-bottom:0.8rem;">
        <div class="card-row">
          <div><label class="f-lbl" style="font-size:10px;">Vencimiento</label><input type="text" class="f-inp" value="08/29" style="margin-bottom:0;"></div>
          <div><label class="f-lbl" style="font-size:10px;">CVV</label><input type="password" class="f-inp" value="441" style="margin-bottom:0;"></div>
        </div>
      </div>
      <div id="desc-transfer" class="method-desc">🏛️ Cuenta Corriente Banco de Chile Nº 99-1205-01. Resguardo institucional interino.</div>

      <button class="btn-confirm" onclick="processPayment()">Pagar y Confirmar Traspaso</button>
    </div>

    <div class="proto-screen" id="screenProcessing">
      <div class="proc-wrap">
        <div class="spinner"></div>
        <h3 id="processingTitle">Autorizando Transacción...</h3>
      </div>
    </div>

    <div class="proto-screen" id="screenSuccess">
      <div class="ok-wrap">
        <div class="ok-circle">✓</div>
        <h2>¡Propiedad Registrada!</h2>
        <div class="ok-folio">Folio Registro:<br><strong id="folioCode">CMMC-9002-2026</strong></div>
        <button class="btn-pdf" onclick="generateOfficialPDF()">📄 Descargar Certificado (PDF)</button>
      </div>
    </div>
  </div>
</div>

<div class="pdf-toast" id="toast">Documento PDF generado con éxito</div>

<script>
  let selectedMethodName = "Transbank Webpay Plus";
  let selectedShippingLabel = "El dueño anterior realiza el envío de forma directa";
  
  let currentActiveItem = {
    title: "Impreso Conmemorativo: Margot Duhalde",
    price: "$12.990",
    seller: "Ana María Prado",
    condition: "Papel de Seguridad",
    certCode: "CERT-2026-X992"
  };

  function switchMainView(viewId) {
    document.querySelectorAll('.view-section').forEach(s => s.classList.remove('active'));
    document.querySelectorAll('.main-tab').forEach(t => t.classList.remove('active'));
    if(viewId === 'catalog') {
      document.getElementById('viewCatalog').classList.add('active');
      document.getElementById('tabLinkCatalog').classList.add('active');
    } else if(viewId === 'sell') {
      document.getElementById('viewSell').classList.add('active');
      document.getElementById('tabLinkSell').classList.add('active');
    } else if(viewId === 'verify') {
      document.getElementById('viewVerify').classList.add('active');
      document.getElementById('tabLinkVerify').classList.add('active');
      loadVerifyView();
    }
  }

  function openPrototype(title, price, seller, condition) {
    currentActiveItem.title = title; currentActiveItem.price = price; currentActiveItem.seller = seller; currentActiveItem.condition = condition;
    document.getElementById('modalTitle').innerText = title;
    document.getElementById('modalSeller').innerText = seller;
    document.getElementById('modalCondition').innerText = condition;
    document.getElementById('btnDetailAction').innerText = "Iniciar Adquisición (" + price + ")";
    document.getElementById('modalPrototype').classList.add('open');
    changeScreen('screenDetail');
  }

  function closeModal() { document.getElementById('modalPrototype').classList.remove('open'); }
  function changeScreen(id) {
    document.querySelectorAll('.proto-screen').forEach(s => s.classList.remove('active'));
    document.getElementById(id).classList.add('active');
  }

  function setShipping(type) {
    document.getElementById('rBox1').classList.remove('active'); document.getElementById('rBox2').classList.remove('active');
    if(type === 'owner') {
      document.getElementById('rBox1').classList.add('active'); document.getElementById('shipOwner').checked = true;
      selectedShippingLabel = "El dueño anterior realiza el envío de forma directa (Acuerdo privado)";
    } else {
      document.getElementById('rBox2').classList.add('active'); document.getElementById('shipCasa').checked = true;
      selectedShippingLabel = "Delegado a Casa de Moneda de Chile (Logística Centralizada)";
    }
  }

  function selectMethod(method) {
    document.querySelectorAll('.mtab').forEach(t => t.classList.remove('active'));
    document.querySelectorAll('.method-desc').forEach(d => d.classList.remove('active'));
    document.getElementById('panel-tbk').style.display = 'none';
    document.getElementById('tab-' + method).classList.add('active');

    if(method === 'tbk') {
      document.getElementById('panel-tbk').style.display = 'block'; selectedMethodName = "Transbank Webpay Plus";
    } else if(method === 'transfer') {
      document.getElementById('desc-transfer').classList.add('active'); selectedMethodName = "Transferencia Bancaria";
    }
  }

  function processPayment() {
    document.getElementById('processingTitle').innerText = "Conectando con " + selectedMethodName + "...";
    changeScreen('screenProcessing');
    setTimeout(() => { 
      currentActiveItem.historyAdded = "Propiedad transferida a " + document.getElementById('buyerName').value + " via " + selectedMethodName;
      changeScreen('screenSuccess'); 
    }, 1200);
  }

  function executePublish() {
    const t = document.getElementById('formTitle').value || "Coleccionable Especial";
    const p = document.getElementById('formPrice').value || "12990";
    const s = document.getElementById('formSeller').value || "Carlos Mendoza";
    const c = document.getElementById('formCondition').value || "Buen Estado";
    const d = document.getElementById('formDesc').value || "Sin descripción";
    const randId = "ITEM-" + Math.floor(10000 + Math.random() * 90000);
    const randCert = "CERT-2026-" + Math.floor(1000 + Math.random() * 9000);

    currentActiveItem = { title: t, price: "$" + parseInt(p).toLocaleString('es-CL'), seller: s, condition: c, certCode: randCert, desc: d };

    const grid = document.getElementById('catalogGrid');
    const card = document.createElement('div');
    card.className = "prod-card";
    card.onclick = function() { openPrototype(t, "$" + parseInt(p).toLocaleString('es-CL'), s, c); };
    card.innerHTML = `
      <div class="prod-img"><img src="image_129428.jpg" alt="Img"><span class="prod-tag">Colección de \${s}</span></div>
      <div class="prod-info">
        <h3>\${t}</h3><p>\${d}</p><div class="prod-qr-status">📱 QR Verificado: Certificado Activo</div>
        <div class="prod-footer"><div class="prod-price">\${"$" + parseInt(p).toLocaleString('es-CL')} <span>CLP</span></div><button class="btn-ver">Ver y Adquirir</button></div>
      </div>`;
    grid.insertBefore(card, grid.firstChild);

    document.getElementById('lblNewId').innerText = "ID: " + randId + " / " + randCert;
    document.getElementById('qrOutputBlock').style.display = "block";
    document.getElementById('sellSuccessBanner').style.display = "block";
    window.scrollTo({top: 0, behavior: 'smooth'});
  }

  function loadVerifyView() {
    document.getElementById('scanTitle').innerText = currentActiveItem.title;
    document.getElementById('scanSellerName').innerText = currentActiveItem.seller;
    document.getElementById('scanPrice').innerText = currentActiveItem.price;
    document.getElementById('scanCondition').innerText = currentActiveItem.condition;
    document.getElementById('scanCertCode').innerText = "ID: " + currentActiveItem.certCode;

    const timeline = document.getElementById('scanTimeline');
    timeline.innerHTML = `
      <div class="timeline-item">
        <div class="timeline-title">Firma de Registro Inicial de Colección</div>
        <div class="timeline-date">Registrado por \${currentActiveItem.seller}</div>
        <div class="timeline-desc">Firma criptográfica auditada.</div>
      </div>`;
    if(currentActiveItem.historyAdded) {
      timeline.innerHTML += `
        <div class="timeline-item">
          <div class="timeline-title">Traspaso Legal de Dominio</div>
          <div class="timeline-date">MonedaViva Blockchain - Hoy</div>
          <div class="timeline-desc">\${currentActiveItem.historyAdded}. Fondos en resguardo técnico.</div>
        </div>`;
    }
  }

  function generateOfficialPDF() {
    const { jsPDF } = window.jspdf;
    const doc = new jsPDF();
    const buyer = document.getElementById('buyerName').value;
    const rut = document.getElementById('buyerRut').value;

    doc.setFillColor(11, 31, 58); doc.rect(0, 0, 210, 40, 'F');
    doc.setTextColor(255, 255, 255); doc.setFont("Helvetica", "bold"); doc.setFontSize(22);
    doc.text("CASA MONEDA DE CHILE", 20, 25);
    
    doc.setTextColor(11, 31, 58); doc.setFontSize(14); doc.text("CERTIFICADO OFICIAL DE ADQUISICIÓN Y DOMINIO DIGITAL", 20, 58);
    doc.setFont("Helvetica", "normal"); doc.setFontSize(10);
    doc.text("• Pieza Numismatica:   " + currentActiveItem.title, 24, 82);
    doc.text("• Vendedor Cedente:    " + currentActiveItem.seller, 24, 89);
    doc.text("• Adquirente Legal:    " + buyer + " (" + rut + ")", 24, 96);
    doc.text("• Logistica Fisica:    " + selectedShippingLabel, 24, 103);
    doc.text("• Codigo Registro:     " + currentActiveItem.certCode, 24, 110);

    doc.save("Certificado-" + currentActiveItem.title.replace(/ /g, "-") + ".pdf");
    const toast = document.getElementById('toast'); toast.classList.add('show');
    setTimeout(() => toast.classList.remove('show'), 3000);
  }
</script>
</body>
</html>
