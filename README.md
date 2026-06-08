# 서울 단관극장 아카이브
**Seoul Single-Screen Cinema Archive · 1910–2024**

An interactive map documenting the rise and disappearance of Seoul's single-screen cinemas — from the city's first permanent movie house in 1910 to the last neighborhood theaters shuttered by the multiplex era.

→ **[Live Demo](https://your-username.github.io/seoul-cinema-map)**

---

## Overview

Seoul's single-screen cinemas were once the cultural heartbeat of the city — neighborhood landmarks, political stages, and social gathering points before the multiplex era. This archive maps 36 cinemas across Seoul (1910–2024), surfacing their histories through structured data and interactive visualization.

Built as a data-driven urban history project combining archival research with frontend visualization.

---

## Features

- **Interactive Leaflet.js map** — Stamen Toner Lite basemap for a clean, editorial feel
- **Retro-editorial design** — sepia palette, serif typography, film strip accents
- **Filterable by district (구) and status** —폐관 / 철거 / 전환 / CGV전환
- **Popup detail cards** — name, operating years, address, current use, historical notes
- **Color-coded markers** — status at a glance (폐관/철거/전환)
- **Sidebar cinema list** — synced with map markers; click to fly to location

---

## Dataset

`data.js` contains 36 cinemas with the following fields:

| Field | Description |
|-------|-------------|
| `name` | Korean name of cinema |
| `open` | Opening year |
| `close` | Closing year |
| `status` | 폐관 / 철거 / 전환 / CGV전환 / 개명 |
| `gu` | District (구) |
| `address` | Historical address |
| `current` | Current use of the site |
| `lat` / `lng` | Approximate coordinates |
| `note` | Historical notes |

### Data Sources
- Korean Film Archive (한국영상자료원) KMDB
- Seoul History Archive (서울역사아카이브)
- Seoul Memory project (서울기억)
- Namu Wiki 영화관/한국
- Dongdaemun-gu Memory Travel (동대문구 기억여행)
- Newspaper archives (경향신문, 오마이스타)

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Map | [Leaflet.js](https://leafletjs.com/) v1.9.4 |
| Tiles | [Stadia Maps / Stamen Toner Lite](https://stadiamaps.com/) |
| Fonts | Noto Serif KR, Playfair Display, IBM Plex Mono |
| Data | Hand-curated JS dataset |
| Build | Vanilla HTML/CSS/JS — zero dependencies beyond Leaflet |

No bundler, no framework. Opens directly in a browser.

---

## Getting Started

```bash
git clone https://github.com/your-username/seoul-cinema-map.git
cd seoul-cinema-map

# Just open index.html in a browser
open index.html

# Or serve locally (avoids any CORS issues)
python3 -m http.server 8000
# → http://localhost:8000
```

---

## Project Structure

```
seoul-cinema-map/
├── index.html      # Map interface + UI
├── data.js         # Cinema dataset (36 entries)
└── README.md
```

---

## Extending the Data

To add a cinema, append an entry to the `cinemas` array in `data.js`:

```js
{
  name: "극장이름",
  open: 1970, close: 1995, status: "폐관",
  gu: "종로구", address: "서울 종로구 ...",
  current: "현재 용도",
  lat: 37.5700, lng: 126.9900,
  note: "역사적 메모."
},
```

Coordinates can be found via [Kakao Maps](https://map.kakao.com) or [Google Maps](https://maps.google.com).

---

## Roadmap

- [ ] Add historical photographs per cinema
- [ ] Timeline slider to show cinemas by era
- [ ] Expand to other Korean cities (부산, 대구, 인천)
- [ ] Mobile-responsive layout
- [ ] Export data as CSV / GeoJSON

---

## License

Data compiled from public historical sources for non-commercial research and educational use.  
Code: MIT License.

---

*"극장이 도시의 랜드마크였던 시절이 있었다."*  
*There was a time when cinemas were the landmarks of the city.*
