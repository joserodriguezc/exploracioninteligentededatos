# Sumativa 1 — MCDI503 · Grupo 10

Avance del Proyecto Fase 1: EDA reproducible del dataset `titanic` (seaborn).

**Integrantes:** José Ignacio Rodríguez Cisternas · Sebastian Andrés Rojas Araya · Yerko Gallardo Miranda
**Docente:** Sergio Paraíso Medina · **Entrega en Canvas:** domingo 29-11-2026, 23:59 (cierre interno 18:00)

## Estructura

```
sumativa1/
├── notebooks/
│   └── mcdi503_f1_sumativo_grupo10.ipynb    # notebook entregable (secciones I–VIII)
├── informe/
│   └── mcdi503_f1_sumativo_grupo10_borrador.docx   # borrador del PDF (apartados I–IX)
├── data/raw/titanic_seaborn.csv             # copia congelada de la fuente (la genera el notebook)
└── docs/                                    # instrucciones y planificación de la evaluación
```

## Cómo reproducir

Requiere [uv](https://docs.astral.sh/uv/). Desde la raíz del repositorio:

```bash
uv sync                                       # instala las versiones fijadas en uv.lock (Python 3.14)
uv run jupyter nbconvert --to notebook --execute --inplace sumativa1/notebooks/mcdi503_f1_sumativo_grupo10.ipynb
```

También se puede abrir en Jupyter o VS Code con el kernel de `.venv` y usar *Restart & Run All*.

- La ejecución lee `data/raw/titanic_seaborn.csv`, la copia congelada incluida en el repositorio; no requiere internet una vez instalado el entorno.
- El notebook verifica la huella SHA-256 de la fuente (`81787d32…`) y las dimensiones (891 × 15). Si la copia local cambia, se detiene antes de cargar los datos.

## Estado por bloque

| Bloque | Responsable | Notebook | Informe | Estado |
|---|---|---|---|---|
| 1. Diseño, carga y diagnóstico | José | I, II, III (+ registro D1–D6 en V.1) | I, II, III | ✅ Listo |
| 2. Transformaciones, exploración y resultados | Sebastián | IV, V, VI completas | IV, V, VIII integrados en el DOCX | Listo para traspaso |
| 3. Verificación, integración y entrega | Yerko | VII, VIII + ejecución limpia | VI, VII, IX + PDF final | ⏳ |

## Traspaso Bloque 1 → Bloque 2 (checklist de Sebastián)

- [x] `uv sync` y ejecutar el notebook completo sin errores.
- [x] Verificar que se reproducen las dimensiones **891 × 15** y la huella **SHA-256** (§III.2).
- [x] Verificar que se reproduce la tabla de faltantes (Tabla 3.4): `deck` 688, `age` 177, `embarked`/`embark_town` 2.
- [x] Verificar que se reproduce el resumen de calidad (Tabla 3.9).
- [x] Continuar el registro de decisiones desde **D7** en §V.1, con motivo y resultado intermedio (cifras antes y después).
- [x] Trabajar siempre sobre `df` y no modificar `df_raw`.
- [x] Numerar tablas y figuras por sección (Tabla 4.x, Figura 6.x…) y citarlas en el informe.
- [ ] El informe tiene un máximo de **3 páginas carta** y usa la plantilla institucional (`docs/f1_s01_evaluacion_entregable.docx`).
  - Página 1: portada con el índice.
  - Página 2: los apartados II–III ocupan ~¾.
  - Para IV–IX queda ~1,2 páginas. Escribir de forma sintética.

## Pendientes conocidos

- Fuente **docente** en APA 7 (material del curso en Canvas). Hay un marcador en la bibliografía del informe.
- Fuente académica complementaria (Bloque 3).

## Traspaso Bloque 2 → Bloque 3

- Notebook con secciones IV–VI, tablas numeradas, tres figuras nuevas, respuestas P1–P3 y decisiones D7–D11.
- `informe/aporte_sebastian.txt`: aporte breve para IV, V y VIII, referencia oficial en APA 7 y notas de integración. Los textos y la referencia técnica ya están integrados en el DOCX institucional; el borrador se revisó visualmente y tiene tres páginas.
- Carga local con SHA-256, sin sobrescribir la fuente. Se mantiene `df_raw`; `df` conserva 891 filas, retira tres columnas redundantes y agrega `fare_log1p` (13 columnas finales).
- P2 edad: 714 válidos y 177 excluidos solo de ese cálculo. P3: 891 pasajeros, 342 sobrevivientes, sin exclusiones por edad.
- Yerko debe completar VII–VIII del notebook, integrar el informe y realizar la verificación final desde un kernel limpio.

Validación del bloque 2: ejecución completa desde un kernel nuevo sin errores (22 celdas de código); se verificaron huella, dimensiones, faltantes, denominadores y conservación de los valores originales.

Integración del informe: apartados IV, V y VIII y referencia oficial incorporados al DOCX. Actualizadas las descripciones de carga local y D5/D7. Pendientes de Yerko: VI, VII, cierre bibliográfico y comprobación de extensión después de sus aportes.
