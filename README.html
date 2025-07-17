<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>NUEVEDIECISEIS • Gestión de Equipos</title>
  <script src="https://cdn.jsdelivr.net/npm/qrious/dist/qrious.min.js"></script>
  <style>
    body { font-family: sans-serif; padding: 20px; background: #f4f6f8; }
    h2 { display: flex; justify-content: space-between; }
    #reloj { color: #555; }
    table { border-collapse: collapse; width: 100%; background: white; box-shadow: 0 0 5px #ccc; margin-bottom: 20px; }
    th, td { padding: 8px; border-bottom: 1px solid #ddd; text-align: center; }
    input { width: 90%; padding: 6px; }
    canvas { margin-top: 5px; }
    button { padding: 6px 12px; margin: 5px; cursor: pointer; }
    .carpeta, .vista-movil { margin-top: 20px; padding: 15px; background: #eef; border-radius: 8px; }
    .resaltar-rojo { background-color: #ffcccc !important; }
    .resaltar-verde { background-color: #ccffcc !important; }
    .resaltar-amarillo { background-color: #ffffcc !important; }
    .cronometro { font-weight: bold; color: #007700; font-size: 1.1em; }
  </style>
</head>
<body>

<h2>
  NUEVEDIECISEIS
  <span id="reloj">⏱ Cargando hora...</span>
</h2>

<table id="tabla">
  <tr>
    <th>Equipo</th><th>Interno</th><th>Modelo</th><th>N° Base</th><th>Horas Base</th><th>Horas Actuales</th><th>Servicio</th><th>QR</th><th>Acción</th>
  </tr>
</table>

<button onclick="agregarFila()">Agregar fila</button>
<div id="carpetas"></div>

<script>
  const carpetas = {};

  // Reloj superior
  setInterval(() => {
    document.getElementById("reloj").textContent = "⏱ " + new Date().toLocaleTimeString();
  }, 1000);

  function agregarFila() {
    const fila = document.createElement("tr");
    const campos = ['equipo','interno','modelo','nroBase','horasBase','horasActuales','servicio'];

    campos.forEach((campo, i) => {
      const td = document.createElement("td");
      const input = document.createElement("input");
      input.type = campo.includes('Horas') ? "number" : "text";
      if (campo === 'horasBase') {
        input.addEventListener("input", () => verificarColor(input));
      }
      td.appendChild(input);
      fila.appendChild(td);
    });

    const qrTd = document.createElement("td");
    const canvas = document.createElement("canvas");
    canvas.width = 80;
    canvas.height = 80;
    qrTd.appendChild(canvas);
    fila.appendChild(qrTd);

    const btnTd = document.createElement("td");
    const btn = document.createElement("button");
    btn.textContent = "Crear carpeta";
    btn.onclick = () => crearCarpeta(fila, canvas);
    btnTd.appendChild(btn);
    fila.appendChild(btnTd);

    document.getElementById("tabla").appendChild(fila);
  }

  function verificarColor(input) {
    const val = parseInt(input.value);
    const celda = input.parentElement;
    celda.className = "";
    if (!isNaN(val)) {
      if (val >= 200 && val <= 250) celda.classList.add("resaltar-rojo");
      else if (val >= 950 && val <= 1000) celda.classList.add("resaltar-verde");
      else if (val >= 1950 && val <= 2000) celda.classList.add("resaltar-amarillo");
    }
  }

  function crearCarpeta(fila, canvas) {
    const inputs = fila.querySelectorAll("input");
    const valores = [...inputs].map(i => i.value.trim());
    const id = `carpeta_${valores[3]}_${Date.now()}`;
    const creado = Date.now();

    carpetas[id] = {
      equipo: valores[0],
      interno: valores[1],
      modelo: valores[2],
      base: valores[3],
      horasBase: valores[4],
      servicio: valores[6],
      creado
    };

    // Guardar en localStorage
    localStorage.setItem(id, JSON.stringify(carpetas[id]));

    // Generar QR con enlace simulado
    const url = location.href + `#${encodeURIComponent(id)}`;
    new QRious({ element: canvas, value: url, size: 80 });

    mostrarVista(id);
  }

  function mostrarVista(id) {
    const datos = carpetas[id];
    const div = document.createElement("div");
    div.className = "vista-movil";
    div.innerHTML = `
      <h3>📁 Carpeta creada: ${id}</h3>
      <p><strong>Equipo:</strong> ${datos.equipo}</p>
      <p><strong>Interno:</strong> ${datos.interno}</p>
      <p><strong>Modelo:</strong> ${datos.modelo}</p>
      <p><strong>N° Base:</strong> ${datos.base}</p>
      <p><strong>Horas Base:</strong> ${datos.horasBase}</p>
      <p><strong>Servicio:</strong> ${datos.servicio}</p>
      <p><strong>Horas Actuales (cronómetro):</strong> <span id="cron_${id}" class="cronometro">00:00:00</span></p>
    `;
    document.getElementById("carpetas").appendChild(div);
    iniciarCronometro(id, datos.creado);
  }

  function iniciarCronometro(id, inicio) {
    function actualizar() {
      const now = Date.now();
      const delta = Math.floor((now - inicio) / 1000);
      const hh = String(Math.floor(delta / 3600)).padStart(2, '0');
      const mm = String(Math.floor((delta % 3600) / 60)).padStart(2, '0');
      const ss = String(delta % 60).padStart(2, '0');
      document.getElementById(`cron_${id}`).textContent = `${hh}:${mm}:${ss}`;
    }
    setInterval(actualizar, 1000);
    actualizar();
  }

  // Si accedés por QR (con hash en URL)
  window.addEventListener("load", () => {
    const hash = location.hash.replace("#", "");
    if (hash && localStorage.getItem(hash)) {
      const datos = JSON.parse(localStorage.getItem(hash));
      carpetas[hash] = datos;
      mostrarVista(hash);
    }
  });
</script>

</body>
</html>
