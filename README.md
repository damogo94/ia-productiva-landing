# Innovai — Landing page

Landing de **Innovai** (inteligencia artificial para empresas) para captar leads de pymes:
formación en IA bonificable vía FUNDAE + consultoría y automatización. La conversión
principal es el formulario de diagnóstico (wizard de 4 pasos).

Sitio estático sin build: CSS propio escrito a mano (sin frameworks ni CDN) + Inter variable autoalojada. Rediseño «Primera Plana» (editorial: hairlines, cifras-hito con count-up, data-viz SVG honesta, 3 portadas oscuras).

## Estructura

- **index.html** — la página completa (hero, credibilidad, problema, método, departamentos, FUNDAE, subvenciones, casos, calculadora, formulario wizard, FAQ).
- **aviso-legal.html · privacidad.html · politica-cookies.html** — páginas legales *(en borrador: pendientes de validación jurídica y de los datos del responsable)*.
- **fonts/inter-var.woff2** — Inter variable (400–700, subset latino), única familia del sitio, con preload y fallback métrico anti-CLS.
- **apple-touch-icon.png** — icono iOS (el favicon es SVG inline con el nodo de la marca).

## Identidad

Wordmark **Innovai** como componente SVG inline (`<symbol>`: variantes `wordmark`, `full`, `mark`):
"Innov" en Inter 500 + "aı" en Inter 700, con el punto de la ı sustituido por el **nodo**
(cuadrado rotado 45° en el acento cian). Sistema de tokens **OKLCH** documentado en el
`<style>` de `index.html` con los ratios WCAG verificados; el acento tiene presupuesto
cerrado (nodo del logo, focus/active, cifras clave y CTA secundario).

## Formulario de contacto

El formulario envía las solicitudes por email mediante [Web3Forms](https://web3forms.com) (sin backend).

1. Genera una **Access Key** en web3forms.com con el correo de destino.
2. En `index.html`, sustituye `TU_ACCESS_KEY` (input hidden `access_key`).
3. Cada envío llega a ese correo con los datos del wizard **y de la calculadora de ahorro**.

> ⚠️ Mientras la clave sea `TU_ACCESS_KEY`, el formulario mostrará el estado de error al enviar.

## Pendientes antes de publicar

- Access Key real de Web3Forms.
- Dominio definitivo en `canonical`, Open Graph y JSON-LD (`TU-DOMINIO.com`) + `og-image.png` 1200×630.
- Nº de registro FUNDAE y datos del responsable (razón social, NIF, email) en la franja de credibilidad, la capa RGPD del formulario y las páginas legales.
- Cambiar `<meta name="robots">` de `noindex` a `index,follow`.
- Caso real para la antigua sección «casos» (retirada temporalmente del HTML; el bloque original está en el historial de git). Reintroducir como un caso anónimo contado en cifras.

## Despliegue

Desplegado en **Vercel** (importando este repositorio de GitHub). Cada `push`
a `main` publica automáticamente.

## Desarrollo local

```bash
python -m http.server 4321
# http://localhost:4321
```
