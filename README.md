# eUNLP Caster Overlay

Overlay de roster para transmisiones de League of Legends en OBS Studio. Incluye equipos rojo y azul, emblemas por posición, búho central con segmentos luminosos animados y carga de roster desde `players.json`.

## Contenido

- `overlay3.html` — interfaz y lógica del overlay.
- `owl-eunlp.svg` — símbolo del búho utilizado en el centro.
- `players.json` — roster de demostración con nombres e identificadores ficticios.
- `LICENSE` — licencia MIT para el código original de este proyecto, con las exclusiones indicadas en `ASSETS-NOT-LICENSED.md`.
- `ASSETS-NOT-LICENSED.md` — aclaración sobre marcas, logos y recursos de terceros.

## Uso en OBS Studio

1. Descargá o cloná este repositorio.
2. En OBS, agregá una **Fuente de navegador**.
3. Activá **Archivo local** y seleccioná `overlay3.html`.
4. Configurá el ancho y alto según tu escena (por ejemplo, 1920 × 1080).
5. Mantené `players.json` y `owl-eunlp.svg` en la misma carpeta que `overlay3.html`.

Si el navegador integrado no puede leer `players.json` desde el archivo local, serví la carpeta mediante un servidor HTTP local y usá la URL correspondiente en la Fuente de navegador. Por ejemplo:

```bash
python -m http.server 8000
```

Luego configurá la URL `http://127.0.0.1:8000/overlay3.html`.

## Editar los equipos

Editá `players.json`. Cada equipo contiene:

- `name`: nombre del equipo.
- `color`: color del panel en formato hexadecimal.
- `players`: lista de cinco jugadores.
- `role`: posición (`Top`, `Jungla`, `Mid`, `ADC` o `Support`).
- `realName`: nombre que se muestra como nombre principal.
- `username`: identificador precedido por `@` en el overlay.

El archivo incluido contiene únicamente datos ficticios de demostración. Reemplazalos antes de utilizar el overlay en una transmisión real.

El HTML también contempla una fuente CSV publicada desde Google Sheets. Para utilizarla, cambiá `source` a `"sheet"` y completá `sheetCsvUrl` en la constante `CONFIG` dentro de `overlay3.html`.

## Licencia

El código original de este proyecto se distribuye bajo MIT. El búho institucional, marcas, logos, nombres de jugadores y otros recursos de terceros no quedan licenciados por MIT. Consultá `ASSETS-NOT-LICENSED.md` antes de reutilizarlos.
