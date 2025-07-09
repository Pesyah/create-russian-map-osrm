# 🇷🇺 Локальный сервер OSRM для России через Docker

Простой способ развернуть локальный сервер маршрутизации **OSRM** с картой России (или другой страны) с помощью Docker.

## 📁 Шаг 1 — Подготовка карты

1. Создайте папку `data` в корне проекта:
```bash
   mkdir data
```

2. Скачайте файл карты в формате `.osm.pbf`  
   👉 [Ссылка на карту России](https://download.geofabrik.de/russia.html)

3. Поместите скачанный файл (например, `russia-latest.osm.pbf`) в папку `data`.

> Убедитесь, что имя файла совпадает с тем, что указано в `docker-compose.yml` (по умолчанию — `russia-latest.osm.pbf`)

---

## 🛠️ Шаг 2 — Обработка карты

Выполните последовательно следующие команды:

```bash
    docker-compose up osrm-extract
    docker-compose up osrm-partition
    docker-compose up osrm-customize
```

🚀 Шаг 3 — Запуск сервера

Запустите маршрутизатор OSRM:
```bash
docker-compose up osrm-routed
```
После запуска сервер будет доступен по адресу:
👉 http://localhost:5000