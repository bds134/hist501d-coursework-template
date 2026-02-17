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
