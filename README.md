# 🏠 ArriendoMapa Chile

> Plataforma **gratuita** con IA para buscar casas en arriendo en Chile. Mapa interactivo de toda la Región Metropolitana, scoring de locomoción, filtros por rangos y asistente de búsqueda en lenguaje natural.

![Status](https://img.shields.io/badge/status-MVP-green) ![Comunas](https://img.shields.io/badge/comunas-18-blue) ![Avisos](https://img.shields.io/badge/avisos-136-orange) ![Metro](https://img.shields.io/badge/líneas%20metro-8-red) ![Inundación](https://img.shields.io/badge/puntos_cr%C3%ADticos_lluvia-154-blue) ![License](https://img.shields.io/badge/license-MIT-lightgrey)

## 🎯 ¿Qué es?

Una alternativa gratuita y abierta a los portales de arriendo tradicionales. En vez de scrollear listados infinitos, el usuario escribe **qué busca como hablaría** y la plataforma filtra el mapa completo de Santiago.

```
"3 dormitorios en Ñuñoa hasta 800 mil cerca del metro"
```

→ filtra por comuna, presupuesto, dormitorios y cercanía al Metro en una sola acción.

## ✨ Características

| Módulo | Descripción |
|---|---|
| 🗺️ **Mapa Santiago completo** | 19 comunas, tiles CARTO, zoom y navegación libre |
| 🚇 **Red Metro real** | 8 líneas con color oficial y 126 estaciones reales (OpenStreetMap) |
| 🔍 **Búsqueda por texto** | Filtra por sector, comuna y características (asistente IA con Claude API: en desarrollo) |
| 🎚️ **Filtros por rangos** | Precio min/max, m², dormitorios, baños, comuna, distancia al Metro |
| 💧 **Riesgo de invierno** | 154 puntos críticos oficiales geocodificados (GORE RM, jul-2026) + canal San Carlos y Zanjón de la Aguada; nivel de riesgo por propiedad |
| 🚌 **Locomoción real (GTFS)** | Recorridos de micros, buses/hora en punta, paradero y Metro más cercanos, desde el GTFS de Red Movilidad (DTPM) |
| ⭐ **Score 0–100** | Locomoción combinada (Metro + micros + frecuencia) y precio $/m² vs mediana comunal |
| ✨ **Amenidades** | Estacionamiento, mascotas, piscina, condominio |
| 🏠 **Fichas con fotos** | Galería, calles cercanas, estado del precio y link al aviso original |
| 📱 **Responsive** | Panel lateral colapsable en móvil |

## 🏗️ Stack

- **Frontend**: HTML + CSS + JavaScript vanilla (sin build, sin dependencias pesadas)
- **Mapa**: Leaflet + CARTO basemaps
- **Datos**: OpenStreetMap (Metro y calles, ODbL), portales inmobiliarios (avisos), GORE RM (puntos críticos de lluvia), DTPM Red Movilidad (GTFS)
- **Dataset**: `datos.js` plano (~460 KB) con riesgo de inundación y locomoción precalculados por propiedad

> Estructura inspirada en [CotizadorIA-v2](https://github.com/mat1dtsc/CotizadorIA-v2) (proyecto de Demian), adaptada al dominio inmobiliario.

## 🚀 Uso

```bash
# Clonar
git clone https://github.com/mat1dtsc/arriendo-mapa-chile.git
cd arriendo-mapa-chile

# Abrir (no requiere instalación)
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

O servir con cualquier servidor estático:
```bash
npx serve .            # Node
python -m http.server  # Python
```

## 📁 Estructura

```
arriendo-mapa-chile/
├── index.html   # App completa (mapa + filtros + fichas + búsqueda)
├── data.js      # Dataset comprimido (avisos + red Metro + estaciones)
└── README.md
```

## 🗺️ Roadmap

- [x] Mapa interactivo Santiago completo
- [x] Red Metro real con 8 líneas y 126 estaciones
- [x] Filtros por rangos y amenidades
- [x] Scoring de locomoción 1–5
- [x] Búsqueda en lenguaje natural
- [x] Dataset comprimido para carga rápida
- [ ] **Backend con Supabase** — avisos en base de datos, actualización en vivo
- [ ] **Publicar aviso** — formulario para dueños/corredoras
- [ ] **Más regiones** — Valparaíso, Concepción, La Serena
- [ ] **Alertas por correo** — aviso cuando aparezca algo que calce
- [ ] **Scoring expandido** — seguridad, colegios, áreas verdes (datos públicos)

## 🤝 Contribuir

1. Fork el repo
2. Crea una rama (`git checkout -b feature/mejora`)
3. Commit (`git commit -m 'feat: mejora'`)
4. Push y abre un Pull Request

## ⚖️ Datos y licencia

- **Avisos de Puente Alto**: extraídos de portales públicos (Portal Inmobiliario, TOCTOC, ChilePropiedades) el 19-jul-2026, con link a la fuente original. Cada aviso pertenece a su corredora/dueño.
- **Red Metro**: © OpenStreetMap contributors (ODbL).
- **Código**: MIT — úsalo, modifícalo, compártelo.

---

**ArriendoMapa Chile** — porque encontrar casa no debería costar plata 🏠
