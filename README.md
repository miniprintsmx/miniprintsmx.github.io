# Catálogo MiniPrints

Sitio estático del catálogo para clientes. **Está separado del sistema del negocio**: otra
dirección y otro repositorio, sin ninguna conexión. No tiene contraseñas, claves ni datos del
negocio. Los productos, precios y existencias se administran aquí, a mano.

- `index.html`: la página completa (estilos y código incluidos).
- `img/`: fotos de los productos.

## Editar productos (sin código)
Abre **https://miniprintsmx.github.io/admin.html**, entra con tu llave de GitHub y desde ahí
agrega, edita, ordena o quita productos y fotos, y edita las categorías. Al tocar **Publicar**,
todo se guarda en un solo cambio en este repositorio y el catálogo se actualiza en 1 o 2 minutos.

- Los productos y categorías viven en `productos.json`; las fotos en `img/` (JPG 1000 × 1000).
- La llave es un *fine-grained token* de GitHub solo para este repositorio, con permiso
  **Contents: Read and write**. Se guarda únicamente en tu dispositivo.
- El número de WhatsApp va en `index.html`, en `const WHATSAPP = "..."`.

## Seguridad
- Política de contenido (`Content-Security-Policy`): el catálogo solo carga sus propios archivos y
  las fuentes de Google; no se conecta a ningún otro servicio. La administración solo habla con
  `api.github.com`.
- Todo texto de `productos.json` se muestra como texto (escapado) y se validan los códigos,
  colores y nombres de foto antes de usarlos.
