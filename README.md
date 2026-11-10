# Plataforma de empleo AMAC — Entrega 2 (HTML y CSS)

Proyecto final **OT2026-WEB**. Sitio web estático, escrito a mano en HTML5 semántico y CSS3, que convierte el prototipo de Figma de la Entrega 1 en páginas reales. AMAC es una plataforma de empleo pensada para **personas adultas mayores** en Monterrey y su área metropolitana, por eso el diseño cuida el tamaño del texto, el contraste y las zonas de clic amplias.

- **Repositorio:** https://github.com/potamo117/amac-web
- **Sitio publicado (Vercel):** _pendiente: pegar aquí la URL cuando se despliegue_




## Integrantes y qué hizo cada uno

| Integrante | Rol | Trabajo |
|---|---|---|
| **Luis Carlos Ramírez Mora** | Persona 1 — Líder Técnico y módulo de vacantes | Estructura del repositorio y carpetas. `css/variables.css` (tokens extraídos de Figma), `css/base.css` (reset, tipografía, foco visible, "saltar al contenido") y `css/layout.css`. Plantilla maestra: encabezado con navegación, pie de página y botón flotante de ayuda (RF-052). Páginas `index.html` (buscador, filtros y 6 tarjetas) y `vacante.html` (detalle con "Postularme" y "Llamar"). Componentes `.tarjeta-vacante`, `.buscador-filtros`, `.detalle-vacante`, `.boton`, `.etiqueta-dato` y `.boton-ayuda`. Revisión del Figma y ajustes de contraste. |
| _[Nombre Persona 2]_ | Persona 2 — Autenticación y candidatos | `login.html`, `registro-candidato.html` (con `fieldset` y `legend`), componente `.campo-formulario`, auditoría Lighthouse y pruebas responsivas. _(completar al terminar)_ |
| _[Nombre Persona 3]_ | Persona 3 — Gestión y empresa | `mis-solicitudes.html`, `empresa-vacantes.html`, componentes `.etiqueta-estatus` y `.tabla-responsiva`, validación W3C y este README. _(completar al terminar)_ |

---

## Paleta de colores (variables CSS)

Extraída del prototipo de Figma. Los valores están en [`css/variables.css`](css/variables.css).

| Variable | Valor | Uso |
|---|---|---|
| `--color-primario` | `#192943` | Botones principales, pie de página |
| `--color-cabecera` | `#202945` | Encabezado |
| `--color-acento` | `#ff815b` | Botón de acción principal, filtro activo, botón de ayuda |
| `--color-fondo-busqueda` | `#c9e4ef` | Caja de búsqueda, bloque "¿Tiene dudas?" |
| `--color-fondo-resumen` | `#ffdaae` | Resumen de la vacante |
| `--color-fondo-tarjeta` | `#fff3e3` | Tarjeta de vacante |
| `--color-borde-tarjeta` | `#fddaad` | Borde de tarjetas y etiquetas |
| `--color-texto` | `#111111` | Texto principal |
| `--color-texto-suave` | `#595757` | Texto secundario |
| `--color-exito` / `--color-error` | `#15803d` / `#b91c1c` | Estados (valores de la guía; no están en Figma) |

### Tipografías

| Variable | Fuente | Uso |
|---|---|---|
| `--fuente-titulo` | Baskervville (Google Fonts) | Títulos y marca |
| `--fuente-base` | Work Sans (Google Fonts) | Texto, botones y formularios |

Tamaño base `1.125rem` (18 px). Todo el texto está en `rem`.

---

## Ajustes respecto al prototipo de Figma

El prototipo es la referencia visual. Estos son los cambios que hicimos y por qué:

| Elemento | En Figma | En el código | Motivo |
|---|---|---|---|
| Texto blanco sobre coral (`Buscar vacantes`, filtro activo) | Blanco, contraste 2.46:1 | Texto oscuro, 8.5:1 | Accesibilidad (mínimo 4.5:1) |
| Enlace "Ver solicitudes" | Coral sobre blanco, 2.46:1 | Azul marino | Accesibilidad |
| Texto gris secundario | `#747272` (4.37:1 sobre la tarjeta) | `#595757` (6.5:1) | Accesibilidad |
| Placeholder de campos | Negro al 50 % (3.95:1) | `#595757` | Accesibilidad |
| Texto pequeño (15–16 px) | 15–16 px | mínimo 18 px (`1.125rem`) | Requisito para adultos mayores |
| Filtros | Solo modalidad | Modalidad + horario + categoría | La rúbrica los pide (RF-002) |
| Fuente | Work Sans y Baskervville | Se mantienen (no Atkinson Hyperlegible) | El Figma es la referencia |

---

## Componentes reutilizables identificados

Cada clase será un componente de React en la Entrega 3.

| Clase CSS | Componente React futuro | Dónde se usa | Responsable |
|---|---|---|---|
| `.boton` (`--primario`, `--acento`, `--secundario`, `--bloque`) | `<Boton />` | Todas las páginas | Persona 1 |
| `.etiqueta-dato` | `<EtiquetaDato />` | Tarjetas y detalle de vacante | Persona 1 |
| `.tarjeta-vacante` | `<TarjetaVacante />` | `index.html` | Persona 1 |
| `.buscador-filtros` | `<BuscadorFiltros />` | `index.html` | Persona 1 |
| `.detalle-vacante` (`__resumen`, `__ayuda`) | `<DetalleVacante />` | `vacante.html` | Persona 1 |
| `.boton-ayuda` | `<BotonAyuda />` | Todas las páginas (RF-052) | Persona 1 |
| `.encabezado` + `.navegacion` | `<Encabezado />` | Todas las páginas | Persona 1 |
| `.pie` | `<Pie />` | Todas las páginas | Persona 1 |
| `.saltar-contenido` | `<SaltarContenido />` | Todas las páginas | Persona 1 |
| `.campo-formulario` | `<CampoFormulario />` | `login.html`, `registro-candidato.html` | Persona 2 |
| `.etiqueta-estatus` | `<EtiquetaEstatus />` | `mis-solicitudes.html`, `empresa-vacantes.html` | Persona 3 |
| `.tabla-responsiva` | `<TablaResponsiva />` | `empresa-vacantes.html` | Persona 3 |

---

## Estructura del proyecto

```
amac-web/
├── index.html               Listado de vacantes, buscador y filtros
├── vacante.html             Detalle de vacante
├── login.html               Inicio de sesión
├── registro-candidato.html  Registro de candidato
├── mis-solicitudes.html     Mis solicitudes
├── empresa-vacantes.html    Panel de vacantes de la empresa
├── css/
│   ├── variables.css        Tokens de Figma
│   ├── base.css             Reset, tipografía, enlaces y foco
│   ├── layout.css           Encabezado, pie, contenedor, rejillas y media queries
│   └── componentes.css      Botones, tarjetas, formularios, etiquetas, tabla
├── img/                     Íconos SVG y capturas
└── README.md
```

## Accesibilidad aplicada

- `<html lang="es">`, un solo `<h1>` por página y jerarquía h1 → h2 → h3.
- Texto base de 1.125rem, definido en `rem` para que escale con el navegador.
- Botones y enlaces de al menos 48 px de alto, con separación entre ellos.
- Todo campo tiene `<label for>` visible; los filtros usan `fieldset` y `legend`.
- Enlace "Saltar al contenido" y botón flotante "Llamar a AMAC".
- Íconos decorativos con `alt=""`. Los enlaces repetidos ("Ver vacante") tienen `aria-label` con la vacante.
- Mobile-first: estilos base para 320 px y cambios en 768 px y 1024 px. Sin scroll horizontal.

## Capturas

**`index.html` en celular (390 px)**

![index en celular](img/captura-index-movil.png)

**`index.html` en escritorio (1440 px)**

![index en escritorio](img/captura-index-escritorio.png)

**Lighthouse – Accessibility de `index.html`**

![Lighthouse Accessibility](img/captura-lighthouse.png)

_Pendiente: guardar la captura como `img/captura-lighthouse.png`._

## Cómo ver el sitio

Abrir `index.html` en el navegador (no requiere servidor ni instalación). Para publicar: Vercel → Add New → Project → `amac-web` → Framework Preset **Other** → Deploy.

## Flujo de la demo

Listado (`index.html`) → detalle (`vacante.html`) → "Postularme" → `mis-solicitudes.html`, en celular y en escritorio.

## Verificación antes de entregar

- [ ] Validador W3C con 0 errores en las 6 páginas
- [ ] Lighthouse Accessibility ≥ 90 en `index.html`
- [ ] Navegación solo con teclado (Tab, Shift+Tab, Enter) con foco siempre visible
- [ ] Zoom al 200 % sin texto cortado ni scroll horizontal
- [ ] Pruebas en 320, 768, 1024 y 1440 px
- [ ] Sin `style=""` en línea y sin estilos repetidos