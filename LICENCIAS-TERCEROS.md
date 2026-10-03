# OptiZip — licencias de terceros

OptiZip es **gratuito**. Los motores de esta lista se incluyen **sin modificar**, como programas independientes
en la carpeta `resources\bin` del portable, y OptiZip los ejecuta como procesos aparte. Los textos completos de
cada licencia y este mismo listado (`FUENTES.txt`) van en la carpeta **`licencias`** junto a `OptiZip.exe`.

| Motor | Versión | Licencia | Para qué lo usa OptiZip | Código fuente |
|---|---|---|---|---|
| 7-Zip (Igor Pavlov) | 26.00 | GNU LGPL-2.1 + restricción unRAR | Comprimir, extraer, listar, editar, cifrar, autoextraíbles | [7z2600-src.7z](https://www.7-zip.org/a/7z2600-src.7z) · [GitHub ip7z/7zip 26.00](https://github.com/ip7z/7zip/releases/tag/26.00) |
| par2cmdline | 1.4.0 | GNU GPL-2.0 | Crear, verificar y reparar datos PAR2 | [Parchive/par2cmdline v1.4.0](https://github.com/Parchive/par2cmdline/tree/v1.4.0) |
| oxipng | 10.2.1 | MIT | Optimizar PNG sin pérdida | [oxipng v10.2.1](https://github.com/oxipng/oxipng/tree/v10.2.1) |
| libjpeg-turbo (jpegtran, djpeg) | 3.2.0 | IJG / BSD-3-Clause / zlib | Optimizar JPG sin pérdida y comprobar los píxeles | [libjpeg-turbo 3.2.0](https://github.com/libjpeg-turbo/libjpeg-turbo/tree/3.2.0) |
| qpdf | 12.4.2 | Apache-2.0 | Optimizar PDF sin pérdida | [qpdf v12.4.2](https://github.com/qpdf/qpdf/tree/v12.4.2) |
| libjxl (cjxl, djxl) | 0.12.0 | BSD-3-Clause | Modo Máximo (.ozx): JPEG → JPEG XL reversible | [libjxl v0.12.0](https://github.com/libjxl/libjxl/tree/v0.12.0) |
| precomp (Christian Schneider) | 0.4.7 | Apache-2.0 (código) | Modo Máximo (.ozx): PDF, PNG, ZIP/Office/APK, GZIP y JPG (packJPG) | [precomp-cpp v0.4.7](https://github.com/schnaader/precomp-cpp/tree/v0.4.7) |
| └ packJPG (dentro de precomp) | 2.5k | GNU LGPL-3.0 | Modo Máximo: JPG | [packjpg/packJPG](https://github.com/packjpg/packJPG) (y `contrib/packjpg` en precomp v0.4.7) |
| └ preflate (dentro de precomp) | 0.3.5 | Apache-2.0 | Modo Máximo: flujos Deflate | `contrib/preflate` en [precomp-cpp v0.4.7](https://github.com/schnaader/precomp-cpp/tree/v0.4.7) |
| Electron (con Chromium y Node.js) | 44.5.1 | MIT (Chromium: avisos en `Chromium-LICENSES.html`) | La ventana del programa | [electron v44.5.1](https://github.com/electron/electron/tree/v44.5.1) |

## Notas

- **Restricción unRAR (7-Zip)**: el código de RAR solo puede usarse para abrir archivos .rar, nunca para crearlos.
  Por eso OptiZip **no crea .rar**.
- **GPL-2.0 (par2cmdline) — oferta de código fuente**: el `par2.exe` incluido es el binario oficial
  `par2cmdline-1.4.0-win-x64.zip` del proyecto, sin cambios (SHA-256
  `cbf0e53b209d7a410c79f995f9662baa1743d90378d84d943744573a49d36efb`, comprobado). Su código fuente completo es el de la
  etiqueta v1.4.0: https://github.com/Parchive/par2cmdline/tree/v1.4.0
- **precomp 0.4.7**: el código de esa versión se publica con licencia Apache-2.0, pero el binario para Windows aún
  muestra el texto antiguo «ALPHA version … Free for non-commercial use». OptiZip es gratuito y no se vende.
  Además, OptiZip no confía en precomp a ciegas: cada archivo transformado se reconstruye y se compara por SHA-256
  antes de aceptarlo, y el .ozx completo se vuelve a verificar antes de entregarlo.
- **libjxl** y **precomp** llevan componentes enlazados estáticamente (brotli, highway, libpng, zlib, bzip2, etc.);
  sus licencias están en las subcarpetas `licencias\libjxl` y `licencias\precomp` del portable.

El código de OptiZip en sí no es público. © 2026 Enmanuel Gil · OptiSuite — https://optisuite.app/optizip/
