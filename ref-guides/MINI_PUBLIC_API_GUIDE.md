# Ecology of Crisis API – Mini Public API Guide

This guide covers the most common public (no authentication required) endpoints for accessing historical event data.

## Base URL
```
https://ecocrisis.net
```

---

## 1. Get All Public Events
- **Endpoint:** `GET /eventinfo/public/events`
- **Description:** List all approved events. Supports filtering by year, theme, etc.


### Example (cURL)
```bash
curl -X GET "https://ecocrisis.net/eventinfo/public/events"
```

### Example (Python)
```python
import requests
url = "https://ecocrisis.net/eventinfo/public/events"
r = requests.get(url)
print(r.json())
```

> **Note:** Filtering by year, theme, or other parameters is not currently supported by this endpoint. To filter results, fetch all events and filter them client-side in your application.

---

## 2. Get Event by ID
- **Endpoint:** `GET /eventinfo/public/event/{id}`
- **Description:** Fetch a single approved event by its unique ID.

### Example (cURL)
```bash
curl -X GET "https://ecocrisis.net/eventinfo/public/event/99"
```

### Example (Python)
```python
import requests
url = "https://ecocrisis.net/eventinfo/public/event/99"
r = requests.get(url)
print(r.json())
```

---

curl -X GET "https://ecocrisis.net/eventinfo/public/events/by-year?startYear=1690&endYear=1700"
## 3. Get Events by Year or Range
- **Endpoint:** `GET /eventinfo/public/events/by-year?startYear=YYYY[&endYear=YYYY]`
- **Description:** Fetch all approved events for a specific year or a year range. If `endYear` is omitted, only `startYear` is used.

### Example (cURL)
```bash
curl -X GET "https://ecocrisis.net/eventinfo/public/events/by-year?startYear=1697"
curl -X GET "https://ecocrisis.net/eventinfo/public/events/by-year?startYear=1690&endYear=1700"
```

### Example (Python)
```python
import requests
# Single year
url = "https://ecocrisis.net/eventinfo/public/events/by-year"
params = {"startYear": 1697}
r = requests.get(url, params=params)
print(r.json())
# Year range
params = {"startYear": 1690, "endYear": 1700}
r = requests.get(url, params=params)
print(r.json())
```

---

## 4. Get Public Stats
- **Endpoint:** `GET /eventinfo/public/stats`
- **Description:** Get overall statistics about the database.

### Example (cURL)
```bash
curl -X GET "https://ecocrisis.net/eventinfo/public/stats"
```

### Example (Python)
```python
import requests
url = "https://ecocrisis.net/eventinfo/public/stats"
r = requests.get(url)
print(r.json())
```

---

## 5. Search Events by Year, State, Class, Domain
- **Endpoint:** `GET /eventinfo/public/events/search`
- **Description:** Fetch approved events filtered by any combination of year range, state, class, and domain. All parameters are optional and can be combined.

### Query Parameters
- `startYear` (integer): Start of year range
- `endYear` (integer): End of year range
- `state` (string): State name (see options below)
- `classId` (integer): Class ID
- `domainId` (integer): Domain ID

### Example (cURL)
```bash
curl -X GET "https://ecocrisis.net/eventinfo/public/events/search?startYear=1700&endYear=1750&state=Jalisco&classId=2&domainId=3"
```

### Example (Python)
```python
import requests
url = "https://ecocrisis.net/eventinfo/public/events/search"
params = {
    "startYear": 1700,
    "endYear": 1750,
    "state": "Jalisco",
    "classId": 2,
    "domainId": 3
}
r = requests.get(url, params=params)
print(r.json())
```

### State Options
Aguascalientes, Baja California Sur, Campeche, Chiapas, Chihuahua, Ciudad de México, Coahuila de Zaragoza, Colima, Durango, Estado de México, Guanajuato, Guerrero, Hidalgo, Jalisco, México, Michoacán de Ocampo, Morelos, Nayarit, Nuevo León, Oaxaca, Puebla, Querétaro, Quintana Roo, San Luis Potosí, San Luís Potosí, Sinaloa, Sonora, State of Mexico, Tabasco, Tamaulipas, Tlaxcala, Veracruz de Ignacio de la Llave, Yucatan, Yucatán, Zacatecas

### Class Options
cold, hot, dry, wet, stormy, sickness, nutrition, political response, agriculture, religious response, popular response, seismic, livestock, volcanic

### Domain Options
health, social, geophysical, biology, climate
