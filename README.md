# IA Productiva — Landing page

Landing page para promocionar los programas de formación en IA para pymes,
bonificables vía FUNDAE.

Sitio estático (un único `index.html`, sin build ni dependencias). Estilo con
Tailwind CSS (CDN) y tipografía Fraunces + Inter.

## Estructura

- **index.html** — la página completa (hero, resultados, método, programas, FUNDAE, formulario).

## Formulario de contacto

El formulario envía las solicitudes al correo mediante [Web3Forms](https://web3forms.com)
(sin backend). Para activarlo:

1. Entra en https://web3forms.com y genera una **Access Key** con el correo
   `david.montesinosg@gmail.com`.
2. En `index.html`, sustituye `TU_ACCESS_KEY` por la clave generada.
3. Listo: cada envío llega a ese correo.

> Nota: mientras la clave sea `TU_ACCESS_KEY`, el formulario mostrará un error al enviar.

## Base de datos (opcional, más adelante)

Para empezar no hace falta. Si en el futuro quieres un panel de leads
(ver/filtrar/exportar las solicitudes como un mini-CRM), se puede añadir
**Supabase** guardando cada envío en una tabla `leads`.

## Despliegue

Desplegado en **Vercel** (importando este repositorio de GitHub). Cada `push`
a `main` publica automáticamente.

## Desarrollo local

Al ser estático, basta con abrir `index.html` en el navegador. Opcionalmente:

```bash
python -m http.server 8000
# http://localhost:8000
```
