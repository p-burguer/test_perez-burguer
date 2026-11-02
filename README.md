# Pérez Burguer

Web de Pérez Burguer (Barquisimeto) con dos partes:

| Dirección | Para quién | Qué es |
|---|---|---|
| `https://perez-burguer.github.io` | **Clientes** | Menú y pedido por WhatsApp. Es el enlace para Instagram y WhatsApp. |
| `https://perez-burguer.github.io/caja/` | **Personal** | App de caja: pedidos, cobros en $ y Bs, clientes, inventario y reportes. Funciona sin internet. |

## Archivos

```
index.html            Página de pedidos para clientes
menu.json             Menú que ve el cliente (se genera desde la caja)
icons/                Logo e iconos
caja/index.html       App de caja
caja/sw.js            Hace que la caja funcione sin internet
caja/manifest.webmanifest
```

## Publicar en GitHub Pages

1. En GitHub: **+ → New organization**, plan **Free**, nombre `perez-burguer`.
2. Dentro, crea un repositorio público llamado exactamente `perez-burguer.github.io`.
3. Pulsa **uploading an existing file** y arrastra **todo el contenido** de esta carpeta (incluidas las carpetas `icons` y `caja`). Pulsa **Commit changes**.
4. **Settings → Pages → Deploy from a branch**, rama **main**, carpeta **/ (root)**, **Save**.

## Página de pedidos (clientes)

- El cliente elige productos, indica si es **delivery o retiro**, su nombre, WhatsApp, dirección con **punto de referencia** y cómo va a pagar. Si paga en efectivo $, indica con cuánto paga para llevar el vuelto.
- Al pulsar **Enviar pedido por WhatsApp** se abre WhatsApp con el mensaje listo para el número del negocio.
- El teléfono del cliente **recuerda sus datos** y ofrece **repetir el último pedido**. Los datos se guardan solo en su teléfono y puede borrarlos.
- Los precios se muestran en dólares. Si hay tasa del día, también en bolívares.

## Actualizar el menú de la web

Cuando cambien precios o productos, o algo se agote:

1. En la caja: **Más → Publicar menú en la web → Descargar menu.json**.
2. En GitHub, en el repositorio: **Add file → Upload files**, sube `menu.json` y pulsa **Commit changes**.
3. En 1–2 minutos los clientes ven el menú nuevo. Los productos marcados como "Oculto" no salen en la web, y los que no tienen ingredientes salen como "Agotado por hoy".

## App de caja (personal)

- Se abre en `perez-burguer.github.io/caja/` y se instala desde Chrome: **⋮ → Instalar aplicación**.
- Funciona sin internet. Los datos se guardan en el dispositivo: haz una **copia de seguridad** cada noche (**Más → Copia de seguridad**).
- Cada día: actualizar la **tasa** al abrir y revisar **Más → Reportes** al cerrar.

## Próximas versiones

- **v2:** caja y cocina sincronizadas en varios dispositivos. Los pedidos de la web entran directamente en la caja y los clientes pueden entrar con Google o con un código por correo.
- **v3:** cobro con Pago Móvil C2P.

## Actualizar la app de caja

Si cambias `caja/index.html`, sube también `caja/sw.js` con la línea `VERSION` cambiada (por ejemplo `pb-caja-v1.1.1`) para que los dispositivos reciban la versión nueva.
