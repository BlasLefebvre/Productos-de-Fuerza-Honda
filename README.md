<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Honda Power - Encontrá tu Equipo Ideal</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root{
      --honda-red: #E4002B;
      --bg: #f7f9fc;
      --card-bg: #ffffff;
      --muted: #6b7280;
      --whatsapp: #25D366;
      --success: #16a34a;
      --max-width: 1100px;
      --radius: 12px;
      font-family: 'Poppins', system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      background:var(--bg);
      color:#111827;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      padding:36px 20px;
      display:flex;
      justify-content:center;
      font-size:16px;
    }
    .container{
      width:100%;
      max-width:var(--max-width);
      background:var(--card-bg);
      border-radius:var(--radius);
      box-shadow:0 10px 40px rgba(15,23,42,0.08);
      padding:28px;
      display:grid;
      grid-template-columns: 1fr 300px; 
      gap:28px;
      align-items:start;
    }

    header{
      grid-column: 1 / -1;
      display:flex;
      justify-content:space-between;
      align-items:flex-start;
      gap:16px;
      margin-bottom:6px;
    }
    .brand{
      max-width:76%;
    }
    .brand h1{
      margin:0;
      color:var(--honda-red);
      font-size:24px; 
      font-weight:700;
      letter-spacing:0.2px;
    }
    .brand h2{
      margin:8px 0 0 0;
      color:#0f172a;
      font-size:16px; 
      font-weight:500;
      line-height:1.25;
    }
    .brand p{
      margin:12px 0 0 0;
      color:var(--muted);
      font-size:14px;
    }
    .tag {
      text-align:right;
      color:var(--muted);
      font-weight:600;
      font-size:13px;
    }

    form{
      background:transparent;
      padding:6px 0;
      display:flex;
      flex-direction:column;
      gap:16px;
      grid-column: 1 / 2;
    }

    .question{
      background:#fff;
      border-radius:10px;
      padding:14px;
      border:1px solid rgba(14,22,36,0.04);
    }
    .question h3{
      margin:0 0 8px 0;
      font-size:16px; 
      color:#0f172a;
      font-weight:600;
    }
    .examples{
      margin:6px 0 0 0;
      color:var(--muted);
      font-size:13px;
      padding-bottom: 8px; 
      border-bottom: 1px solid #eee;
    }
    .options{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      margin-top:10px;
    }
    
    .info-aclaracion {
        margin-top: 15px;
        padding: 10px 14px;
        border-radius: 8px;
        background: #f0f4f8;
        border-left: 4px solid var(--honda-red);
        font-size: 13px;
        color: #374151;
        line-height: 1.5;
        font-weight: 500;
    }
    .info-aclaracion p { margin: 0; }
    .info-aclaracion strong { color: var(--honda-red); }


    /* Styled radio pill */
    .option{
      display:flex;
      align-items:flex-start;
      gap:10px;
      background:#fbfdff;
      padding:8px 12px;
      border-radius:10px;
      border:1px solid rgba(14,22,36,0.03);
      cursor:pointer;
      min-width:180px;
      transition: border-color 0.2s;
    }
    input[type="radio"]:checked + div .label-main { color: var(--honda-red); }

    .option input[type="radio"]{
      appearance:none;
      -webkit-appearance:none;
      width:18px;
      height:18px;
      border-radius:50%;
      border:2px solid #cbd5e1;
      display:inline-block;
      position:relative;
      margin-top:2px;
      flex:0 0 auto;
    }
    .option input[type="radio"]:checked{
      border-color:var(--honda-red);
      box-shadow:inset 0 0 0 4px rgba(228,0,43,0.08); 
    }
    .option .label-main{
      font-size:14px;
      color:#0f172a;
      font-weight:600;
      transition: color 0.2s;
    }
    .option .label-sub{
      display:block;
      margin-top:4px;
      color:var(--muted);
      font-size:12px;
      font-weight:400;
    }

    .submit-row{
      display:flex;
      justify-content:center;
      gap:12px;
      margin-top:10px;
      align-items:center;
      padding-bottom: 10px;
    }
    
    button.primary{
      background:var(--honda-red);
      color:white;
      border:0;
      padding:14px 24px;
      border-radius:10px;
      cursor:pointer;
      font-weight:700;
      font-size:16px;
      box-shadow:0 10px 25px rgba(228,0,43,0.15); 
      transition: background-color 0.2s, transform 0.1s;
    }
    button.primary:hover{background: #c40025}
    button.primary:active{transform:translateY(1px)}
    
    /* Sidebar - Panel lateral estático */
    .panel{
      grid-column: 2 / 3;
      position: sticky;
      top: 20px;
      background:#fbfdff;
      border-radius:10px;
      padding:18px;
      border:1px solid rgba(14,22,36,0.04);
      min-height:100px;
    }
    .panel h3{margin:0 0 8px 0;color:#0f172a;font-size:15px; font-weight:600;}
    #glosario-content{
      color:#374151;
      font-size:14px;
      line-height:1.4;
    }

    /* Result as a prominent box/pseudo-modal */
    #resultado{
      display:none;
      grid-column: 1 / 3;
      margin-top:14px;
      border-radius:var(--radius);
      padding:20px;
      border:3px solid var(--success);
      background:linear-gradient(180deg, #e6ffe6, #ffffff); 
      box-shadow:0 15px 40px rgba(22, 163, 74, 0.15);
    }
    #resultado.visible{display:block}

    .result-grid{
      display:grid;
      grid-template-columns:120px 1fr;
      gap:16px;
      align-items:start;
    }
    
    /* Image Container Styles */
    .image-container{
      width:120px;
      height:120px;
      border-radius:8px;
      background:#fafafa;
      border:1px solid rgba(14,22,36,0.06);
      overflow:hidden;
    }

    .product-title{
      font-weight:800;
      color:var(--honda-red);
      margin:0 0 4px 0;
      font-size:20px;
    }
    .product-specs{
      font-weight:600;
      color:#0f172a;
      margin:0 0 4px 0;
      font-size:14px;
    }
    .product-price{
      font-weight:700;
      color:#0f172a;
      margin:0 0 10px 0;
      font-size:17px;
    }
    .product-advantage{
      color:#064e3b; 
      font-size:14px;
      margin:0 0 12px 0;
      font-weight:600;
      border-top: 1px solid #c8e6c8;
      padding-top: 10px;
    }
    .meta{
      display:none;
    }
    .whatsapp{
      display:inline-block;
      margin-top:12px;
      background:var(--whatsapp);
      color:white;
      padding:12px 18px;
      border-radius:10px;
      text-decoration:none;
      font-weight:700;
      font-size:16px;
      transition: background-color 0.2s;
    }

    .error{
      color:#b91c1c;
      font-weight:700;
      font-size:14px;
      padding: 10px 0;
    }
    
    .loading-placeholder {
        color: var(--muted); 
        font-style: italic; 
        width: 100%; 
        padding: 10px 0; 
        font-size: 14px;
    }

    @media (max-width:980px){
      .container{grid-template-columns:1fr; padding:18px}
      header{grid-column: 1 / 2;}
      form{grid-column: 1 / 2;}
      .panel{grid-row: 3 / 4; grid-column: 1 / 2; margin-top: 10px; position: relative; top: 0;}
      #resultado{grid-column: 1 / 2;}
      .result-grid{grid-template-columns:1fr}
      .image-container{width:100%;height:160px}
    }
  </style>
</head>
<body>
  <main class="container" role="main">
    <header>
      <div class="brand">
        <h1>Honda Power - Encontrá tu Equipo Ideal</h1>
        <h2>Asesor Digital Rápido. Seleccioná el tipo de equipo, definí la potencia y el uso.</h2>
        <p>Precisión técnica. Encontrá tu equipo profesional con la ingeniería y respaldo de Honda.</p>
      </div>
      <div class="tag">
        Asesor Honda<br/><small style="color:var(--muted)">Profesional • Rápido • Confiable</small>
      </div>
    </header>

    <form id="asesor" autocomplete="off" novalidate>
            <div class="question" id="p1">
        <h3>1. ¿Qué Tipo de Equipo Motorizado Necesitas?</h3>
        <div class="examples">Define el equipo base para su aplicación principal.</div>
        <div class="options" role="radiogroup" aria-labelledby="p1">
          <label class="option"><input type="radio" name="uso" value="Generador" required><div><span class="label-main">Generador de Energía</span><span class="label-sub">Respaldo, obra, equipos electrónicos sensibles.</span></div></label>
          <label class="option"><input type="radio" name="uso" value="Motobomba"><div><span class="label-main">Motobomba de Agua</span><span class="label-sub">Drenaje, transferencia de fluidos o elevación.</span></div></label>
          <label class="option"><input type="radio" name="uso" value="Motor Estacionario"><div><span class="label-main">Motor Estacionario</span><span class="label-sub">Propulsor independiente para acople industrial o reemplazo.</span></div></label>
          <label class="option"><input type="radio" name="uso" value="Cortadora de Césped"><div><span class="label-main">Cortadora de Césped</span><span class="label-sub">Mantenimiento de jardines y parques.</span></div></label>
          <label class="option"><input type="radio" name="uso" value="Motoguadaña"><div><span class="label-main">Motoguadaña / Desmalezadora</span><span class="label-sub">Corte de maleza, pasto alto y bordes.</span></div></label>
          <label class="option"><input type="radio" name="uso" value="Sopladora"><div><span class="label-main">Sopladora</span><span class="label-sub">Limpieza y recolección de hojas y escombros.</span></div></label>
          <label class="option"><input type="radio" name="uso" value="Sierra/Cortacerco"><div><span class="label-main">Sierra / Cortacerco</span><span class="label-sub">Herramientas de poda y recorte (principalmente a batería).</span></div></label>
          <label class="option"><input type="radio" name="uso" value="Fumigadora"><div><span class="label-main">Mochila Fumigadora</span><span class="label-sub">Rociado de fertilizantes, control de plagas y herbicidas.</span></div></label>
        </div>
      </div>
      
            <div class="question" id="p2"> 
        <h3>2. ¿Qué Capacidad o Potencia Requieres?</h3>
        <div class="examples" id="p2-examples">Selecciona el rango de rendimiento más adecuado para tu proyecto.</div>
        <div class="options" role="radiogroup" aria-labelledby="p2" id="p2-options">
          <p class="loading-placeholder">Selecciona un Tipo de Equipo en el paso 1.</p>
        </div>
        <div class="info-aclaracion" id="p2-aclaracion">
            <p><strong>Aclaración Técnica:</strong> Por favor, selecciona un tipo de equipo en el paso 1 para ver los términos técnicos clave que se aplicarán a tu elección.</p>
        </div>
      </div>

            <div class="question" id="p3">
        <h3>3. ¿Cuál será la Frecuencia y Duración de Uso?</h3>
        <div class="examples" id="p3-examples">Define la intensidad de trabajo para seleccionar el grado de motor o el tipo de alimentación.</div>
        <div class="options" role="radiogroup" aria-labelledby="p3" id="p3-options">
          <p class="loading-placeholder">Selecciona un Tipo de Equipo en el paso 1.</p>
        </div>
        <div class="info-aclaracion" id="p3-aclaracion">
            <p><strong>Diferenciador:</strong> Selecciona un tipo de equipo en el paso 1 para ver la diferencia de durabilidad aplicada.</p>
        </div>
      </div>

            <div class="question" id="p4">
        <h3>4. ¿Cuál es tu Prioridad de Diseño y Funcionalidad?</h3>
        <div class="examples" id="p4-examples">Esto ayuda a filtrar entre modelos estándar, insonorizados, autopropulsados o con capacidad de sólidos.</div>
        <div class="options" role="radiogroup" aria-labelledby="p4" id="p4-options">
          <p class="loading-placeholder">Selecciona un Tipo de Equipo en el paso 1.</p>
        </div>
      </div>

            <div class="question" id="p5">
        <h3>5. ¿Cuál es el Entorno Principal de Operación?</h3>
        <div class="examples">El entorno define las exigencias de portabilidad, protección (IP) y la conexión eléctrica requerida.</div>
        <div class="options" role="radiogroup" aria-labelledby="p5">
          <label class="option"><input type="radio" name="entorno" value="Urbano / Residencial" required><div><span class="label-main">Urbano / Residencial (220V)</span><span class="label-sub">Hogar, mantenimiento de jardines o comercios pequeños. Demanda bajo ruido.</span></div></label>
          <label class="option"><input type="radio" name="entorno" value="Rural / Agropecuario"><div><span class="label-main">Rural / Agropecuario</span><span class="label-sub">Riego, grandes extensiones, aislamiento. Requiere robustez y autonomía de motor.</span></div></label>
          <label class="option"><input type="radio" name="entorno" value="Industrial / Comercial"><div><span class="label-main">Industrial / Comercial (380V)</span><span class="label-sub">Fábricas o equipos que operan con conexión **Trifásica (380V)**.</span></div></label>
          <label class="option"><input type="radio" name="entorno" value="Obras / Construcción"><div><span class="label-main">Obras / Construcción</span><span class="label-sub">Sitios de trabajo rudo, alta exposición a polvo. Prioriza motor **GX** y manejo de sólidos.</span></div></label>
        </div>
      </div>

      <div class="submit-row">
        <button type="submit" class="primary">Obtener Recomendación Honda</button>
      </div>

      <div id="resultado" role="status" aria-live="polite"></div>
    </form>

    <aside class="panel" aria-label="Información adicional">
      <h3>📢 Asesoramiento Profesional</h3>
      <div id="glosario-content">
        <p>Este sistema te da una **guía rápida**. Al presionar el botón de **WhatsApp** con tu resultado, nuestro equipo técnico te asistirá para validar tus necesidades (ej: el **kVA** de arranque de tus máquinas) antes de la compra final.</p>
      </div>
      <hr style="border:0; border-top:1px solid #ddd; margin:10px 0;"/>
      <p style="margin:0;color:var(--muted);font-size:13px; font-style:italic;">Recomendación orientativa basada en ingeniería Honda. Los precios son estimados. Consultar stock y disponibilidad por WhatsApp.</p>
    </aside>
  </main>

  <script>
    (function(){
      const form = document.getElementById('asesor');
      const resultado = document.getElementById('resultado');

      // !!! ATENCIÓN: REEMPLAZAR ESTE VALOR ANTES DE PUBLICAR !!!
      const WHATSAPP_NUMBER = '54911xxxxxxxx'; 
      const IS_WHATSAPP_CONFIGURED = (WHATSAPP_NUMBER !== '54911xxxxxxxx'); 

      // Mapeo de URLs de imágenes y PRODUCTOS
      const PHOTO_PLACEHOLDERS = { 
        'EG6500CXS-RAH': 'https://picsum.photos/seed/EG6500/120/120', 'EU22IT-RA': 'https://picsum.photos/seed/EU22I/120/120', 'ET12000K1-RRH': 'https://picsum.photos/seed/ET12000/120/120', 'EZ3000CX- RA': 'https://picsum.photos/seed/EZ3000/120/120', 
        'GX390H2-QX': 'https://picsum.photos/seed/GX390/120/120', 'GX160H2-SX1': 'https://picsum.photos/seed/GX160/120/120', 'GP160H-SH1': 'https://picsum.photos/seed/GXR120/120/120',
        'WB20XH2-DR': 'https://picsum.photos/seed/WB20XH2/120/120', 'WB30XH2-DRX': 'https://picsum.photos/seed/WB30XH2/120/120', 'WH20XT-DFX': 'https://picsum.photos/seed/WH20XT/120/120', 'WL20XH': 'https://picsum.photos/seed/WL20XH/120/120', 'WL30XH-DRX': 'https://picsum.photos/seed/WL30XH/120/120', 'WT30XK4-DE': 'https://picsum.photos/seed/WT30XK4/120/120', 'WT40XK3-DE': 'https://picsum.photos/seed/WT40XK3/120/120',
        'HRN216-PKA': 'https://picsum.photos/seed/HRN216P/120/120', 'HRN216-VKA': 'https://picsum.photos/seed/HRN216V/120/120', 'HRX217K6-VKAA': 'https://picsum.photos/seed/HRX217/120/120',
        'HHT36': 'https://picsum.photos/seed/HHT36/120/120', 'UMK425T-UTDT': 'https://picsum.photos/seed/UMK425/120/120', 'UMK435T-UEDT': 'https://picsum.photos/seed/UMK435/120/120', 'UMK450T-UEDT': 'https://picsum.photos/seed/UMK450/120/120',
        'HHB25-ET1': 'https://picsum.photos/seed/HHB25/120/120', 'HHB36': 'https://picsum.photos/seed/HHB36/120/120',
        'HHH36': 'https://picsum.photos/seed/HHH36/120/120', 'HHC36': 'https://picsum.photos/seed/HHC36/120/120',
        'WJR2525T1-GCS': 'https://picsum.photos/seed/WJR2525/120/120', 'WJR4025T-GCS': 'https://picsum.photos/seed/WJR4025/120/120',
      };
      
      const PRODUCTS = { 
        // GENERADORES 
        'EU22IT-RA': { producto: 'HONDA GENERADOR EU22IT-RA (Inverter)', precio: '~$950.000 ARS', specs: 'Motor **GX120** | Potencia Máx. **2.2 kVA** | Voltaje **220V Monofásico** | **Inverter**', ventaja: 'Diseño **Inverter insonorizado**. Genera onda pura, ideal para electrónica sensible y uso residencial.', photoUrl: PHOTO_PLACEHOLDERS['EU22IT-RA'] },
        'EZ3000CX- RA': { producto: 'HONDA GENERADOR EZ3000CX- RA (Estándar GP)', precio: '~$700.000 ARS', specs: 'Motor **GP200** | Potencia Máx. **2.8 kVA** | Voltaje **220V Monofásico** | **Serie GP**', ventaja: 'Línea de uso general. Buen balance entre potencia y costo. Ideal para tareas ocasionales y respaldo básico.', photoUrl: PHOTO_PLACEHOLDERS['EZ3000CX- RA'] },
        'EG6500CXS-RAH': { producto: 'HONDA GENERADOR EG6500CXS-RAH (Alta Potencia GX)', precio: '~$1.800.000 ARS', specs: 'Motor **GX390** | Potencia Máx. **5.5 kVA** | Voltaje **220V Monofásico** | **D-AVR**', ventaja: 'Motor GX de uso profesional. Máxima potencia monofásica y regulación D-AVR para trabajo continuo.', photoUrl: PHOTO_PLACEHOLDERS['EG6500CXS-RAH'] },
        'ET12000K1-RRH': { producto: 'HONDA GENERADOR ET12000K1-RRH (Trifásico)', precio: '~$3.500.000 ARS', specs: 'Motor **GX630 (V-Twin)** | Potencia Máx. **10.0 kVA** | Voltaje **220/380V Trifásico**', ventaja: 'El equipo más robusto. Doble motor V-Twin para alto rendimiento industrial y única solución para conexiones **Trifásicas 380V**.', photoUrl: PHOTO_PLACEHOLDERS['ET12000K1-RRH'] },
        // MOTOBOMBAS
        'WB20XH2-DR': { producto: 'HONDA MOTOBOMBA WB20XH2-DR (Agua Limpia 2" GX)', precio: '~$380.000 ARS', specs: 'Motor **GX160** | Caudal Máx. **670 L/min** | Conexión **2"** | Tipo **Agua Limpia**', ventaja: 'Alto caudal en tamaño compacto, ideal para riego y transferencia de agua limpia con el motor profesional GX.', photoUrl: PHOTO_PLACEHOLDERS['WB20XH2-DR'] },
        'WL20XH': { producto: 'HONDA MOTOBOMBA WL20XH (Agua Limpia 2" GP)', precio: '~$350.000 ARS', specs: 'Motor **GP160** | Caudal Máx. **600 L/min** | Conexión **2"** | Tipo **Agua Limpia (Uso General)**', ventaja: 'Opción económica (Serie GP) para uso ocasional o semi-frecuente, manteniendo un excelente caudal de agua limpia.', photoUrl: PHOTO_PLACEHOLDERS['WL20XH'] },
        'WB30XH2-DRX': { producto: 'HONDA MOTOBOMBA WB30XH2-DRX (Agua Limpia 3" GX)', precio: '~$480.000 ARS', specs: 'Motor **GX200** | Caudal Máx. **1100 L/min** | Conexión **3"** | Tipo **Agua Limpia**', ventaja: 'Máximo caudal de agua limpia (3") para drenajes muy rápidos y grandes volúmenes de transferencia.', photoUrl: PHOTO_PLACEHOLDERS['WB30XH2-DRX'] },
        'WL30XH-DRX': { producto: 'HONDA MOTOBOMBA WL30XH-DRX (Agua Limpia 3" GP)', precio: '~$440.000 ARS', specs: 'Motor **GP200** | Caudal Máx. **1000 L/min** | Conexión **3"** | Tipo **Agua Limpia (Uso General)**', ventaja: 'Excelente rendimiento de 3" en línea económica (GP). Ideal para agricultores con uso estacional.', photoUrl: PHOTO_PLACEHOLDERS['WL30XH-DRX'] },
        'WH20XT-DFX': { producto: 'HONDA MOTOBOMBA WH20XT-DFX (Alta Presión)', precio: '~$450.000 ARS', specs: 'Motor **GX160** | Presión Máx. **4.5 Bar (45m)** | Conexión **2"** | Tipo **Alta Presión**', ventaja: 'Especializada en altura. Imprescindible para sistemas de aspersión y elevación de agua a larga distancia/altura.', photoUrl: PHOTO_PLACEHOLDERS['WH20XT-DFX'] },
        'WT30XK4-DE': { producto: 'HONDA MOTOBOMBA WT30XK4-DE (Aguas Sucias 3")', precio: '~$750.000 ARS', specs: 'Motor **GX270** | Caudal Máx. **1300 L/min** | Paso de Sólidos **28 mm (Trash)**', ventaja: 'Ideal para obras y emergencias. Motor profesional GX y manejo de sólidos de hasta 28mm (3").', photoUrl: PHOTO_PLACEHOLDERS['WT30XK4-DE'] },
        'WT40XK3-DE': { producto: 'HONDA MOTOBOMBA WT40XK3-DE (Aguas Sucias 4")', precio: '~$850.000 ARS', specs: 'Motor **GX340** | Caudal Máx. **1640 L/min** | Paso de Sólidos **40 mm (Trash)**', ventaja: 'La motobomba más potente. Máxima capacidad de caudal y manejo de sólidos grandes (4"). Para los trabajos más exigentes.', photoUrl: PHOTO_PLACEHOLDERS['WT40XK3-DE'] },
        // MOTORES ESTACIONARIOS
        'GX160H2-SX1': { producto: 'HONDA MOTOR ESTACIONARIO GX160H2-SX1 (5.5 HP)', precio: '~$160.000 ARS', specs: 'Serie **GX (Profesional)** | Potencia Neta **5.5 HP** | Cilindrada **163 cc**', ventaja: 'Motor de rendimiento estándar. Confiabilidad GX para uso frecuente en máquinas de mediana potencia.', photoUrl: PHOTO_PLACEHOLDERS['GX160H2-SX1'] },
        'GX390H2-QX': { producto: 'HONDA MOTOR ESTACIONARIO GX390H2-QX (13 HP)', precio: '~$280.000 ARS', specs: 'Serie **GX (Profesional)** | Potencia Neta **13 HP** | Cilindrada **389 cc**', ventaja: 'Máximo torque y durabilidad. Esencial para equipos industriales con alta demanda de potencia continua.', photoUrl: PHOTO_PLACEHOLDERS['GX390H2-QX'] },
        'GP160H-SH1': { producto: 'HONDA MOTOR ESTACIONARIO GP160H-SH1 (5 HP)', precio: '~$120.000 ARS', specs: 'Serie **GP (Uso General)** | Potencia Neta **5 HP** | Uso **Ocasional**', ventaja: 'Opción económica para uso ocasional. Ideal para reemplazos o aplicaciones que no requieren la robustez extrema de la serie GX.', photoUrl: PHOTO_PLACEHOLDERS['GP160H-SH1'] },
        // CORTADORAS DE CÉSPED
        'HRN216-PKA': { producto: 'HONDA CORTADORA DE CESPED HRN216-PKA (Empuje)', precio: '~$450.000 ARS', specs: 'Motor **GVC170** | Sistema **Empuje** | Ancho de Corte **21"**', ventaja: 'Modelo a empuje. Combina el motor de alto rendimiento GVC170 con un diseño robusto y económico para jardines planos.', photoUrl: PHOTO_PLACEHOLDERS['HRN216-PKA'] },
        'HRN216-VKA': { producto: 'HONDA CORTADORA DE CESPED HRN216-VKA (Autopropulsada Estándar)', precio: '~$600.000 ARS', specs: 'Motor **GVC170** | Sistema **Autopropulsado** | **Velocidad Variable**', ventaja: 'Ideal para terrenos medianos e inclinados. El sistema de tracción variable elimina el esfuerzo, aumentando la productividad.', photoUrl: PHOTO_PLACEHOLDERS['HRN216-VKA'] },
        'HRX217K6-VKAA': { producto: 'HONDA CORTADORA DE CESPED HRX217K6-VKAA (Autopropulsada Premium)', precio: '~$950.000 ARS', specs: 'Motor **GCVX200** | Sistema **Autopropulsado (Select Drive)** | **Versamow™**', ventaja: 'La tope de gama. Versamow™ integrado para mulching y embolsado. Máxima calidad de corte y confort profesional.', photoUrl: PHOTO_PLACEHOLDERS['HRX217K6-VKAA'] },
        // HERRAMIENTAS LIGERAS
        'HHT36': { producto: 'HONDA DESMALEZADORA A BATERÍA HHT36', precio: '~$180.000 ARS', specs: 'Alimentación **Batería** | **Cero Emisiones** | Bajo Ruido', ventaja: 'Comodidad de batería con el respaldo Honda. Perfecta para residencias y mantenimiento silencioso de jardines pequeños.', photoUrl: PHOTO_PLACEHOLDERS['HHT36'] },
        'UMK425T-UTDT': { producto: 'HONDA MOTOGUADAÑA UMK425T-UTDT (25cc)', precio: '~$250.000 ARS', specs: 'Motor **GX25** | **4 Tiempos** | Uso **Semi-Profesional**', ventaja: 'Potencia intermedia 4T para trabajos frecuentes, sin mezcla de aceite.', photoUrl: PHOTO_PLACEHOLDERS['UMK425T-UTDT'] },
        'UMK435T-UEDT': { producto: 'HONDA MOTOGUADAÑA UMK435T-UEDT (35cc)', precio: '~$320.000 ARS', specs: 'Motor **GX35** | **4 Tiempos** | Uso **Profesional Intensivo**', ventaja: 'El modelo estándar profesional. Máxima potencia y resistencia para largas jornadas de desmalezado continuo.', photoUrl: PHOTO_PLACEHOLDERS['UMK435T-UEDT'] },
        'UMK450T-UEDT': { producto: 'HONDA MOTOGUADAÑA UMK450T-UEDT (50cc)', precio: '~$380.000 ARS', specs: 'Motor **GX50** | **4 Tiempos** | Uso **Heavy Duty**', ventaja: 'La desmalezadora 4T más potente. Recomendada para trabajos industriales y terrenos extremadamente duros.', photoUrl: PHOTO_PLACEHOLDERS['UMK450T-UEDT'] },
        'HHB25-ET1': { producto: 'HONDA SOPLADOR HHB25-ET1 (4T Mano)', precio: '~$220.000 ARS', specs: 'Motor **GX25** | **4 Tiempos** | Tipo **Mano**', ventaja: 'Sopladora a gasolina 4T de alta velocidad. Máximo caudal de aire en un diseño de mano cómodo.', photoUrl: PHOTO_PLACEHOLDERS['HHB25-ET1'] },
        'HHB36': { producto: 'HONDA SOPLADOR A BATERÍA HHB36', precio: '~$150.000 ARS', specs: 'Alimentación **Batería** | **Cero Emisiones** | Bajo Ruido', ventaja: 'Limpieza rápida y silenciosa de hojas y residuos en áreas sensibles al ruido.', photoUrl: PHOTO_PLACEHOLDERS['HHB36'] },
        'HHH36': { producto: 'HONDA CORTACERCO A BATERÍA HHH36', precio: '~$190.000 ARS', specs: 'Alimentación **Batería** | **Cero Emisiones** | Cuchillas **Láser**', ventaja: 'Corte preciso y ergonómico sin cables ni combustible. Ideal para formas y setos.', photoUrl: PHOTO_PLACEHOLDERS['HHH36'] },
        'HHC36': { producto: 'HONDA ELECTROSIERRA HHC36', precio: '~$210.000 ARS', specs: 'Alimentación **Batería** | **Cero Emisiones** | Barra de **16"**', ventaja: 'Potente sierra de batería para podas y trabajos ligeros de corte.', photoUrl: PHOTO_PLACEHOLDERS['HHC36'] },
        'WJR2525T1-GCS': { producto: 'HONDA MOCHILA FUMIGADORA WJR2525T1-GCS (25cc)', precio: '~$300.000 ARS', specs: 'Motor **GX25** | **4 Tiempos** | Capacidad **25 cc**', ventaja: 'Modelo de bajo consumo y 4 tiempos. Ideal para uso general y agricultura pequeña. Liviana.', photoUrl: PHOTO_PLACEHOLDERS['WJR2525T1-GCS'] },
        'WJR4025T-GCS': { producto: 'HONDA MOCHILA FUMIGADORA WJR4025T-GCS (40cc)', precio: '~$450.000 ARS', specs: 'Motor **GX35** | **4 Tiempos** | Capacidad **40 cc**', ventaja: 'Máxima capacidad y presión para fumigación profesional de grandes extensiones agrícolas. Motor robusto GX35.', photoUrl: PHOTO_PLACEHOLDERS['WJR4025T-GCS'] },
      };

      // Opciones Condicionales para P2 (Potencia/Capacidad)
      const P2_OPTIONS = {
        'Generador': [
          { value: 'Inverter_BajoRuido', label: 'Bajo Ruido / Inverter (2.2 kVA)', sub: 'Generación Inverter de onda pura para equipos electrónicos sensibles.' },
          { value: 'Monofásico_Medio', label: 'Potencia Estándar Monofásica (2.8 kVA)', sub: 'Respaldo básico de hogar o herramientas eléctricas de bajo consumo.' },
          { value: 'Monofásico_Alto', label: 'Alta Potencia Monofásica (5.5 kVA)', sub: 'Comercios, pequeños talleres o respaldo de hogar completo.' },
          { value: 'Trifásico_Alto', label: 'Máxima Potencia Trifásica (10.0 kVA)', sub: 'Para tableros y maquinaria que operan con **380V**. Uso industrial.' },
        ],
        'Motobomba': [
          { value: 'Limpia_Caudal_2p', label: 'Agua Limpia - Caudal 2" (670 L/min)', sub: 'Mover grandes volúmenes de agua limpia a baja altura.' },
          { value: 'Limpia_Caudal_3p', label: 'Agua Limpia - Caudal 3" (1100 L/min)', sub: 'Máximo volumen de agua limpia para riego o drenaje rápido.' },
          { value: 'Limpia_Presión', label: 'Agua Limpia - Alta Presión (45 metros)', sub: 'Elevar el fluido a gran altura o alimentar sistemas de riego por aspersión.' },
          { value: 'Sucia_Caudal', label: 'Aguas Sucias (Trash) - Sólidos', sub: 'Drenaje de fluidos con sólidos, arena, lodo. Imprescindible en obras.' }
        ],
        'Motor Estacionario': [
          { value: 'Reemplazo_Eco', label: 'Serie GP - Uso General (5 HP)', sub: 'Aplicaciones económicas, hobby o maquinaria que no opera de forma diaria.' },
          { value: 'Profesional_Baja', label: 'Serie GX - Estándar (5.5 HP)', sub: 'Para reemplazo o acople a hormigoneras, vibradores, o equipamiento agrícola liviano.' },
          { value: 'Profesional_Alta', label: 'Serie GX - Alta Potencia (13 HP)', sub: 'Máximo torque para hidrolavadoras de gran caudal, generadores o equipos industriales.' }
        ],
        'Cortadora de Césped': [
          { value: 'Empuje_Residencial', label: 'Corte por Empuje (Hogar)', sub: 'Control total de la velocidad. Simple, eficiente y económico.' },
          { value: 'Autopropulsada_Estándar', label: 'Tracción Autopropulsada (HRN)', sub: 'Sistema Variable. Mayor comodidad y productividad en jardines medios.' },
          { value: 'Autopropulsada_Premium', label: 'Tracción Autopropulsada (HRX)', sub: 'Sistema Select Drive, motor premium y Versamow™ (mulching/embolsado).' }
        ],
        'Motoguadaña': [
          { value: 'Bateria_Ligero', label: 'A Batería (Cero Emisiones)', sub: 'Bajo ruido, ideal para uso residencial, bordes y tareas ligeras.' },
          { value: 'Gasolina_Media', label: 'Combustión 4T - Semi-Profesional (25cc)', sub: 'Excelente rendimiento, sin mezcla de aceite, ideal para mantenimiento frecuente.' },
          { value: 'Gasolina_Intensiva', label: 'Combustión 4T - Profesional (35cc/50cc)', sub: 'Máxima potencia para desmalezado continuo, arboles jóvenes y terrenos duros.' }
        ],
        'Sopladora': [
          { value: 'Bateria_Ligero', label: 'A Batería (Cero Emisiones)', sub: 'Bajo ruido, ideal para uso residencial y limpieza rápida de pequeñas áreas.' },
          { value: 'Gasolina_Mano', label: 'Combustión 4T - Uso Manual (25cc)', sub: 'Potencia constante para limpieza en mano. Sin mezcla de aceite.' }
        ],
        'Sierra/Cortacerco': [
          { value: 'Cortacerco_Bateria', label: 'Cortacerco A Batería', sub: 'Para setos, con cero emisiones y cuchillas precisas.' },
          { value: 'Electrosierra_Bateria', label: 'Electrosierra A Batería', sub: 'Potente sierra de batería para poda y corte de madera.' }
        ],
        'Fumigadora': [
          { value: 'Fumigadora_25cc', label: 'Mochila de Uso General (25 cc)', sub: 'Para tareas de rociado en jardines y cultivos pequeños. Compacta y ligera.' },
          { value: 'Fumigadora_40cc', label: 'Mochila de Alto Rendimiento (40 cc)', sub: 'Mayor potencia de rociado para grandes extensiones agrícolas y uso profesional.' }
        ],
      };
      
      // Opciones Condicionales para P3 (Frecuencia)
      const P3_OPTIONS = {
          'Combustión': [
              { value: 'Ocasional', label: 'Uso Ocasional (GP Series / EZ)', sub: 'Emergencias, tareas específicas de baja demanda. Menos de **50 horas/año**.' },
              { value: 'Frecuente', label: 'Uso Frecuente (GX Series / Estándar)', sub: 'Respaldo comercial, trabajo semi-diario. Más de **100 horas/año**. Diseño profesional.' },
              { value: 'Intensivo', label: 'Uso Continuo / Intensivo (GX Series - Industrial)', sub: 'Aplicaciones de trabajo diario, alquiler, minería. Máxima resistencia a la fatiga.' },
          ],
          'Batería/Residencial': [
              { value: 'Ocasional', label: 'Uso Residencial Ocasional', sub: 'Tareas de mantenimiento de jardín de baja demanda (1-2 veces por mes).'},
              { value: 'Frecuente', label: 'Uso Residencial Frecuente', sub: 'Mantenimiento semanal o diario de jardines grandes. Requiere mayor autonomía y durabilidad.'},
          ]
      };
      
      // Aclaraciones para P3
      const P3_ACLARACION = {
          'Generador': '<strong>Diferenciador GX vs. GP:</strong> La **Serie GX** es industrial (mayor vida útil). La **Serie GP** es para uso general u ocasional, ofreciendo buen rendimiento a menor costo.',
          'Motobomba': '<strong>Diferenciador GX vs. GP:</strong> Los modelos **GX** son recomendados para uso profesional y trabajo continuo (ej: obras, riego constante). **GP** es para uso doméstico o drenajes esporádicos.',
          'Motor Estacionario': '<strong>Diferenciador GX vs. GP:</strong> La serie **GX** es para acople industrial (GX160, GX390). La serie **GP** es ideal para reemplazo económico o maquinaria de bajo ciclo de trabajo.',
          'Cortadora de Césped': '<strong>Diferenciador Motores GC/GCV:</strong> Los motores **GC** son residenciales, mientras que los **GCV** (Autopropulsados) tienen mayor rendimiento y torque para trabajos más exigentes.',
          'Motoguadaña': '<strong>Diferenciador:</strong> Considera la opción **A Batería** para uso muy ligero o la robustez de los motores **4 Tiempos (GX/UMK)** para trabajos intensivos.',
          'Sopladora': '<strong>Diferenciador:</strong> Los modelos **4T** ofrecen potencia y caudal de aire superior. Los modelos a **Batería** priorizan el bajo ruido y las cero emisiones.',
          'Sierra/Cortacerco': '<strong>Diferenciador:</strong> Estos equipos son altamente dependientes de la **Batería**. Si necesitas autonomía extrema, la combustión 4T de Honda es la alternativa.',
          'Fumigadora': '<strong>Diferenciador 4T:</strong> Las mochilas **4 Tiempos (WJR)** eliminan la necesidad de mezclar aceite y combustible, asegurando arranques más fáciles y menor emisión de humo.',
      };

      // Opciones Condicionales para P4 (Prioridad)
      const P4_OPTIONS = {
          'Generador': [
              { value: 'Bajo Ruido/Inverter', label: 'Bajo Ruido / Estabilización (Inverter)', sub: 'Para equipos sensibles (TV, PC) y operar en zonas residenciales o campamentos.' },
              { value: 'Potencia Máxima/Trifásico', label: 'Máxima Potencia / Conexión Trifásica (380V)', sub: 'Priorizar potencia bruta o requerir conexión de 380V.' },
              { value: 'Eficiencia y Repuestos', label: 'Durabilidad y Respaldo (Motor GX)', sub: 'Priorizar la vida útil del motor, la disponibilidad de repuestos y la red de service.' },
          ],
          'Motobomba': [
              { value: 'Manejo de Sólidos/Lodos', label: 'Capacidad para Aguas Sucias (Trash)', sub: 'Drenar fluidos con sólidos, arena o lodo (WT Series).' },
              { value: 'Alta Presión/Altura', label: 'Máxima Presión / Gran Altura', sub: 'Necesidad de impulsar el agua a 40+ metros de altura (WH Series).' },
              { value: 'Alto Caudal/Volumen', label: 'Alto Caudal / Máximo Volumen (2" o 3")', sub: 'Drenar o transferir el mayor volumen de agua posible en poco tiempo (WB/WL Series).' },
          ],
          'Motor Estacionario': [
              { value: 'Torque Industrial (GX)', label: 'Máximo Torque Industrial (GX Series)', sub: 'Para compresores o maquinaria que exige alto torque constante.' },
              { value: 'Costo-Beneficio (GP)', label: 'Costo-Beneficio y Facilidad de Reemplazo (GP Series)', sub: 'Si el motor es un reemplazo puntual o el presupuesto es ajustado.' },
          ],
          'Cortadora de Césped': [
              { value: 'Sistema Mulching/Versamow', label: 'Mulching y Recolección (Versamow™)', sub: 'Ajustar la proporción de corte entre embolsado y triturado.' },
              { value: 'Tracción Autopropulsada', label: 'Tracción / Eliminación de Esfuerzo', sub: 'Facilidad de uso y velocidad de corte en terrenos grandes o inclinados.' },
              { value: 'Simpleza/Bajo Peso', label: 'Simplicidad y Bajo Peso (Empuje)', sub: 'Si el jardín es pequeño o la prioridad es el manejo simple y sin tracción.' },
          ],
          'Motoguadaña': [
              { value: 'Potencia y Durabilidad 4T', label: 'Potencia y Durabilidad del 4 Tiempos', sub: 'Para desmalezado pesado y uso profesional continuo (sin mezcla).' },
              { value: 'Cero Emisiones / Bajo Ruido', label: 'Bajo Ruido / Cero Emisiones (Batería)', sub: 'Trabajar en entornos sensibles al ruido, o áreas residenciales.' },
          ],
          'Sopladora': [
              { value: 'Potencia de Caudal 4T', label: 'Máximo Caudal de Aire (Motor 4T)', sub: 'Para mover material pesado o grandes volúmenes de hojas húmedas.' },
              { value: 'Cero Emisiones / Bajo Ruido', label: 'Bajo Ruido / Cero Emisiones (Batería)', sub: 'Trabajar en entornos sensibles al ruido (parques, residencias).' },
          ],
          'Sierra/Cortacerco': [
              { value: 'Cero Emisiones / Bajo Ruido', label: 'Bajo Ruido / Cero Emisiones (Batería)', sub: 'Prioridad máxima para estos equipos ligeros y de precisión.' },
              { value: 'Ergonomía y Liviandad', label: 'Máxima Ergonomía y Liviandad', sub: 'Trabajos de precisión con el menor esfuerzo físico y la mejor maniobrabilidad.' },
          ],
          'Fumigadora': [
              { value: 'Alta Presión de Rociado', label: 'Alta Presión y Alcance de Rociado', sub: 'Para grandes extensiones o árboles altos, requiriendo un motor más potente (40cc).' },
              { value: 'Bajo Consumo y Fácil Arranque', label: 'Bajo Consumo y Fácil Arranque (25cc)', sub: 'Para fumigación localizada y uso doméstico/semi-profesional.' },
          ],
      };


      function seleccion(name){
        const el = document.querySelector('input[name="'+name+'"]:checked');
        return el ? el.value : '';
      }
      
      // Función genérica para renderizar opciones
      function renderOptions(containerId, options, name) {
          const container = document.getElementById(containerId);
          container.innerHTML = '';
          options.forEach(option => {
              const label = document.createElement('label');
              label.className = 'option';
              label.innerHTML = `
                  <input type="radio" name="${name}" value="${option.value}" required>
                  <div>
                      <span class="label-main">${option.label}</span>
                      <span class="label-sub">${option.sub}</span>
                  </div>
              `;
              container.appendChild(label);
          });
          // Limpia el valor anterior
          document.querySelectorAll(`input[name="${name}"]`).forEach(input => {
              input.checked = false;
          });
      }

      // Función para generar las aclaraciones técnicas específicas para P2
      function getP2Aclaracion(usoValue) {
          if (usoValue === 'Generador') {
              return '<p><strong>Aclaración Generadores:</strong> El **kVA** es la potencia aparente. **Monofásico** a **220V**, **Trifásico** a **380V**. Los modelos **Inverter** son de onda pura.</p>';
          } else if (usoValue === 'Motobomba') {
              return '<p><strong>Aclaración Motobombas:</strong> El **Caudal** (**L/min**) es el volumen. La **Presión** (**metros de altura**) es la fuerza de elevación. Las bombas **WT** son *Trash* (Aguas Sucias) y manejan sólidos.</p>';
          } else if (usoValue === 'Motor Estacionario') {
              return '<p><strong>Aclaración Motores:</strong> El **HP** (caballos de fuerza) determina el torque. La serie **GX** es profesional/industrial, mientras que **GP** es para uso general.</p>';
          } else if (usoValue === 'Cortadora de Césped') {
              return '<p><strong>Aclaración Cortadoras:</strong> El sistema **Autopropulsado** elimina el esfuerzo de empuje. Los modelos Premium (HRX) usan la tecnología **Versamow™** (mulching variable).</p>';
          } else if (usoValue === 'Motoguadaña') {
              return '<p><strong>Aclaración Motoguadañas:</strong> Los equipos **4 Tiempos (4T)** usan nafta sola (sin mezcla). La opción **A Batería** es bajo ruido y cero mantenimiento de combustible.</p>';
          } else if (usoValue === 'Sopladora') {
              return '<p><strong>Aclaración Sopladoras:</strong> Los modelos **4T** ofrecen máxima potencia para caudal de aire. La línea **A Batería** ofrece comodidad y bajo nivel de ruido.</p>';
          } else if (usoValue === 'Sierra/Cortacerco') {
              return '<p><strong>Aclaración Herramientas:</strong> Los equipos de esta gama son solo a batería, enfocados en la precisión, el bajo ruido y el confort ergonómico.</p>';
          } else if (usoValue === 'Fumigadora') {
              return '<p><strong>Aclaración Fumigadoras:</strong> La cilindrada (**cc**) indica la potencia del motor para generar la presión de rociado. Los modelos **4T** (WJR) son ideales por su bajo consumo y arranque sencillo.</p>';
          }
          return '<p><strong>Aclaración Técnica:</strong> Por favor, selecciona un tipo de equipo en el paso 1 para cargar las opciones de Potencia/Capacidad relevantes.</p>'; 
      }
      
      // Función para renderizar P2
      function updateP2Options(usoValue) {
        const p2OptionsDiv = document.getElementById('p2-options');
        const p2AclaracionDiv = document.getElementById('p2-aclaracion');
        
        p2AclaracionDiv.innerHTML = getP2Aclaracion(usoValue);

        if (usoValue && P2_OPTIONS[usoValue]) {
          renderOptions('p2-options', P2_OPTIONS[usoValue], 'capacidad');
        } else {
          p2OptionsDiv.innerHTML = '<p class="loading-placeholder">Selecciona un Tipo de Equipo en el paso 1.</p>';
        }
      }

      // Función para renderizar P3 y P4
      function updateP3P4Options(usoValue) {
          const p3OptionsDiv = document.getElementById('p3-options');
          const p3AclaracionDiv = document.getElementById('p3-aclaracion');
          const p4OptionsDiv = document.getElementById('p4-options');
          const p3ExamplesDiv = document.getElementById('p3-examples');
          const p4ExamplesDiv = document.getElementById('p4-examples');
          
          if (!usoValue) {
              p3OptionsDiv.innerHTML = '<p class="loading-placeholder">Selecciona un Tipo de Equipo en el paso 1.</p>';
              p4OptionsDiv.innerHTML = '<p class="loading-placeholder">Selecciona un Tipo de Equipo en el paso 1.</p>';
              p3AclaracionDiv.innerHTML = '<p><strong>Diferenciador:</strong> Selecciona un tipo de equipo en el paso 1 para ver la diferencia de durabilidad aplicada.</p>';
              return;
          }

          // 1. Lógica P3 (Frecuencia)
          p3AclaracionDiv.innerHTML = `<p>${P3_ACLARACION[usoValue]}</p>`;

          let p3Set = P3_OPTIONS['Combustión'];
          if (['Cortadora de Césped', 'Motoguadaña', 'Sopladora', 'Sierra/Cortacerco'].includes(usoValue)) {
              p3Set = P3_OPTIONS['Batería/Residencial'];
          }
          if (['Motoguadaña', 'Sopladora', 'Sierra/Cortacerco'].includes(usoValue) && usoValue !== 'Motoguadaña') {
               p3ExamplesDiv.textContent = 'Define la intensidad de uso. Para herramientas, esto define si requieres más baterías o un motor de combustión.';
          } else {
               p3ExamplesDiv.textContent = 'Define la intensidad de trabajo para seleccionar el grado de motor (GP o GX) o el tipo de alimentación.';
          }
          renderOptions('p3-options', p3Set, 'frecuencia');


          // 2. Lógica P4 (Prioridad de Diseño)
          p4ExamplesDiv.textContent = 'Esto ayuda a filtrar entre modelos estándar, insonorizados, autopropulsados, con capacidad para sólidos, o a batería. Elige tu característica clave.';
          renderOptions('p4-options', P4_OPTIONS[usoValue], 'prioridad');
      }

      // Escucha el cambio en P1 (Uso)
      document.querySelectorAll('input[name="uso"]').forEach(input => {
          input.addEventListener('change', (e) => {
              const usoValue = e.target.value;
              updateP2Options(usoValue);
              updateP3P4Options(usoValue);
          });
      });
      

      // --- LÓGICA DE FILTRADO (FINAL) ---
      function recomendar(uso, frecuencia, prioridad, entorno, capacidad){
        
        const isContinuous = frecuencia === 'Intensivo';
        const isOcasional = frecuencia === 'Ocasional';
        // Variables de Prioridad (P4)
        const isBajoRuido = prioridad === 'Bajo Ruido/Inverter' || prioridad === 'Cero Emisiones / Bajo Ruido';
        const isTrifasico = prioridad === 'Potencia Máxima/Trifásico';
        const isSolidHandling = prioridad === 'Manejo de Sólidos/Lodos';
        const isPressure = prioridad === 'Alta Presión/Altura';
        const isMulching = prioridad === 'Sistema Mulching/Versamow';
        const isTraction = prioridad === 'Tracción Autopropulsada';
        const isMaxTorque = prioridad === 'Torque Industrial (GX)';

        // ------------------------------------
        // LÓGICA GENERADORES (4 Productos)
        // ------------------------------------
        if (uso === 'Generador') {
            if (isTrifasico || entorno === 'Industrial / Comercial') return PRODUCTS['ET12000K1-RRH']; 
            if (capacidad === 'Inverter_BajoRuido' || isBajoRuido) return PRODUCTS['EU22IT-RA'];
            if (capacidad === 'Monofásico_Alto' || isContinuous) return PRODUCTS['EG6500CXS-RAH'];
            // Monofásico_Medio: se filtra por la frecuencia (GX vs GP)
            if (capacidad === 'Monofásico_Medio') return isContinuous ? PRODUCTS['EG6500CXS-RAH'] : PRODUCTS['EZ3000CX- RA'];
            return PRODUCTS['EZ3000CX- RA']; 
        }

        // ------------------------------------
        // LÓGICA MOTOBOMBAS (7 Productos)
        // ------------------------------------
        if (uso === 'Motobomba') {
            // Prioridad máxima: Sólidos
            if (isSolidHandling) {
                // Si la prioridad es Sólidos y Capacidad es Aguas Sucias, la diferencia es el motor/tamaño.
                return (entorno === 'Obras / Construcción') ? PRODUCTS['WT40XK3-DE'] : PRODUCTS['WT30XK4-DE']; 
            }
            // Segunda prioridad: Presión
            if (capacidad === 'Limpia_Presión' || isPressure) return PRODUCTS['WH20XT-DFX'];
            
            // Tercera prioridad: Caudal (2" vs 3") y Frecuencia (GX vs GP)
            if (capacidad === 'Limpia_Caudal_3p') return isContinuous ? PRODUCTS['WB30XH2-DRX'] : PRODUCTS['WL30XH-DRX']; 
            if (capacidad === 'Limpia_Caudal_2p') return isContinuous ? PRODUCTS['WB20XH2-DR'] : PRODUCTS['WL20XH']; 
            
            // Fallback (Si eligió 3" o 2" sin determinar frecuencia, damos GP/WL)
            return PRODUCTS['WL20XH']; 
        }

        // ------------------------------------
        // LÓGICA MOTORES ESTACIONARIOS (3 Productos)
        // ------------------------------------
        if (uso === 'Motor Estacionario') {
          if (capacidad === 'Profesional_Alta' || isMaxTorque || isContinuous) return PRODUCTS['GX390H2-QX'];
          if (capacidad === 'Profesional_Baja' || frecuencia === 'Frecuente') return PRODUCTS['GX160H2-SX1'];
          if (capacidad === 'Reemplazo_Eco' || isOcasional) return PRODUCTS['GP160H-SH1'];
          // Fallback por defecto a GX (Estándar) si la respuesta es ambigua
          return PRODUCTS['GX160H2-SX1'];
        }
        
        // ------------------------------------
        // LÓGICA CORTADORAS DE CÉSPED (3 Productos)
        // ------------------------------------
        if (uso === 'Cortadora de Césped') {
            if (capacidad === 'Autopropulsada_Premium' || isMulching) return PRODUCTS['HRX217K6-VKAA'];
            if (capacidad === 'Autopropulsada_Estándar' || isTraction) return PRODUCTS['HRN216-VKA'];
            if (capacidad === 'Empuje_Residencial') return PRODUCTS['HRN216-PKA'];
            return PRODUCTS['HRN216-PKA']; 
        }

        // ------------------------------------
        // LÓGICA MOTOGUADAÑAS (4 Productos)
        // ------------------------------------
        if (uso === 'Motoguadaña') {
            // Prioridad Batería (P2 o P4)
            if (capacidad === 'Bateria_Ligero' || isBajoRuido) return PRODUCTS['HHT36']; 
            
            // Prioridad Combustión por Potencia (P2/P3)
            if (capacidad === 'Gasolina_Intensiva') return PRODUCTS['UMK450T-UEDT']; // Heavy Duty (GX50)
            if (capacidad === 'Gasolina_Media' && frecuencia === 'Frecuente') return PRODUCTS['UMK435T-UEDT']; // Profesional (GX35)
            if (capacidad === 'Gasolina_Media' && isOcasional) return PRODUCTS['UMK425T-UTDT']; // Semi-Profesional (GX25)
            
            return PRODUCTS['UMK435T-UEDT']; 
        }

        // ------------------------------------
        // LÓGICA SOPLADORAS (2 Productos)
        // ------------------------------------
        if (uso === 'Sopladora') {
            if (capacidad === 'Bateria_Ligero' || isBajoRuido) return PRODUCTS['HHB36'];
            if (capacidad === 'Gasolina_Mano') return PRODUCTS['HHB25-ET1'];
            return PRODUCTS['HHB25-ET1'];
        }
        
        // ------------------------------------
        // LÓGICA SIERRA/CORTACERCO (2 Productos)
        // ------------------------------------
        if (uso === 'Sierra/Cortacerco') {
            if (capacidad === 'Cortacerco_Bateria') return PRODUCTS['HHH36'];
            if (capacidad === 'Electrosierra_Bateria') return PRODUCTS['HHC36'];
            return PRODUCTS['HHH36'];
        }
        
        // ------------------------------------
        // LÓGICA FUMIGADORAS (2 Productos)
        // ------------------------------------
        if (uso === 'Fumigadora') {
             if (capacidad === 'Fumigadora_40cc' || isContinuous) return PRODUCTS['WJR4025T-GCS']; // Profesional (GX35)
             if (capacidad === 'Fumigadora_25cc') return PRODUCTS['WJR2525T1-GCS']; // Uso General (GX25)
             return PRODUCTS['WJR2525T1-GCS'];
        }
        
        // Fallback de emergencia total
        return PRODUCTS['EZ3000CX- RA']; 
      }

      function crearWhatsApp(producto, frecuencia, prioridad, entorno, capacidad){
        if (!IS_WHATSAPP_CONFIGURED) return '#'; 
        const mensaje = `¡Hola! Estoy interesado/a en ${producto} (Rec. Asesor). Mi uso es: ${seleccion('uso')}. Capacidad Requerida: ${capacidad}. Frecuencia: ${frecuencia}. Prioridad: ${prioridad}. Entorno: ${entorno}. Quiero más detalles y cotización exacta.`;
        return 'https://wa.me/' + WHATSAPP_NUMBER + '?text=' + encodeURIComponent(mensaje);
      }

      function validarCampos(){
        return {
          uso: seleccion('uso'),
          capacidad: seleccion('capacidad'), 
          frecuencia: seleccion('frecuencia'),
          prioridad: seleccion('prioridad'),
          entorno: seleccion('entorno'),
        };
      }

      form.addEventListener('submit', function(e){
        e.preventDefault();
        resultado.classList.remove('visible');

        const {uso, capacidad, frecuencia, prioridad, entorno} = validarCampos(); 

        // Se asegura la validación de los 5 campos
        if(!uso || !capacidad || !frecuencia || !prioridad || !entorno){
          resultado.innerHTML = '<div class="error">⚠️ ¡Atención! Debés responder las 5 preguntas para obtener tu recomendación.</div>';
          resultado.classList.add('visible');
          resultado.scrollIntoView({behavior:'smooth', block:'center'});
          return;
        }

        const rec = recomendar(uso, frecuencia, prioridad, entorno, capacidad); 
        const wa = crearWhatsApp(rec.producto, frecuencia, prioridad, entorno, capacidad); 
        
        const whatsappButtonText = IS_WHATSAPP_CONFIGURED ? `Consultar por ${rec.producto}` : '⚠️ ¡CONFIGURAR WHATSAPP! ⚠️';
        const whatsappLink = IS_WHATSAPP_CONFIGURED ? wa : '#';


        // Construir resultado HTML
        resultado.innerHTML = `
          <div class="result-grid">
            <div class="image-container">
              <img src="${rec.photoUrl}" alt="Imagen del producto recomendado: ${rec.producto}" style="width:100%; height:100%; object-fit:cover; display:block;">
            </div>
            <div>
              <div class="product-title">✅ ${rec.producto}</div>
              <div class="product-specs">${rec.specs}</div> 
              <div class="product-price">Precio Estimado: ${rec.precio}</div>
              <div class="product-advantage">🔥 **Ventaja Clave:** ${rec.ventaja}</div>
              <a class="whatsapp" href="${whatsappLink}" target="_blank" rel="noopener">${whatsappButtonText}</a>
            </div>
          </div>
        `;
        resultado.classList.add('visible');
        resultado.scrollIntoView({behavior:'smooth', block:'center'});
      });

      // Inicializar el estado de P2, P3 y P4 al cargar la página
      document.addEventListener('DOMContentLoaded', () => {
          updateP2Options(null); 
          updateP3P4Options(null); 
      });
    })();
  </script>
</body>
</html>
