<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>PETA Pelanggan - PT AIMI INDONESIA</title>
  <link rel="icon" href="logo.png" />
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
    }
    header {
      background: #fff;
      padding: 10px 20px;
      display: flex;
      align-items: center;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    header img {
      height: 40px;
      margin-right: 15px;
    }
    header h1 {
      font-size: 20px;
      margin: 0;
    }
    .desc {
      padding: 10px 20px;
      background-color: #e9e9e9;
      font-size: 14px;
      color: #333;
    }
    #map {
      height: 80vh;
      width: 100%;
    }
  </style>
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
</head>
<body>
  <header>
    <img src="logo.png" alt="Logo AIMI">
    <h1>PT AIMI INDONESIA - Peta Pelanggan</h1>
  </header>
  <div class="desc">
    Website ini menampilkan lokasi-lokasi pelanggan aktif dari PT AIMI INDONESIA di seluruh wilayah Indonesia dan sekitarnya.
  </div>
  <div id="map"></div>

  <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
  <script>
    var map = L.map('map').setView([-2.5, 118], 5);
    L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; OpenStreetMap',
    }).addTo(map);

    var locations = [
      {lat: -6.2, lon: 106.8, title: "Jakarta"},
      {lat: -7.25, lon: 112.75, title: "Surabaya"},
      {lat: -6.9, lon: 107.6, title: "Bandung"},
      {lat: -0.9, lon: 119.8, title: "Sulawesi Tengah"},
      {lat: -2.5, lon: 140.7, title: "Jayapura"}
    ];

    locations.forEach(loc => {
      L.marker([loc.lat, loc.lon]).addTo(map).bindPopup(loc.title);
    });
  </script>
</body>
</html>
