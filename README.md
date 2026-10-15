# Catálogo MiniPrints

Sitio estático del catálogo para clientes. **Está separado del sistema del negocio**: otra
dirección y otro repositorio, sin ninguna conexión. No tiene contraseñas, claves ni datos del
negocio. Los productos, precios y existencias se administran aquí, a mano.

- `index.html`: la página completa (estilos y código incluidos).
- `img/`: fotos de los productos.

## Editar productos
Los productos están en `index.html`, en `const PRODUCTS = [...]`. Cada uno tiene `name`, `sub`,
`desc`, `imgs`, `specs`, `price` y `was` (precio anterior, opcional).
El número de WhatsApp va en `const WHATSAPP = ""` (solo dígitos con código de país).

## Seguridad
- Política de contenido (`Content-Security-Policy`): la página solo carga sus propios archivos y
  las fuentes de Google; no se conecta a ningún otro servicio.
