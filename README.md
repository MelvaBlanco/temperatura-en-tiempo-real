# temperatura-en-tiempo-real
<!DOCTYPE html>
<html>
<head>
  <title>Temperatura en Tiempo Real</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body { font-family: Arial, sans-serif; text-align: center; }
    h1 { color: #333; }
    #temp { font-size: 3em; color: #c00; }
  </style>
</head>
<body>
  <h1>Temperatura en Tiempo Real</h1>
  <div id="temp">TEMP: Cargando...</div>
  <script>
    function obtenerTemperatura() {
      fetch('https://192.168.1.233/temperatura')
        .then(response => response.text())
        .then(data => document.getElementById('temp').innerHTML = 'TEMP: ' + data + " &deg;C")
        .catch(error => document.getElementById('temp').innerHTML = "Error al cargar la temperatura");
    }

    setInterval(obtenerTemperatura, 1000);
  </script>
</body>
</html>
