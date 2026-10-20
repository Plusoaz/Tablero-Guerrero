# Tablero de coordinación empresarial · Guerrero

Tablero de Guerrero Impulsa para dar seguimiento al trabajo con empresarios y cámaras, a la agenda de CONDESA Guerrero y a la incidencia pública de Guerrero Industrial.

**Estado: versión de demostración (mockup funcional), octubre de 2026.** Guerrero Impulsa, CONDESA Guerrero, FICOSEGro y BANDEGRO son propuestas.

## Qué contiene

| Archivo | Contenido |
|---|---|
| `index.html` | El tablero completo (una sola página, sin dependencias). Lleva una copia interna de los datos para funcionar aunque no encuentre los CSV. |
| `data/actividades.csv` | Bitácora de actividades. Hoy trae 36 registros **de ejemplo** (`ejemplo=si`). |
| `data/organismos.csv` | Directorio de cámaras y organismos v1 (corte 2-oct-2026), solo campos públicos: sin dirigentes ni contactos. |
| `data/municipios_guerrero.geojson` | 85 municipios en WGS84 con región, población 2020 y bandera de población estimada. Sirve para QGIS o R. |

## Versiones

Hay dos versiones del mismo tablero; solo cambia una línea al inicio del código (`const CONFIG = { foto: ... }`):

- **Pública (`index.html` de este repositorio):** `foto: ''`, sin foto. Es la que se sube a GitHub.
- **Equipo:** archivo aparte con la foto en la esquina superior derecha. No se sube a este repositorio público; se comparte directamente.

## Escala de color

En todos los mapas, más población o más datos = color más intenso u oscuro; menos = color más claro. Se mantiene igual en modo claro y oscuro.

## Publicar en GitHub Pages

1. Crea un repositorio (por ejemplo `Tablero-Guerrero`) y sube todo el contenido de esta carpeta.
2. En el repositorio: **Settings › Pages › Build and deployment**, elige *Deploy from a branch*, rama `main`, carpeta `/ (root)`.
3. En uno o dos minutos queda en `https://<usuario>.github.io/Tablero-Guerrero/`.

## Actualizar datos

- Edita `data/actividades.csv` (directo en GitHub o en Excel guardando como CSV UTF-8). El tablero lee ese archivo al abrir.
- La pestaña «Registrar actividad» guarda capturas en el navegador de quien las hace; el botón «Descargar CSV» las exporta para pegarlas en `data/actividades.csv`.
- Para usar solo datos reales, borra las filas con `ejemplo=si` o apaga el interruptor «Incluir datos de ejemplo».

Columnas de `actividades.csv`: `id, fecha (AAAA-MM-DD), tipo, municipio, con_quien, tipo_actor, mesa, resultado, siguiente_paso, responsable, ejemplo`. El municipio debe escribirse como aparece en el tablero; la región se asigna sola.

## Privacidad (importante)

En GitHub Pages gratuito el repositorio es **público**. No subas nombres de personas, teléfonos, correos ni detalles de reuniones que no deban ser públicos. La versión operativa con datos reales debe vivir en un repositorio privado o en otra plataforma con acceso controlado, con aviso de privacidad conforme a la ley de datos personales.

## Fuentes y notas

- Población: INEGI, Censo de Población y Vivienda 2020, ITER Guerrero.
- Límites municipales: INE, Base Geográfica Digital, corte diciembre 2025 (85 municipios).
- Las Vigas, Ñuu Savi, San Nicolás y Santa Cruz del Rincón se crearon después del censo: su población es una estimación propia sumando las localidades ITER 2020 dentro de su polígono (por verificar).
- Asignación de municipios a regiones: preliminar, por verificar con el catálogo oficial. La región Sierra se define por 818 localidades de 14 municipios; se agregará cuando se cuente con ese catálogo.
