# El Observador de Lanzarote — código del sitio

Esto es el andamiaje del sitio. El diseño reproduce la maqueta que ya aprobaste
(cabecera con color sólido, tarjetas con foto, ficha de caso con cita separada
del análisis). Lo que falta es contenido: cada ficha nueva es un archivo,
nada de tocar HTML.

## Cómo añadir una ficha nueva

1. Copia `_fichas/2026-09-14-playa-honda-recogida-enseres.md` (es el ejemplo)
   y ponle un nombre nuevo con el formato `AAAA-MM-DD-titulo-corto.md`, dentro
   de la carpeta `_fichas/`.
2. Rellena las cabeceras (entre las líneas `---`):
   - `title`: el titular de la ficha.
   - `date`: fecha de publicación en el sitio.
   - `ayuntamiento`: "San Bartolomé" o "Teguise" (tal cual, con tilde) — de
     esto depende el color de la etiqueta.
   - `tema`: el tema (Residuos, Urbanismo, Presupuestos...).
   - `expediente`: número de ficha, para el sello tipo "FICHA Nº 002".
   - `dek`: una frase de resumen para la portada.
   - `cita`: la cita textual entre comillas «así».
   - `medio_fuente`, `fecha_fuente`, `enlace_fuente`: la atribución completa
     — esto es obligatorio por el modelo de derecho de cita, no lo dejes vacío.
   - `foto_descripcion`: qué muestra la foto (para el texto alternativo y el
     hueco mientras no hay foto real).
   - `foto`: déjalo comentado (con `#` delante) hasta que subas la imagen de
     verdad a `assets/images/` — entonces quita el `#` y pon la ruta.
3. Debajo de la segunda línea `---`, escribe el análisis (tu comentario,
   como opinión razonada o pregunta retórica) en markdown normal. Eso es lo
   que se ve como el texto de "Análisis" en la ficha.
4. Guarda, y sube el archivo a GitHub (ver más abajo). El sitio se reconstruye
   solo en 1-2 minutos.

Cuando tengas contenido real, borra o renombra la ficha de ejemplo
(`2026-09-14-playa-honda-recogida-enseres.md`) para que no se quede ahí como
si fuera de verdad.

## Fotos

De momento cada ficha muestra un hueco de color con el texto "Fotografía
ilustrativa" si no hay foto. Cuando tengas la imagen (banco gratuito o
generada por IA, nunca del hecho concreto):

1. Súbela a `assets/images/` con un nombre corto sin espacios ni tildes
   (ej. `playa-honda-residuos.jpg`).
2. En la ficha, descomenta la línea `foto:` y pon `/assets/images/nombre.jpg`.

## Columna "Contrapunto" (opinión del alcalde + reacción ciudadana)

Aparece a la derecha de la portada y tiene su propia página ampliada al hacer
clic. Muestra, una junto a la otra, una cita de una columna de opinión real
publicada por un alcalde y una cita de la reacción ciudadana ya publicada
sobre ese mismo asunto — con tu análisis debajo. Es el mismo modelo de
derecho de cita que las fichas normales, pero con dos fuentes en vez de una.

Para añadir una pieza nueva:

1. Copia `_contrapunto/PLANTILLA-no-publicar.md` con un nombre nuevo
   (`AAAA-MM-DD-titulo-corto.md`), dentro de la carpeta `_contrapunto/`.
2. Rellena los corchetes `[...]` con datos reales. Las dos citas
   (`cita_alcalde` y `cita_ciudadana`) tienen que ser literales y venir de
   algo que un medio real ya haya publicado — nunca las inventes, ni siquiera
   como borrador. Si todavía no tienes las dos fuentes reales, deja el
   archivo tal cual, con `published: false`, hasta que las tengas.
3. Cuando esté todo listo, quita la línea `published: false` (o cámbiala a
   `published: true`) y sube el archivo a GitHub como cualquier otro cambio.

Mientras no haya ninguna pieza publicada, la columna de la derecha muestra
un aviso en lugar de quedar vacía o inventarse contenido.

## Identidad separada de este proyecto

Este sitio vive en una cuenta de GitHub dedicada y separada de tus cuentas
personales (`raflee4444`) y de El Pringao (`confesionesdeunpringao`):

- Gmail dedicado: `elobservatoriodelanzarote@gmail.com`
- Usuario de GitHub: `elobservadordelanzarote`
- Repositorio: `elobservadordelanzarote/elobservadordelanzarote.github.io`
  (el nombre exacto `<usuario>.github.io` hace que el sitio quede en la raíz,
  sin ninguna carpeta detrás en la URL)

No mezcles esta cuenta con tu Chrome habitual ni con el de El Pringao — usa
siempre la ventana/perfil dedicada para tocar este repositorio.

## Publicar una ficha nueva (o cualquier cambio)

El repositorio y GitHub Pages ya están activados. Para publicar un cambio,
la forma más sencilla sin usar terminal es subir el archivo directamente
desde la web de GitHub:

1. Entra en el repositorio (con la sesión de `elobservadordelanzarote` ya
   iniciada) → botón **Add file → Upload files**.
2. Arrastra el archivo nuevo o modificado a la carpeta correspondiente
   (por ejemplo, una ficha nueva va dentro de `_fichas/`).
3. Abajo, en "Commit changes", escribe un mensaje breve (ej. "Nueva ficha:
   recogida de enseres") y pulsa **Commit changes**.
4. En 1-2 minutos el sitio se reconstruye solo y el cambio ya está en
   `https://elobservadordelanzarote.github.io/`.

Si en algún momento prefieres trabajar con `git` desde una terminal en esta
carpeta, también puedes — el repositorio remoto es:
`https://github.com/elobservadordelanzarote/elobservadordelanzarote.github.io.git`
y, si haces commits desde tu máquina, usa una identidad de commit separada
de la tuya real:

```
git -c user.name="Observador" -c user.email="elobservatoriodelanzarote@gmail.com" commit -m "..."
```

## Si más adelante compras un dominio propio

Cambia en `_config.yml` la línea `url:` por tu dominio (ej.
`https://elobservadordelanzarote.com`) y deja `baseurl:` vacío (ya lo está).
Luego, en GitHub → Settings → Pages, añade el dominio en "Custom domain" y
sigue las instrucciones de GitHub para los registros DNS. GitHub Pages sigue
siendo gratis; solo pagas el dominio en sí (10-15 €/año aprox.).

## Cosas que ya vienen automáticas

- **Sitemap** (`/sitemap.xml`) y **RSS** (`/feed.xml`): se generan solos con
  cada ficha nueva, no hay que tocar nada.
- El **perfil bajo** ya está aplicado: no hay ninguna navegación en portada
  que liste San Bartolomé y Teguise juntos — cada ficha lleva su etiqueta
  individual, como en cualquier pieza periodística.
