# 🇷🇺 Local OSRM Server for Russia via Docker

A simple way to deploy a local **OSRM** routing server with the Russia map (or any other) using Docker.

## 📁 Step 1 — Prepare the Map

1. Create a folder named `data` in the root of your project:  
```bash
   mkdir data
```

2. Download the map file in `.osm.pbf` format  
   👉 [Russia map download](https://download.geofabrik.de/russia.html)

3. Place the downloaded file (e.g. `russia-latest.osm.pbf`) into the `data` folder.

> Make sure the filename matches the one specified in `docker-compose.yml` (by default `russia-latest.osm.pbf`).

---

## 🛠️ Step 2 — Process the Map

Run the following commands one by one:

```bash
    docker-compose up osrm-extract
    docker-compose up osrm-partition
    docker-compose up osrm-customize
```

---

## 🚀 Step 3 — Run the Server

Start the OSRM routing server:
```bash
    docker-compose up osrm-routed
```

After starting, the server will be available at:  
👉 [http://localhost:5000](http://localhost:5000)

---

## ✅ Done

Now you can use your local **OSRM** server for:

- route building  
- integrating with geo interfaces  
- other geodata-related tasks  

---

## 📌 Note

If you want to use another country or region, replace the map with the corresponding `.osm.pbf` file and update the filename in `docker-compose.yml`.

