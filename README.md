# canta — sitio de soporte y políticas

Sitio estático que sirve las dos URL públicas que exigen App Store y Google Play:
la política de privacidad y la página de soporte. Nada más.

No hay build ni dependencias: son ficheros HTML y una hoja de estilos. GitHub Pages
los publica tal cual desde `main`.

## Páginas

| Ruta               | Para qué                                          |
| ------------------ | ------------------------------------------------- |
| `index.html`       | Portada (ES) — descripción de la app              |
| `en.html`          | Portada (EN)                                      |
| `privacidad.html`  | Política de privacidad (ES) → `privacyPolicyUrl`  |
| `privacy.html`     | Política de privacidad (EN) → `privacyPolicyUrl`  |
| `soporte.html`     | Soporte (ES) → Support URL de App Store Connect   |
| `support.html`     | Soporte (EN) → Support URL de App Store Connect   |

## Dónde se usan estas URL

- **App Store Connect** → Información de la app → Política de privacidad, y
  Support URL. También en `store.config.json` del proyecto de la app, en
  `apple.info.<locale>.privacyPolicyUrl`, para poder subirlas con
  `eas metadata:push`.
- **Play Console** → Contenido de la aplicación → Política de privacidad.

## Cuidado con esto

Cada afirmación de la política está verificada contra el código de la app: sin red,
sin analítica, sin anuncios, sin compras, y el audio del micrófono nunca se escribe
a disco.

**Si la app cambia en cualquiera de esos puntos, la política deja de ser cierta** y
hay que corregirla aquí antes de publicar la nueva versión. Prometer «no recopilamos
nada» y luego recopilar es exactamente el tipo de cosa por la que Apple retira una
app.

## Editar

Cambia el HTML y haz push a `main`. Pages republica en un minuto o dos.
