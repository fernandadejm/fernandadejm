#fernandadejm.github.io
Project Website
<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Viajes — Explore &amp; Go</title>
  <meta name="description" content="Página de ejemplo para un sitio de viajes: destinos, galería y reservas." />
  <style>
    /* Reset ligero */
    *{box-sizing:border-box;margin:0;padding:0}
    :root{
      --accent:#0ea5a4; /* teal */
      --dark:#0f172a;
      --muted:#6b7280;
      --card:#ffffff;
      --glass: rgba(255,255,255,0.08);
      font-family:Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    body{background:linear-gradient(180deg,#f8fafc 0%, #eef2f7 100%);color:var(--dark);line-height:1.45}
    .container{max-width:1100px;margin:28px auto;padding:20px}

    /* Header */
    header{display:flex;align-items:center;justify-content:space-between;gap:16px}
    .brand{display:flex;align-items:center;gap:12px}
    .logo{width:52px;height:52px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#06b6d4);display:flex;align-items:center;justify-content:center;color:#fff;font-weight:700}
    nav a{margin-left:14px;text-decoration:none;color:var(--dark);font-weight:600}

    /* Hero */
    .hero{display:grid;grid-template-columns:1fr 420px;gap:28px;margin-top:22px;align-items:center}
    .hero-card{background:linear-gradient(180deg,rgba(255,255,255,0.9),#fff);padding:28px;border-radius:16px;box-shadow:0 6px 18px rgba(16,24,40,0.06)}
    .hero h1{font-size:28px;margin-bottom:10px}
    .hero p{color:var(--muted);margin-bottom:18px}
    .search{display:flex;gap:10px}
    .search input, .search select{padding:12px 14px;border-radius:10px;border:1px solid #e6e9ef;outline:none;font-size:14px}
    .btn{background:var(--accent);color:#fff;padding:12px 16px;border-radius:10px;border:none;cursor:pointer;font-weight:700}

    /* Destinations */
    .section{margin-top:28px}
    .grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
    .card{background:var(--card);border-radius:12px;overflow:hidden;box-shadow:0 6px 18px rgba(16,24,40,0.06)}
    .card img{width:100%;height:160px;object-fit:cover;display:block}
    .card .body{padding:12px}
    .tag{display:inline-block;padding:6px 8px;border-radius:999px;font-size:12px;background:var(--glass);color:var(--muted);margin-bottom:8px}
    .card h3{margin-bottom:8px}
    .card p{font-size:13px;color:var(--muted)}

    /* Gallery */
    .gallery{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;margin-top:14px}
    .gallery img{width:100%;height:120px;object-fit:cover;border-radius:8px}

    /* CTA */
    .cta{margin-top:22px;background:linear-gradient(90deg,rgba(14,165,164,0.08),rgba(6,182,212,0.06));padding:18px;border-radius:12px;display:flex;align-items:center;justify-content:space-between}

    /* Footer */
    footer{margin-top:36px;padding:20px 0;color:var(--muted);font-size:14px;border-top:1px solid #eef2f7}

    /* Responsive */
    @media (max-width:980px){
      .hero{grid-template-columns:1fr}
      .grid{grid-template-columns:repeat(2,1fr)}
      .gallery{grid-template-columns:repeat(3,1fr)}
    }
    @media (max-width:620px){
      .container{padding:12px}
      nav{display:none}
      .grid{grid-template-columns:1fr}
      .gallery{grid-template-columns:repeat(2,1fr)}
      .logo{width:44px;height:44px}
      .hero h1{font-size:22px}
    }

    /* small utilities */
    .muted{color:var(--muted)}
    .flex{display:flex;align-items:center}
    .gap{gap:10px}
    .pill{padding:8px 12px;border-radius:999px;background:#fff;border:1px solid #f1f5f9}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">EG</div>
        <div>
          <div style="font-weight:800">Explore &amp; Go</div>
          <div style="font-size:12px;color:var(--muted)">Tu próxima aventura empieza aquí</div>
        </div>
      </div>
      <nav>
        <a href="#destinos">Destinos</a>
        <a href="#galeria">Galería</a>
        <a href="#contacto">Contacto</a>
      </nav>
    </header>

    <section class="hero">
      <div class="hero-card">
        <h1>Descubre destinos increíbles — Viaja smart</h1>
        <p>Busca por ciudad, fecha y tipo de experiencia. Inspiración para viajes de aventura, playa, cultura y relajación.</p>
        <form class="search" onsubmit="event.preventDefault();findTrips()">
          <input id="where" type="text" placeholder="¿A dónde quieres ir? (ej. Cancún)" required />
          <select id="type">
            <option value="any">Cualquier tipo</option>
            <option value="beach">Playa</option>
            <option value="adventure">Aventura</option>
            <option value="city">Ciudad</option>
            <option value="nature">Naturaleza</option>
          </select>
          <button class="btn" type="submit">Buscar</button>
        </form>

        <div style="margin-top:16px" class="flex gap">
          <div class="pill"><strong>Mejor precio</strong> desde <span style="margin-left:8px;color:var(--accent)">$199</span></div>
          <div class="pill muted">Soporte 24/7</div>
        </div>

      </div>

      <aside>
        <div style="border-radius:12px;overflow:hidden;box-shadow:0 8px 24px rgba(2,6,23,0.06)">
          <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?q=80&w=900&auto=format&fit=crop&ixlib=rb-4.0.3&s=000" alt="Playa" style="width:100%;height:300px;object-fit:cover;display:block">
          <div style="padding:12px;background:#fff">
            <div style="font-weight:700">Oferta destacada: Riviera Maya</div>
            <div class="muted" style="font-size:13px;margin-top:6px">5 días · Vuelo + Hotel · Desde $199</div>
            <div style="margin-top:10px"><button class="btn">Ver oferta</button></div>
          </div>
        </div>
      </aside>

    </section>

    <section id="destinos" class="section">
      <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:12px">
        <h2>Destinos populares</h2>
        <div class="muted">Explora por categoría</div>
      </div>

      <div class="grid">
        <!-- Card 1 -->
        <article class="card">
          <img src="https://images.unsplash.com/photo-1526772662000-3f88f10405ff?q=80&w=1200&auto=format&fit=crop" alt="Paris">
          <div class="body">
            <span class="tag">Ciudad</span>
            <h3>París, Francia</h3>
            <p class="muted">Museos, cafés y la Torre Eiffel. Perfecto para una escapada urbana romántica.</p>
          </div>
        </article>

        <!-- Card 2 -->
        <article class="card">
          <img src="https://images.unsplash.com/photo-1501785888041-af3ef285b470?q=80&w=1200&auto=format&fit=crop" alt="Bali">
          <div class="body">
            <span class="tag">Playa</span>
            <h3>Bali, Indonesia</h3>
            <p class="muted">Playas, templos y surf. Ideal para relajarse y explorar la cultura local.</p>
          </div>
        </article>

        <!-- Card 3 -->
        <article class="card">
          <img src="https://images.unsplash.com/photo-1501785888041-a3ef285b470?q=80&w=1200&auto=format&fit=crop" alt="Montaña">
          <div class="body">
            <span class="tag">Naturaleza</span>
            <h3>Patagonia, Chile</h3>
            <p class="muted">Trekking épico entre glaciares y montañas. Para amantes de la aventura.</p>
          </div>
        </article>
      </div>
    </section>

    <section id="galeria" class="section">
      <h2>Galería</h2>
      <p class="muted" style="margin-top:6px">Fotos reales de viajeros</p>
      <div class="gallery" style="margin-top:12px">
        <img alt="gallery1" src="https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?q=80&w=800&auto=format&fit=crop">
        <img alt="gallery2" src="https://images.unsplash.com/photo-1494526585095-c41746248156?q=80&w=800&auto=format&fit=crop">
        <img alt="gallery3" src="https://images.unsplash.com/photo-1505765054644-4f8d0d7a8a1a?q=80&w=800&auto=format&fit=crop">
        <img alt="gallery4" src="https://images.unsplash.com/photo-1526772662000-3f88f10405ff?q=80&w=800&auto=format&fit=crop">
      </div>
    </section>

    <section class="section">
      <div class="cta">
        <div>
          <div style="font-weight:800">¿Listo para tu próxima aventura?</div>
          <div class="muted" style="margin-top:6px">Recibe ofertas y guías personalizadas — sin spam.</div>
        </div>
        <form onsubmit="event.preventDefault();subscribe()" style="display:flex;gap:8px;align-items:center">
          <input id="email" type="email" placeholder="Tu correo" required style="padding:10px 12px;border-radius:10px;border:1px solid #e6e9ef">
          <button class="btn" type="submit">Suscribirme</button>
        </form>
      </div>
    </section>

    <section id="contacto" class="section">
      <h2>Contacto</h2>
      <p class="muted">Escríbenos para preguntas sobre reservas o grupos.</p>
      <form style="margin-top:10px;display:grid;grid-template-columns:1fr 1fr;gap:10px;" onsubmit="event.preventDefault();sendMessage()">
        <input type="text" id="nombre" placeholder="Tu nombre" required style="padding:10px;border-radius:8px;border:1px solid #eef2f7">
        <input type="text" id="asunto" placeholder="Asunto" required style="padding:10px;border-radius:8px;border:1px solid #eef2f7">
        <textarea id="mensaje" placeholder="Escribe tu mensaje" style="grid-column:1/3;padding:10px;border-radius:8px;border:1px solid #eef2f7;min-height:110px"></textarea>
        <button class="btn" type="submit" style="grid-column:2/3;justify-self:end">Enviar</button>
      </form>
    </section>

    <footer>
      <div style="display:flex;justify-content:space-between;align-items:center;gap:20px;flex-wrap:wrap">
        <div>© <strong>Explore & Go</strong> — Hecho con ❤️ para viajeros</div>
        <div class="muted">Política de privacidad · Términos · Ayuda</div>
      </div>
    </footer>
  </div>

  <script>
    // Funciones simples de interacción (simuladas)
    function findTrips(){
      const where = document.getElementById('where').value.trim();
      const type = document.getElementById('type').value;
      if(!where) return alert('Escribe un destino para buscar.');
      alert(`Buscando viajes a ${where} — tipo: ${type}`);
    }

    function subscribe(){
      const email = document.getElementById('email').value.trim();
      if(!email) return alert('Introduce un correo válido.');
      alert('¡Gracias! Te hemos suscrito — revisa tu correo.');
      document.getElementById('email').value = '';
    }

    function sendMessage(){
      const nombre = document.getElementById('nombre').value.trim();
      const asunto = document.getElementById('asunto').value.trim();
      const mensaje = document.getElementById('mensaje').value.trim();
      if(!nombre || !asunto || !mensaje) return alert('Completa todos los campos.');
      alert('Mensaje enviado. Nos pondremos en contacto contigo pronto.');
      document.getElementById('nombre').value='';
      document.getElementById('asunto').value='';
      document.getElementById('mensaje').value='';
    }
  </script>
</body>
</html>
