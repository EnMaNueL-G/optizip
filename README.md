<div align="center">

<img src="assets/icon-256.png" width="96" alt="OptiZip"/>

# OptiZip

[![Descargar](https://img.shields.io/badge/⬇_Descargar-OptiZip_Portable-6366f1?style=for-the-badge)](https://github.com/EnMaNueL-G/optizip/releases/latest/download/OptiZip-Portable.zip)
&nbsp;
[![Windows](https://img.shields.io/badge/Windows_10/11-0a7?style=for-the-badge&logo=windows)](#requisitos)

</div>

**Compresor y gestor de archivos comprimidos para Windows.** Crea 7z, ZIP, TAR, ZST y más; abre más de 40 formatos
(RAR incluido); cifra con AES-256; repara con PAR2 y revisa cada archivo con un escudo de seguridad antes de extraer.
**Todo se hace en tu PC, sin internet y sin telemetría.** Gratis.

Parte de la suite **[OptiSuite](https://optisuite.app/optizip/)** · Windows 10/11 (64 bits) · por Enmanuel Gil.

## Descarga

[**OptiZip-Portable.zip**](https://github.com/EnMaNueL-G/optizip/releases/latest/download/OptiZip-Portable.zip) (~144 MB, versión 1.3.0). No hace falta instalar nada.

1. Clic derecho en el ZIP → **«Extraer todo…»** (no lo abras sin extraer).
2. Abre **`OptiZip.exe`** dentro de la carpeta `OptiZip`.
3. Si Windows avisa («Windows protegió su PC»): **«Más información» → «Ejecutar de todas formas»**. El programa no está firmado con un certificado de pago.

## Qué hace

- **Comprimir** en 7z, ZIP, TAR, tar.zst, tar.xz, tar.gz, tar.bz2, WIM, ZST, GZ, XZ y BZ2. Formato «Automático» si no quieres elegir.
- **Niveles** Rápido, Normal, Máximo, **Ultra** y **Extremo**. **Normal** (por defecto) comprime en 7z por bloques que se descomprimen en paralelo, y la extracción usa varios procesos a la vez cuando hay muchos archivos. Ultra en 7z es **multimétodo**: separa el texto por tipo, elige entre LZMA2 y PPMd en cada grupo (comprobándolo con el grupo entero en los casos dudosos). El resultado sigue siendo un **.7z estándar** que abre cualquier 7-Zip.
- **Modo Máximo (.ozx)**: transforma sin pérdida JPG (JPEG XL / packJPG), PDF, PNG, Office, APK y ZIP antes de comprimir, y guarda una sola vez los archivos repetidos. Cada archivo se restaura **idéntico byte a byte** (comprobado con SHA-256 antes de entregarte el .ozx).
- **Análisis previo**: antes de empezar te dice qué se va a reducir bien y qué no.
- **Recompresión sin pérdida** opcional de JPG/PNG/PDF antes de comprimir (no toca tus originales; los píxeles se comprueban idénticos).
- **Contraseña AES-256**, con opción de cifrar también los nombres (7z y .ozx), medidor de fuerza y generador de contraseñas.
- **Dividir en partes** (Gmail 25 MB, CD, WhatsApp 2 GB, FAT32 4 GB, DVD o a medida) y **autoextraíble (.exe)** en 7z.
- **Datos de reparación PAR2**: crear, verificar y reparar archivos dañados.
- **Abrir comprimidos**: ver el contenido, buscar, vista previa, extraer todo o solo lo seleccionado, probar la integridad y **convertir** (por ejemplo, RAR → 7z o ZIP). En 7z/ZIP se puede **añadir, renombrar y borrar** sin descomprimir.
- **Escudo de seguridad** antes de extraer: rutas peligrosas (zip slip), doble extensión (`.pdf.exe`), ejecutables y scripts, carácter RTL oculto, bombas zip y más. Al extraer bloquea las rutas peligrosas, no crea enlaces y mantiene la marca «descargado de internet» para que Windows lo vigile.
- **Herramientas**: optimizar fotos y PDF sin pérdida, huella digital (SHA-256, SHA-1, MD5, CRC32, BLAKE2sp, SHA-512), velocidad de este PC.
- **Integración con Windows (opcional)**: submenú OptiZip en el clic derecho del Explorador y OptiZip en «Abrir con». Solo cambia claves de tu usuario, sin permisos de administrador, y «Desactivar» lo deja como estaba.
- Historial de la sesión, tema claro/oscuro y atajos de teclado.

## Capturas

| Inicio | Comprimir con análisis previo |
|---|---|
| ![Pantalla de inicio de OptiZip](assets/shot-optizip-inicio.webp) | ![Comprimir: lista de archivos y análisis previo](assets/shot-optizip-comprimir.webp) |

| Resultado con Ultra multimétodo | Resultado con el modo Máximo (.ozx) |
|---|---|
| ![Resultado de una compresión con Ultra multimétodo](assets/shot-optizip-ultra.webp) | ![Resultado del modo Máximo .ozx verificado](assets/shot-optizip-maximo.webp) |

| Abrir comprimido con escudo y vista previa | Herramientas |
|---|---|
| ![Explorador de un .7z con aviso de seguridad y vista previa](assets/shot-optizip-explorador.webp) | ![Herramientas: optimizar, PAR2, hash, contraseñas](assets/shot-optizip-herramientas.webp) |

| Integración con Windows |
|---|
| ![Integración con Windows: menú del botón derecho y Abrir con](assets/shot-optizip-windows.webp) |

## Cifras medidas

Medido el 3-4 de octubre de 2026 en un Ryzen 7 5700G (16 hilos) con 32 GB de RAM, frente a **WinRAR 7.20** (`Rar.exe`, mismo motor que
la ventana de WinRAR) y al **7-Zip 26.00** instalados. Cada archivo creado se extrajo con su propio extractor y se comparó
**archivo por archivo con SHA-256** con el original: todo idéntico. Los tamaños son exactos; los tiempos, de una sola compresión
(extracción: mediana de 3), con un ±10 % de ruido. Negativo = OptiZip ocupa menos.

**WinRAR en su máximo** («WinRAR Máxima+») = lo más fuerte que ofrece RAR 7.20: `-m5`, sólido, diccionario que abarca el conjunto
entero y búsqueda exhaustiva `-mcx` (en cada conjunto se toma la variante, con o sin `-mcx`, que ocupa menos).

### Normal (el nivel por defecto) frente a WinRAR en su máximo

| Conjunto | WinRAR Máxima+: tamaño · comprimir · extraer | **OptiZip Normal v1.3**: tamaño · comprimir · extraer |
|---|---|---|
| Texto (3566 archivos, 155,7 MB) | 7 162 254 B · 11,7 s · 2,44 s | **−1,67 %** · **7,1 s** · **0,90 s** |
| Código (15 737 archivos, 125,8 MB) | 16 255 945 B · 32,5 s · 9,31 s | **−9,11 %** · **8,6 s** · **3,02 s** |
| Programas DLL/EXE (289 archivos, 157,9 MB) | 42 574 065 B · 16,3 s · 0,92 s | **−2,35 %** · **8,6 s** · **0,68 s** |
| Imágenes JPG/PNG (590 archivos, 131,2 MB) | 126 478 926 B · 4,9 s · 0,90 s | **−0,29 %** · **2,5 s** · **0,74 s** |
| Mezcla (4437 archivos, 168,4 MB) | 59 963 483 B · 16,2 s · 3,27 s | **−3,78 %** · **12,8 s** · **1,63 s** |
| **Total** | 252 434 673 B · 81,6 s · 16,83 s | **−2,08 %** · **39,7 s** · **6,96 s** |

**Normal ocupa menos y comprime y extrae más rápido que WinRAR en su máximo en los 5 conjuntos.** Es un .7z estándar:
lo abren 7-Zip, NanaZip o WinRAR. El margen más justo está en imágenes (JPG/PNG ya comprimidos) y en texto.

### Ultra y modo Máximo (.ozx) frente a WinRAR en su máximo

**Ultra v1.3** (.7z estándar multimétodo), medido en la misma sesión que WinRAR Máxima+:

| Conjunto | WinRAR Máxima+: tamaño · comprimir · extraer | **OptiZip Ultra v1.3**: tamaño · comprimir · extraer |
|---|---|---|
| Texto | 7 162 254 B · 14,2 s · 2,42 s | 5 931 210 B (**−17,19 %**) · 33,0 s · 2,69 s |
| Código | 16 265 019 B · 37,5 s · 10,04 s | 12 828 345 B (**−21,13 %**) · **30,1 s** · 21,11 s |
| Programas | 42 574 065 B · 19,9 s · 1,03 s | 37 861 248 B (**−11,07 %**) · 50,0 s · 1,47 s |
| Imágenes | 126 478 926 B · 6,8 s · 0,93 s | 126 107 400 B (−0,29 %) · **2,6 s** · **0,72 s** |
| Mezcla | 59 958 970 B · 15,2 s · 3,33 s | 56 847 977 B (**−5,19 %**) · 24,7 s · 3,88 s |
| **Total** | 252 439 234 B | 239 576 180 B (**−5,10 %**) |

**Ultra ocupa un 5,1 % menos en total que WinRAR en su máximo, pero es más lento que WinRAR al comprimir en texto, programas
y mezcla, y al extraer en todos salvo imágenes** (en código, 21,1 s frente a 10,0 s, porque PPMd descomprime en un solo proceso).
Si quieres la velocidad de WinRAR con más reducción que él, usa **Normal**.

**Modo Máximo (.ozx)** frente a WinRAR Máxima+ (tamaños medidos con el .ozx de la v1.2; el de la v1.3 ocupa prácticamente lo
mismo, entre +0,01 % y −1,41 % según el conjunto): **−17,6 % en imágenes, −14,3 % en la mezcla y −15,9 % en total.**
En texto, código y programas no aporta más que Ultra. Solo lo restaura OptiZip.

**Frente a WinRAR sin tocar nada** (Normal: `-m3`, no sólido, 32 MB) la diferencia es mucho mayor: OptiZip Ultra ocupa **menos de
la mitad** en texto (5,97 MB frente a 12,96 MB) y en código (12,78 MB frente a 26,53 MB).

**Honestidad:** gran parte de la ventaja es del formato 7z, no mérito propio de OptiZip: **7-Zip Ultra a secas ya gana a WinRAR en
su máximo por un 4,2 % en total.** WinRAR usa mucha menos RAM al extraer (menos de 200 MB; OptiZip Ultra hasta ~1 GB donde usa PPMd).

### Frente a 7-Zip y al ZIP de Windows (medido con la v1.1)

| Conjunto | 7-Zip Ultra (`-mx9`) | OptiZip Ultra v1.1 | Diferencia |
|---|---:|---:|---:|
| Documentos y texto (3546 archivos) | 6 605 619 B | 5 958 403 B | **−9,80 %** |
| Código fuente (15 810 archivos) | 14 299 396 B | 12 740 382 B | **−10,90 %** |
| Programas DLL/EXE (289 archivos) | 38 019 085 B | 37 831 453 B | −0,49 % |
| Imágenes JPG/PNG (590 archivos) | 125 538 081 B | 125 546 760 B | +0,007 % (empate) |
| Mezcla (7876 archivos) | 58 212 802 B | 57 305 100 B | −1,56 % |

Modo Máximo (.ozx) frente a 7-Zip Ultra: **−35,41 %** en documentos reales (PDF, DOCX, ZIP, APK, PNG; 18 archivos, 87,6 MiB),
**−17,44 %** en imágenes JPG/PNG y **−13,57 %** en la mezcla.

Frente al ZIP de Windows (`tar.exe -a`, medido con el Ultra de la v1.0): −69,2 % en texto, −54,2 % en código, −41,3 % en programas,
−21,3 % en la mezcla y −1,6 % en imágenes.

### El precio, también medido

- **Ultra** necesita hasta ~1 GB de RAM para extraer donde usa PPMd (código: 1005 MiB medidos) y lo indica en el resultado.
- **Extremo** gana poco a Ultra (código −1,13 %, texto −0,12 % frente al Ultra v1.2) y tarda bastante más (código 214 s).
- **Modo Máximo (.ozx) v1.3**: comprimir imágenes tarda 100 s (la v1.2, 342 s) y la mezcla 137 s; restaurar es mucho más
  rápido que en la v1.2 (texto 19×, código 15×, mezcla 5,8×), pero sigue siendo lento en imágenes (22,6 s). Llega a usar
  ~5,8 GB de RAM al comprimir imágenes y ~2,2 GB al restaurarlas.

## Lo que NO hace

- **No crea archivos .rar.** La licencia de RAR no lo permite. Sí los abre, los extrae y los convierte a 7z o ZIP.
- **Las fotos y vídeos ya comprimidos (JPG, MP4, MP3…) apenas bajan** sin pérdida con 7z o ZIP: ningún compresor general los reduce más de un 3-4 %. La recompresión sin pérdida de JPG/PNG/PDF ahorra normalmente un 2-20 %; el modo Máximo, más (ver cifras), pero es mucho más lento.
- **Un .ozx solo lo restaura OptiZip.** 7-Zip o WinRAR lo abren, pero no devuelven los archivos originales. Para enviárselo a otra persona, conviértelo a 7z o ZIP.
- **Menú principal del clic derecho de Windows 11 (desde la v1.2.0):** OptiZip incluye un paquete MSIX firmado con un **certificado propio de OptiSuite** (autofirmado). Al pulsar *Integración con Windows → Menú principal de Windows 11 → Activar*, Windows pide **una vez** permiso de administrador para confiar en ese certificado; el resto se instala solo para tu usuario y *Desactivar* lo deshace. Si no lo activas, el submenú está en «Mostrar más opciones» (o Mayús + F10). WinRAR no pide ese paso porque usa un certificado comercial de pago.
- **No cambia tu programa predeterminado por su cuenta**: Windows no lo permite. Si quieres que el doble clic abra OptiZip, elígelo tú en Configuración → Aplicaciones predeterminadas.
- Si olvidas la contraseña de un archivo cifrado, **no hay forma de recuperarlo**.

## Requisitos

- Windows 10 u 11 de **64 bits**.
- Unos 345 MB de disco para la carpeta extraída.
- Ultra/Extremo y el modo Máximo usan más memoria (ver cifras); OptiZip limita 7-Zip al 70 % de la RAM libre.

## Privacidad

Todo se procesa **en tu PC**. OptiZip **no se conecta a internet**: sin telemetría, sin cuentas, sin anuncios ni
actualizaciones automáticas. Los temporales se borran al terminar y tus archivos originales no se modifican.

## Licencias de terceros

OptiZip es gratuito. Incluye, sin modificar, 7-Zip 26.00 (LGPL-2.1 + restricción unRAR), par2cmdline 1.4.0 (GPL-2.0),
oxipng 10.2.1 (MIT), libjpeg-turbo 3.2.0 (IJG/BSD-3/zlib), qpdf 12.4.2 (Apache-2.0), libjxl 0.12.0 (BSD-3),
precomp 0.4.7 (Apache-2.0, con packJPG LGPL-3.0) y Electron (MIT). Versiones, licencias y **enlaces al código fuente**:
[LICENCIAS-TERCEROS.md](LICENCIAS-TERCEROS.md). Los textos completos van en la carpeta `licencias` del ZIP.

## Apoya el proyecto

Sin anuncios ni telemetría. Donación voluntaria por Binance:

- **Binance Pay ID:** `1165745950`
- **USDT (BSC · BEP-20):** `0xb6f6731a4ea87f8e1fd6f44f48b5bc4204571f08`

— Web: **https://optisuite.app/optizip/** · Soporte: **support@optisuite.app**

El código fuente de OptiZip no es público; este repositorio contiene las descargas (Releases) y la documentación.

© 2026 Enmanuel Gil · OptiSuite
