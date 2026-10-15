# Catálogo MiniPrints

Sitio estático del catálogo para clientes. **Está separado del sistema del negocio**: otra
dirección, otro repositorio y otro proyecto de Firebase. No tiene contraseñas, claves ni datos
del negocio, y no puede leer ni escribir nada del sistema.

- `index.html`: la página completa (estilos y código incluidos).
- `img/`: fotos de los productos.

## Editar productos
Los productos están en `index.html`, en `const PRODUCTS = [...]`. Cada uno tiene `name`, `sub`,
`desc`, `imgs`, `specs`, `price`, `was` (precio anterior, opcional) e `inv` (opcional, ver abajo).
El número de WhatsApp va en `const WHATSAPP = ""` (solo dígitos con código de país).

## Avisos de "Últimas piezas" y "Agotado"
El sistema de inventario publica, solo para las piezas marcadas con "Mostrar en catálogo", una
marca por pieza en el proyecto de Firebase **miniprints-catalogo** (documento `publico/estado`).
El catálogo solo la lee; nunca recibe cantidades, precios, costos, ventas ni clientes.

- `const AVISOS_PROYECTO = "miniprints-catalogo"` activa los avisos (vacío = sin avisos).
- Cada producto se enlaza con la pieza por su `inv` (o su `id` si no tiene). Es el **código** que
  aparece en el sistema en Inventario › pieza › "Mostrar en catálogo" y en Más › Catálogo.
  Ejemplo: la pieza "Lavanda Punk" tiene código `lavanda-punk`; si el producto es `id:"lavanda"`,
  agrégale `inv:"lavanda-punk"`.
- Si no se puede leer el aviso (sin internet, proyecto apagado), el catálogo se ve igual que siempre.

## Seguridad
- Política de contenido (`Content-Security-Policy`): la página solo carga sus propios archivos,
  las fuentes de Google y lee el aviso de `firestore.googleapis.com`.
- Los avisos se validan: solo se aceptan los valores `ultimas` y `agotado`; cualquier otro se ignora.
