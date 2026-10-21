# CDE Virgen de Atocha FESD · Web del equipo

Web estática para GitHub Pages con resultados, clasificación, plantilla y estadísticas.
No necesita servidor ni dependencias: todo se alimenta de los archivos de la carpeta `data/`.

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub (p. ej. `atocha-fesd`) y sube el contenido de esta carpeta.
2. En el repositorio: **Settings → Pages → Build and deployment**.
3. En *Source* elige **Deploy from a branch**, rama `main`, carpeta `/ (root)`.
4. En un minuto la web estará en `https://TU-USUARIO.github.io/atocha-fesd/`.

## Actualizar los datos

Los datos oficiales están en la web de la RFFM
(<https://www.rffm.es/fichaequipo/28022265>). Tras cada jornada edita estos archivos
(puedes hacerlo desde la propia web de GitHub, botón del lápiz) y haz *commit*:

| Archivo | Qué contiene |
| --- | --- |
| `data/equipo.json` | Nombre, competición, temporada, grupo, fecha de actualización y lista de equipos |
| `data/partidos.json` | Calendario completo (182 partidos) y resultados: rellena `golesLocal` y `golesVisitante` (están en `null` si no se ha jugado) |
| `data/jugadores.json` | Plantilla y estadísticas individuales (plantilla real; las estadísticas están en `null` = "—" hasta que las rellenes) |

La **clasificación** y el **resumen de la temporada** se calculan solos a partir de los resultados
de `partidos.json`, así que basta con ir rellenando los marcadores de todos los equipos.
El calendario viene del PDF oficial de la RFFM (Primera Juvenil FS, Grupo 3, 2026-27).

## Probar en local

```
python3 -m http.server 8000
```

y abre <http://localhost:8000>.

## Nota sobre la RFFM

La web de la RFFM no permite el acceso automatizado, por eso los datos se copian a mano
(o con una exportación que facilite el club). Revisa sus condiciones de uso antes de
automatizar nada.
