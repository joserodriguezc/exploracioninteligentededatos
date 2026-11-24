# Sumativa 1 — MCDI503 · Grupo 10

Avance del Proyecto Fase 1: EDA reproducible del dataset `titanic` (seaborn).

**Integrantes:** José Ignacio Rodríguez Cisternas · Sebastian Andrés Rojas Araya · Yerko Gallardo Miranda
**Docente:** Sergio Paraíso Medina · **Entrega en Canvas:** domingo 29-11-2026, 23:59 (cierre interno 18:00)

## Estructura

```
sumativa1/
├── mcdi503_f1_sumativo_grupo10.ipynb        # notebook entregable (secciones I–VIII)
├── informe/
│   └── mcdi503_f1_sumativo_grupo10_borrador.docx   # borrador del PDF (apartados I–IX)
├── data/raw/titanic_seaborn.csv             # copia congelada de la fuente (la genera el notebook)
└── docs/                                    # instrucciones y planificación de la evaluación
```

## Cómo reproducir

Requiere [uv](https://docs.astral.sh/uv/). Desde la raíz del repositorio:

```bash
uv sync                                       # instala las versiones fijadas en uv.lock (Python 3.14)
uv run jupyter nbconvert --to notebook --execute --inplace sumativa1/mcdi503_f1_sumativo_grupo10.ipynb
```

También se puede abrir en Jupyter o VS Code con el kernel de `.venv` y usar *Restart & Run All*.

- La primera ejecución descarga el dataset con `sns.load_dataset("titanic")`, así que necesita conexión a internet.
- El notebook verifica la huella SHA-256 de la fuente (`81787d32…`) y las dimensiones (891 × 15). Si la fuente remota cambia, se detiene con un mensaje explícito.

## Estado por bloque

| Bloque | Responsable | Notebook | Informe | Estado |
|---|---|---|---|---|
| 1. Diseño, carga y diagnóstico | José | I, II, III (+ registro D1–D6 en V.1) | I, II, III | ✅ Listo |
| 2. Transformaciones, exploración y resultados | Sebastián | IV, V, VI | IV, V, VIII | ⏳ |
| 3. Verificación, integración y entrega | Yerko | VII, VIII + ejecución limpia | VI, VII, IX + PDF final | ⏳ |

## Traspaso Bloque 1 → Bloque 2 (checklist de Sebastián)

- [ ] `uv sync` y ejecutar el notebook completo sin errores.
- [ ] Verificar que se reproducen las dimensiones **891 × 15** y la huella **SHA-256** (§III.2).
- [ ] Verificar que se reproduce la tabla de faltantes (Tabla 3.4): `deck` 688, `age` 177, `embarked`/`embark_town` 2.
- [ ] Verificar que se reproduce el resumen de calidad (Tabla 3.9).
- [ ] Continuar el registro de decisiones desde **D7** en §V.1, con motivo y resultado intermedio (cifras antes y después).
- [ ] Trabajar siempre sobre `df` y no modificar `df_raw`.
- [ ] Numerar tablas y figuras por sección (Tabla 4.x, Figura 6.x…) y citarlas en el informe.
- [ ] El informe tiene un máximo de **3 páginas carta** y usa la plantilla institucional (`docs/f1_s01_evaluacion_entregable.docx`).
  - Página 1: portada con el índice.
  - Página 2: los apartados II–III ocupan ~¾.
  - Para IV–IX queda ~1,2 páginas. Escribir de forma sintética.

## Pendientes conocidos

- Fuente **docente** en APA 7 (material del curso en Canvas). Hay un marcador en la bibliografía del informe.
- Fuente académica complementaria (Bloque 3).
