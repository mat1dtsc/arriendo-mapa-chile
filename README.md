# 🏠 ArriendoMapa Chile

> Plataforma **gratuita** con IA para buscar casas en arriendo en Chile. Mapa interactivo de toda la Región Metropolitana, scoring de locomoción, filtros por rangos y asistente de búsqueda en lenguaje natural.

![Status](https://img.shields.io/badge/status-MVP-green) ![Comunas](https://img.shields.io/badge/comunas-19-blue) ![Avisos](https://img.shields.io/badge/avisos-111-orange) ![Metro](https://img.shields.io/badge/líneas%20metro-8-red)

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
| 🔍 **Búsqueda en lenguaje natural** | Interpreta presupuesto, dormitorios, comuna, locomoción |
| 🎚️ **Filtros por rangos** | Precio min/max, m², dormitorios, baños, comuna, distancia al Metro |
| ⭐ **Scoring 1–5** | Locomoción (Metro + paraderos) y precio por m², calculados con datos reales |
| ✨ **Amenidades** | Estacionamiento, mascotas, piscina, condominio |
| 🏠 **Fichas con fotos** | Galería, calles cercanas, estado del precio y link al aviso original |
| 📱 **Responsive** | Panel lateral colapsable en móvil |

## 🏗️ Stack

- **Frontend**: HTML + CSS + JavaScript vanilla (sin build)
- **Mapa**: Leaflet + CARTO basemaps
- **Datos**: OpenStreetMap (Metro), portales inmobiliarios (avisos Puente Alto)
- **Todo local**: sin backend, sin dependencias pesadas, abre al instante

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
├── data.js      # Dataset: avisos + red Metro + estaciones
└── README.md
```

## 🗺️ Roadmap

- [x] Mapa interactivo Santiago completo
- [x] Red Metro real con 8 líneas
- [x] Filtros por rangos y amenidades
- [x] Scoring de locomoción 1–5
- [x] Búsqueda en lenguaje natural
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
