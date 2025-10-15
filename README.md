# 🌾 Irrigation Mapping Tool

## Overview
The **Irrigation Mapping Tool** is a web-based application that allows users to visualize farmland using satellite imagery, manually draw irrigation zones, label them, and export the data for irrigation management and planning.

---

## 🚀 Features
- **Satellite Imagery Integration** — View high-resolution imagery via Mapbox or Google Maps.
- **Manual Zone Drawing** — Draw polygons representing irrigation zones.
- **Editable Labels** — Assign crop types, names, and irrigation parameters to each zone.
- **Export & Import** — Export data as GeoJSON, KML, or CSV; import existing zone data.
- **Analytics** — Calculate area and perimeter for each zone.
- **Cloud Storage** — Save and retrieve data from a backend service.

---

## 🧠 Tech Stack

### Frontend
- **Framework:** React (Next.js optional)
- **Mapping:** Mapbox GL JS or Leaflet
- **UI:** Tailwind CSS + shadcn/ui
- **Geometry Tools:** turf.js

### Backend
- **Server:** Node.js + Express
- **Database:** PostgreSQL + PostGIS (or Firebase alternative)
- **Storage:** AWS S3 or Firebase Storage

---

## 🗺️ Core Functionality

### Map & Drawing Tools
- Display satellite basemap (Mapbox)
- Draw and edit polygons representing irrigation zones
- Assign colors and labels to each zone
- Display zone info in sidebar

### Zone Management API (Example)
| Endpoint | Method | Description |
|-----------|--------|-------------|
| `/zones` | `POST` | Save a new zone |
| `/zones` | `GET` | Retrieve all zones |
| `/zones/:id` | `PUT` | Update a zone |
| `/zones/:id` | `DELETE` | Delete a zone |

### Example Data Model (PostGIS)
```sql
CREATE TABLE irrigation_zones (
  id SERIAL PRIMARY KEY,
  name VARCHAR(255),
  crop_type VARCHAR(255),
  irrigation_rate FLOAT,
  color VARCHAR(20),
  geometry GEOMETRY(POLYGON, 4326),
  created_at TIMESTAMP DEFAULT NOW()
);
```

---

## ⚙️ Setup Instructions

### 1. Clone Repository
```bash
git clone https://github.com/your-org/irrigation-mapping-tool.git
cd irrigation-mapping-tool
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Environment Variables
Create a `.env` file:
```bash
MAPBOX_TOKEN=your_mapbox_token
DATABASE_URL=postgresql://user:password@localhost:5432/irrigation
```

### 4. Run Development Server
```bash
npm run dev
```

### 5. Run Backend (if separate)
```bash
cd server
npm install
npm run start
```

---

## 📦 Export & Import

### Export Options
- **GeoJSON** — preserves geometry and metadata.
- **KML** — for use in Google Earth.
- **CSV** — lists zone attributes and coordinates.

### Import Options
- Upload existing GeoJSON or shapefile.

---

## 📈 Future Enhancements
- NDVI and soil moisture overlays via Sentinel API
- AI-assisted irrigation zone detection
- Mobile optimization for fieldwork
- Integration with smart irrigation controllers

---

## 🧑‍💻 Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

---

## 📄 License
MIT License © 2025
