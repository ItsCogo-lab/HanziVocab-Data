# HanziVocab-Data

Datos del diccionario completo de [HanziVocab](https://github.com/ItsCogo-lab/HanziVocab),
que la app lee en tiempo de ejecución a través de jsDelivr. **No se edita a
mano**: se genera con `npm run data:build` en el repositorio de la app y se
publica con `npm run data:release` (o el workflow «Publish data»).

Versión actual: **1.0.0** (generada el 2026-09-28T20:25:51Z).

## Contenido

- `v1/manifest.json`: formato, versión actual, fecha y versiones de las fuentes.
- `v1/<versión>/dictionary/0.json` a `31.json`: todo CC-CEDICT salvo
  HSK 1-4 (que va dentro de la app). Cada entrada está en el archivo del punto
  de código de su primer carácter módulo 32.

La app pide `https://cdn.jsdelivr.net/gh/ItsCogo-lab/HanziVocab-Data@main/v1/manifest.json`
y después los trozos de la carpeta de esa versión. Una carpeta de versión no se
modifica nunca: una versión nueva es una carpeta nueva y un manifiesto nuevo.
Se conservan las 2 versiones anteriores. Un cambio de formato incompatible
va en `v2/`, sin romper las versiones de la app que leen `v1/`.

## Fuentes, licencias y atribución

- **cc-cedict**: cedict-json@1.3.20251213 (CC-CEDICT 2025-12-13)
- **unihan**: Unicode 18.0.0
- **makemeahanzi**: skishore/makemeahanzi@bddc96d41bef78427ed0e034e9f7e31d71fd1b92
- **hanzi-writer-data**: hanzi-writer-data@2.0.1

- Significados, pinyin y formas tradicionales: [CC-CEDICT](https://cc-cedict.org/wiki/),
  [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Estos datos,
  al derivar de CC-CEDICT, se distribuyen con la misma licencia.
- Radical, número de trazos y variantes: [Unicode Unihan](https://www.unicode.org/charts/unihan.html),
  [Unicode License v3](https://www.unicode.org/license.txt). Copyright © Unicode, Inc.
- Descomposición y etimología: [Make Me a Hanzi](https://github.com/skishore/makemeahanzi),
  LGPL 3.0 o posterior.
- Número de trazos: [hanzi-writer-data](https://github.com/chanind/hanzi-writer-data),
  Arphic Public License.
