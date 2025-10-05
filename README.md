<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Mi página web</title>
  <meta name="description" content="Una página web simple, responsive y fácil de editar." />
  <style>
    :root{--bg:#0f1724;--card:#111827;--accent:#06b6d4;--muted:#94a3b8;--glass: rgba(255,255,255,0.04)}
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,'Helvetica Neue',Arial}
    body{background:linear-gradient(180deg,#071023 0%, #0b1220 100%);color:#e6eef6;display:flex;align-items:center;justify-content:center;padding:32px}
    .container{width:100%;max-width:1000px}

    header{display:flex;align-items:center;justify-content:space-between;gap:16px;margin-bottom:28px}
    .logo{display:flex;align-items:center;gap:12px}
    .logo .mark{width:44px;height:44px;border-radius:10px;background:linear-gradient(135deg,var(--accent),#7c3aed);display:flex;align-items:center;justify-content:center;font-weight:700}
    nav a{color:var(--muted);text-decoration:none;margin-left:14px}
    nav a.cta{background:var(--accent);color:#07202a;padding:8px 12px;border-radius:8px;font-weight:600}

    .grid{display:grid;grid-template-columns:1fr 380px;gap:24px}
    @media(max-width:900px){.grid{grid-template-columns:1fr;}.sidebar{order:2}}

    .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.04);padding:22px;border-radius:14px;box-shadow: 0 6px 24px rgba(2,6,23,0.6)}

    h1{margin:0 0 8px;font-size:28px}
    p.lead{color:var(--muted);margin-top:0}

    .hero-actions{margin-top:18px;display:flex;gap:12px;flex-wrap:wrap}
    .btn{padding:10px 14px;border-radius:10px;display:inline-block;text-decoration:none;font-weight:600}
    .btn.primary{background:var(--accent);color:#04292f}
    .btn.ghost{border:1px solid rgba(255,255,255,0.06);color:var(--muted);background:transparent}

    .features{display:grid;grid-template-columns:repeat(2,1fr);gap:12px;margin-top:18px}
    @media(max-width:600px){.features{grid-template-columns:1fr}}
    .feature{padding:14px;border-radius:10px;background:var(--glass);border:1px solid rgba(255,255,255,0.02)}
    .feature h4{margin:0 0 6px}
    .muted{color:var(--muted);font-size:14px}

    .sidebar .meta-row{display:flex;align-items:center;justify-content:space-between;margin-bottom:10px}
    .input, textarea{width:100%;padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:inherit}
    .small{font-size:13px;color:var(--muted)}

    footer{margin-top:26px;color:var(--muted);text-align:center}

    /* small utility */
    .kbd{background:rgba(255,255,255,0.05);padding:6px 8px;border-radius:6px;font-weight:700}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="logo">
        <div class="mark">MW</div>
        <div>
          <div style="font-weight:700">Mi Web</div>
          <div class="small">Página ejemplo — editable</div>
        </div>
      </div>
      <nav>
        <a href="#features">Características</a>
        <a href="#contact">Contacto</a>
        <a class="cta" href="#">Publicar</a>
      </nav>
    </header>

    <main class="grid">
      <section>
        <div class="card">
          <h1>Construye tu página en minutos</h1>
          <p class="lead">Plantilla limpia, responsive y fácil de personalizar. Cambia el texto, colores y sube tus imágenes.</p>

          <div class="hero-actions">
            <a class="btn primary" id="downloadBtn">Descargar HTML</a>
            <a class="btn ghost" id="previewBtn">Abrir vista previa</a>
          </div>

          <div id="features" class="features">
            <div class="feature">
              <h4>Responsive</h4>
              <div class="muted">Funciona en móviles y escritorio sin librerías.</div>
            </div>
            <div class="feature">
              <h4>Fácil de editar</h4>
              <div class="muted">HTML y CSS claros para que puedas modificarlo rápido.</div>
            </div>
            <div class="feature">
              <h4>Ligera</h4>
              <div class="muted">Carga rápida y optimizada para performance.</div>
            </div>
            <div class="feature">
              <h4>Hosting</h4>
              <div class="muted">Listo para GitHub Pages, Netlify o Vercel.</div>
            </div>
          </div>

        </div>

        <div class="card" style="margin-top:16px">
          <h3 id="contact">Contacto</h3>
          <p class="small">Completa este formulario y pulsa "Publicar" para simular envío (ejemplo local).</p>
          <div style="display:grid;gap:10px;margin-top:12px">
            <input class="input" placeholder="Nombre" id="name">
            <input class="input" placeholder="Email" id="email">
            <textarea placeholder="Mensaje" rows="4" id="message" style="resize:vertical"></textarea>
            <div style="display:flex;gap:8px">
              <button class="btn primary" id="sendBtn">Enviar</button>
              <button class="btn ghost" id="clearBtn">Limpiar</button>
            </div>
            <div id="formStatus" class="small"></div>
          </div>
        </div>

      </section>

      <aside class="sidebar">
        <div class="card">
          <div class="meta-row"><div><strong>Estado</strong></div><div class="small">Borrador</div></div>
          <div class="meta-row"><div><strong>Tema</strong></div><div class="small">Oscuro</div></div>
          <hr style="border:none;border-top:1px solid rgba(255,255,255,0.03);margin:12px 0">
          <div class="small">Atajos</div>
          <div style="display:flex;gap:8px;margin-top:8px"><div class="kbd">Ctrl</div><div class="kbd">S</div></div>

          <hr style="border:none;border-top:1px solid rgba(255,255,255,0.03);margin:12px 0">
          <div class="small">Opciones</div>
          <div style="margin-top:10px;display:flex;gap:8px;flex-direction:column">
            <label class="small">Color primary
              <input type="color" id="themeColor" value="#06b6d4" style="margin-left:8px"></label>
            <label class="small">Mostrar secciones
              <select id="layoutSelect" style="margin-left:8px"><option value="full">Completo</option><option value="compact">Compacto</option></select></label>
          </div>
        </div>
      </aside>
    </main>

    <footer class="small">Hecho con ❤️ — plantilla de ejemplo</footer>
  </div>

<script>
// Interacciones básicas (sin servidor)
const themeColor = document.getElementById('themeColor');
themeColor.addEventListener('input', e=>{document.documentElement.style.setProperty('--accent', e.target.value)});

const clearBtn = document.getElementById('clearBtn');
clearBtn.addEventListener('click', ()=>{['name','email','message'].forEach(id=>document.getElementById(id).value='');document.getElementById('formStatus').textContent='Formulario limpiado.'});

const sendBtn = document.getElementById('sendBtn');
sendBtn.addEventListener('click', ()=>{
  const name=document.getElementById('name').value.trim();
  const email=document.getElementById('email').value.trim();
  const message=document.getElementById('message').value.trim();
  if(!name||!email||!message){document.getElementById('formStatus').textContent='Por favor completa todos los campos.';return}
  document.getElementById('formStatus').textContent='Gracias '+name+', (simulación) mensaje enviado.';
});

// Descargar el HTML actual (simula exportar)
const downloadBtn = document.getElementById('downloadBtn');
downloadBtn.addEventListener('click', ()=>{
  const html = '<!doctype html>' + '\n' + document.documentElement.outerHTML;
  const blob = new Blob([html], {type: 'text/html'});
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url; a.download = 'mi-pagina.html'; document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url);
});

// Vista previa en nueva pestaña
const previewBtn = document.getElementById('previewBtn');
previewBtn.addEventListener('click', ()=>{
  const html = '<!doctype html>' + '\n' + document.documentElement.outerHTML;
  const w = window.open(); w.document.open(); w.document.write(html); w.document.close();
});

// Atajo Ctrl+S para descargar
window.addEventListener('keydown', (e)=>{
  if((e.ctrlKey||e.metaKey) && e.key.toLowerCase()==='s'){e.preventDefault();downloadBtn.click();}
});
</script>
</body>
</html>
