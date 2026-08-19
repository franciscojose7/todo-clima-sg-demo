# Todo Clima SG — Landing page

Landing page para **Todo Clima SG**, servicio de aire acondicionado y electricidad en Montevideo, Uruguay.

🔗 **Demo:** _(se completa cuando se active GitHub Pages)_
📱 **Cliente:** [@todoclima_serviciosgenerales](https://www.instagram.com/todoclima_serviciosgenerales/) · [Google Maps](https://maps.app.goo.gl/MvtbuDPWQYenWd8c8) · 094 677 178

---

## Qué es

Un solo archivo HTML autocontenido (`index.html`), sin build, sin framework y sin dependencias que haya que instalar. CSS y JavaScript van inline. Se abre con doble clic y funciona.

Dependencias externas (dos, ambas opcionales para que la página funcione):

| Recurso | Para qué | Si falla |
|---|---|---|
| Google Fonts — Sora + Inter | tipografías | cae a la tipografía del sistema |
| iframe de Google Maps | mapa del local | queda un bloque gris |

## Publicar

### Opción A — GitHub Pages (gratis, ya está configurado)

El workflow `.github/workflows/pages.yml` publica solo con cada push a `main`.
Hay que habilitarlo una vez: **Settings → Pages → Source: GitHub Actions**.

Queda en `https://<usuario>.github.io/<repo>/`.

### Opción B — Netlify / Vercel / Cloudflare Pages

Arrastrar la carpeta o conectar el repo. No hay comando de build: el directorio raíz ya es el sitio.

### Dominio propio

Cuando el cliente tenga dominio, crear un archivo `CNAME` en la raíz con el dominio adentro
(ej. `todoclimasg.com.uy`) y apuntar el DNS a GitHub Pages.

---

## Estructura

```
index.html                     todo el sitio
fotos/                         fotos de trabajos (ver fotos/LEEME.md)
.github/workflows/pages.yml    deploy automático a GitHub Pages
.nojekyll                      evita que Jekyll procese los archivos
```

---

## Decisiones de diseño

La paleta sale del logo del cliente: negro, **oro `#F5B324`** para el calor y **celeste `#34AEE8`** para el frío. Esa dualidad frío/calor es el eje gráfico de toda la página.

Tres bloques hacen el trabajo comercial:

**1. Triage por síntoma.** Seis tarjetas ("prende pero no enfría", "tira agua para adentro", "salta la térmica", "me mudo y quiero llevarlo"…). Cada una abre WhatsApp con el mensaje ya redactado, así el cliente no tiene que explicar nada y el negocio recibe la consulta ya clasificada.

**2. Bloque estacional.** Hoy vende *service de pretemporada*: en diciembre no hay agenda en ningún servicio técnico de Montevideo y el que llama con 35 grados paga la urgencia. **Este texto hay que rotarlo** — ver más abajo.

**3. Calculadora de BTU.** m² × 600 × factor de sol × extras, redondeado a las medidas que se venden en plaza (9/12/18/24/30/36 mil BTU). El CTA sale a WhatsApp con el metraje y la medida ya escritos en el mensaje.

Todos los CTA usan `wa.me/59894677178` en lugar del `wa.link` del cliente, porque `wa.link` no admite texto precargado.

### SEO

- `HVACBusiness` en JSON-LD con dirección, teléfono, zona de cobertura y el rating 5,0 / 23 reseñas → habilita rich results en Google.
- Title y meta description orientados a "aire acondicionado Montevideo" + los servicios.
- Un solo `<h1>`, jerarquía de headings correcta, `lang="es-UY"`.

---

## Mantenimiento

### Rotar el bloque de temporada

En `index.html`, sección `id="service"`, dentro de `<div class="season">`:

| Cuándo | Mensaje que conviene |
|---|---|
| **Ago – Nov** | Service de pretemporada: "en diciembre no hay agenda" ← es el texto actual |
| **Dic – Feb** | Temporada alta: disponibilidad, urgencias, "instalamos esta semana" |
| **Mar – Jul** | Modo calor: el aire como calefacción, consumo frente a otras opciones |

### Cambiar teléfono o WhatsApp

El número aparece en varios lugares. Buscar y reemplazar en todo el archivo:

- `59894677178` — todos los links de WhatsApp
- `+59894677178` — links `tel:` y el JSON-LD
- `094 677 178` — el texto visible

---

## Pendientes de confirmar con el cliente

Todo lo que sigue está en la página con un valor conservador, para no inventar datos:

- [ ] **Fotos** de trabajos — hay 4 slots vacíos (ver `fotos/LEEME.md`)
- [ ] **Horarios exactos** — Google solo dice que cierran 18 h; hoy figura "lunes a viernes hasta las 18 h"
- [ ] **Zona de cobertura real** — hoy: Montevideo, Ciudad de la Costa, Canelones, Costa de Oro
- [ ] **Plazo de garantía** — está redactado en genérico ("el plazo se confirma en el presupuesto"). Si tienen un plazo fijo, ponerlo: vende más
- [ ] **Marcas** con las que trabajan — no se listaron para no inventar (en Instagram se vio AUX)
- [ ] **Reseñas** — se citaron 3 de Google con el nombre abreviado; confirmar que están cómodos
- [ ] **Cargar el sitio en su ficha de Google Business** una vez publicado. Hoy la ficha no tiene web: es el mayor salto de conversión disponible, y es gratis

---

## Licencia

Trabajo hecho para Todo Clima SG. El contenido, la marca y las fotos son del cliente.
