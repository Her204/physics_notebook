# Lluvia de ideas — mejoras al notebook 7_astrofisica.ipynb

Fecha de análisis: 2026-04-03  
Herramienta: Claude Code + MCP alphaXiv

---

## Diagnóstico del estado actual

El notebook tiene buena estructura pedagógica (FLRW → Friedmann → observables → tensiones → inflación → ejercicio).  
Problemas concretos detectados:

1. **Las tensiones cosmológicas están ausentes como tema central** — se mencionan de pasada pero no se cuantifican ni se grafica el espacio de parámetros donde viven.
2. **DESI DR2 (marzo 2025) merece su propia celda de análisis** — el notebook lo menciona en texto pero no hay visualización del plano w0–wa ni de la evidencia de energía oscura dinámica.
3. **ACT DR6 (marzo 2025) no aparece** — es el experimento CMB post-Planck más importante publicado recientemente.
4. **Las masas de neutrinos no tienen números** — hay texto conceptual pero falta la restricción cuantitativa (Σmν < 0.12 eV Planck 2018; posible detección ~2σ con DESI DR2).
5. **JWST y las primeras galaxias están completamente ausentes** — hallazgos que desafían modelos de formación de estructura.
6. **Inflación: solo descripción conceptual** — falta la comparación ns–r con predicciones de modelos específicos (Starobinsky, Higgs) contra datos ACT DR6 + Planck.
7. **Ondas gravitacionales como sonda cosmológica** — ausentes (GWTC-4.0, NANOGrav).
8. **Graficas actuales**: dominantemente seaborn básico con paletas genéricas; falta contexto observacional real (no solo esquemas pedagógicos).

---

## Puntos clave a agregar

### A. Tensión de Hubble — sección dedicada con gráfica

**Por qué es urgente**: es la anomalía estadísticamente más significativa de la cosmología moderna (~5σ en 2024–2025), y el notebook no la toca como tema.

**Qué agregar**:
- Gráfica de "violín" o "barra de error" comparando mediciones independientes de H0:
  - CMB: Planck 2018 → H0 = 67.4 ± 0.5 km/s/Mpc
  - CMB: ACT DR6 (2503.14452) → H0 = 68.3 ± 1.1 km/s/Mpc
  - BAO sound-horizon free: DESI 2024 (2411.16677) → ~69–70
  - SH0ES (Cepheidas + SNe Ia) → H0 = 73.0 ± 1.0 km/s/Mpc
  - Lentes gravitacionales (H0LiCOW/TDCOSMO) → ~73
  - Sirenas oscuras GWTC-4 (2509.04348) → ~68 con incertidumbre ~8%
- Texto: explicar por qué esto podría ser física nueva (EDE, interacción sector oscuro, variación de constantes) vs. sistemáticas

**Papers de referencia**:
- `2601.00650` — *Dissecting the Hubble tension: sound horizon-free H0 measurements* (2026-01-02)
- `2411.16677` — *A Sound Horizon-Free Measurement of H0 in DESI 2024* (2024-11-25)
- `2504.01669` — *CosmoVerse White Paper* (2025-04-02, revisión exhaustiva de todas las tensiones)
- `2601.01525` — *Cracks in the Standard Cosmological Model* (2026-01-04)

---

### B. Tensión de S8 / σ8 — agregar a sección de materia oscura

**Por qué**: la tensión S8 ≡ σ8 √(Ωm/0.3) entre CMB (alto) y lensing débil (bajo) es la segunda tensión más importante y es ortogonal a la de H0.

**Qué agregar**:
- Gráfica contorno en plano (Ωm, σ8) mostrando: Planck 2018 CMB vs. KiDS-Legacy (2512.11041) vs. DES Y6
- Texto: qué clases de física la explicarían (interacción DM–DE, neutri nos masivos, estructura barionica mal modelada)

**Papers**:
- `2512.11041` — *KiDS-Legacy: constraining dark energy, neutrino mass, and curvature* (2025-12-11)
- `2504.01669` — CosmoVerse White Paper (incluye revisión de la tensión S8)

---

### C. DESI DR2 — plano w0–wa con visualización propia

**Por qué**: DESI DR2 (marzo 2025) reportó la evidencia más fuerte hasta ahora de energía oscura dinámica, con w0 > -1 y wa < 0, cruzando w = -1 (quintom-B). La herramienta pedagógica natural es el plano w0–wa.

**Qué agregar**:
- Gráfica de contornos en plano (w0, wa) con:
  - DESI DR2 + CMB (contorno relleno)
  - DESI DR2 + CMB + DES SN5YR (contorno más estrecho)
  - Punto ΛCDM marcado como referencia
  - Línea wa = 0 (quintessence clásico) y línea w0 = -1
  - Indicar el nivel de significancia (~3.9σ sobre ΛCDM)
- Texto: explicar qué significa el cruce del fantasma (w < -1) y por qué es teóricamente problemático sin campo exótico (violación NEC)

**Papers**:
- `2503.14743` — *Extended Dark Energy analysis using DESI DR2* (2025-03-18) — paper de soporte clave
- `2503.14742` — *Validation of DESI DR2 BAO from Galaxies and Quasars* (2025-03-18)
- `2504.07791` — *Quantum Gravity Meets DESI: Trans-Planckian Censorship* (2025-04-10) — perspectiva teórica
- `2505.24732` — *Quintom theory of dark energy after DESI DR2* (2025-05-30)
- `2504.15222` — *Did DESI DR2 truly reveal dynamical dark energy?* (2025-04-21) — lado escéptico

---

### D. ACT DR6 — nuevo ancla CMB post-Planck

**Por qué**: ACT DR6 (marzo 2025) es el resultado CMB más significativo tras Planck. Confirma parámetros ΛCDM de forma independiente y actualiza las restricciones de inflación.

**Qué agregar**:
- Comparación tabular/visual: Planck 2018 vs. ACT DR6 en parámetros clave (H0, Ωm, σ8, ns)
- Texto: qué confirma ACT y dónde hay diferencias (ACT DR6 da H0 ligeramente mayor que Planck)

**Papers**:
- `2503.14452` — *ACT DR6 Power Spectra, Likelihoods and ΛCDM Parameters* (2025-03-18)
- `2503.14454` — *ACT DR6 Constraints on Extended Cosmological Models* (2025-03-18)

---

### E. Inflación: diagrama ns–r con modelos específicos

**Por qué**: el notebook trata inflación solo conceptualmente. El plano ns–r es **la** visualización canónica para confrontar modelos inflacionarios con datos.

**Qué agregar**:
- Gráfica en plano (ns, r) mostrando:
  - Región permitida observacionalmente: Planck 2018 + ACT DR6 (ns ≈ 0.965 ± 0.004, r < 0.036)
  - Predicciones de modelos específicos:
    - **Starobinsky R²**: ns = 1 − 2/N, r = 12/N² → ns≈0.967, r≈0.003 para N=60 — muy favorecido
    - **Higgs inflation** (Bezrukov & Shaposhnikov): mismas predicciones que Starobinsky en el atractor
    - **Power-law φⁿ**: n=2 → r≈0.13 (excluido), n=1/3 → r≈0.02 (marginal)
    - **Natural inflation**: cuerda de predicciones dependiendo de f/Mpl
  - BICEP/Keck 2021 como límite en r
- Texto: por qué los modelos tipo Starobinsky son los más favorecidos actualmente

**Papers**:
- `2505.13646` — *On the Present Status of Inflationary Cosmology* (2025-05-19) — revisión actualizada
- `2503.14454` — ACT DR6 Constraints on Extended Models (incluye plano ns–r con ACT)
- `2504.02655` — *The early universe is ACT-ing warm* (2025-04-03)

---

### F. Masas de neutrinos — restricciones cuantitativas

**Por qué**: el notebook habla de neutrinos masivos pero sin números. Las restricciones cosmológicas son las más fuertes que existen.

**Qué agregar**:
- Tabla comparativa de límites:
  - Planck 2018 solo: Σmν < 0.24 eV (95% CL)
  - Planck + BAO pre-DESI: Σmν < 0.12 eV
  - DESI DR2 + Planck + ACT (2504.15340): posible detección ~2σ, Σmν ~ 0.05–0.10 eV
  - Mínimo de oscilaciones: Σmν > 0.06 eV (jerarquía normal) o > 0.10 eV (jerarquía invertida)
- Texto: la tensión entre la restricción cosmológica y el límite inferior de física de oscilaciones → señal de que algo en el modelo cosmológico podría estar mal (energía oscura dinámica + neutrinos masivos se degeneran)

**Papers**:
- `2503.14470` — *What's the matter with Σmν?* (2025-03-18)
- `2504.15340` — *Cosmology in Extended Parameter Space with DESI DR2: 2σ+ detection of non-zero neutrino masses* (2025-04-21)
- `2412.05451` — *The Status of Neutrino Cosmology* (2024-12-06)

---

### G. JWST y primeras galaxias — nueva sección o subsección

**Por qué**: JWST encontró galaxias masivas y brillantes a z > 10 que son difíciles de explicar con ΛCDM estándar + formación estelar convencional. Es el resultado observacional más llamativo de 2022–2025.

**Qué agregar**:
- Gráfica de función de luminosidad UV a z ≥ 9: predicciones ΛCDM vs. datos JWST (JADES, CEERS, PRIMER)
- Texto: las "little red dots" (LRDs) como AGN masivos a z ~ 5–11 que complicaron el panorama de reionización
- Mención de la crisis de reionización: JWST sugiere que los AGN de baja luminosidad podrían haber contribuido más de lo pensado a la reionización

**Papers**:
- `2304.14469` — *Galaxy UV luminosity function at z≈11* (2023)
- `2406.05306` — *New galaxy candidates z > 11 in JADES field* (2024-06-08)
- `2404.07250` — *Reionization after JWST: a photon budget crisis?* (2024-09-05)
- `2404.03576` — *Little Red Dots in JWST extragalactic fields* (2024-04-19)

---

### H. Ondas gravitacionales como sonda cosmológica

**Por qué**: la era multimensajero abre un canal completamente independiente para medir H0 y probar GR a distancias cosmológicas.

**Qué agregar**:
- Subsección breve dentro de técnicas experimentales:
  - GWTC-4.0 (2509.04348): 142 fuentes GW → H0 = 68+8−6 km/s/Mpc — consistente con CMB, no resuelve la tensión aún pero señala el camino
  - NANOGrav 15-year: fondo estocástico de OG, posiblemente de origen cosmológico (transiciones de fase, cuerdas cósmicas)
  - Einstein Telescope (futuro): perspectiva a ~2035

**Papers**:
- `2509.04348` — *GWTC-4.0: Constraints on Cosmic Expansion Rate* (2025-09-04)
- `2503.12263` — *The Science of the Einstein Telescope* (2025-03-15)

---

## Mejoras a gráficas existentes

| Gráfica actual | Problema | Mejora propuesta |
|---|---|---|
| Densidades vs. a(t) (Cell 6) | Solo esquemática, sin unidades observacionales | Agregar puntos de datos BAO reales (z_eff vs. Dv/rs) de DESI DR2 superpuestos al modelo |
| Animación expansión (Cell 8) | Útil pero muy simplificada | Agregar curva H(z) observada vs. ΛCDM en panel lateral |
| Tabla de probes (Cell 10) | Solo texto, sin comparación cuantitativa | Agregar columna "Tensión con ΛCDM" con nivel de significancia |
| Diagrama de Hubble SN Ia (Cell 12) | Solo ΛCDM vs. w0wa esquemático | Añadir residuos (Hubble residuals) reales estilo Pantheon+/DES SN5YR |
| BAO animación (Cell 14) | Señal artificial | Añadir comparación con datos DESI DR2 reales (7 puntos clave en z_eff) |
| Fracciones de energía y q(z) (Cell 19) | Correcto pero sin contexto observacional | Añadir banda sombreada donde DESI DR2 da evidencia de w ≠ -1 |
| Tabla de teorías (Cell 21) | Muy cualitativa | Agregar columna "Predicción cuantitativa falsificable" con valores de ns, r, w0, wa |

---

## Orden de prioridad de implementación

1. **Sección de tensiones (H0 + S8)** — mayor impacto pedagógico, más urgente
2. **Diagrama ns–r con modelos inflacionarios** — completa el arco conceptual de inflación
3. **Plano w0–wa con DESI DR2** — actualización crítica del resultado más reciente
4. **Masas de neutrinos con números** — fácil de agregar, gran valor conceptual
5. **JWST primeras galaxias** — subsección nueva, rica en sorpresas observacionales
6. **ACT DR6 comparación con Planck** — tabla/gráfica de actualización de parámetros
7. **Ondas gravitacionales** — subsección breve, abre ventana al futuro

---

## Notas adicionales

- El CosmoVerse White Paper (`2504.01669`, publicado 2025-04-02 — literalmente hace dos días) es una referencia exhaustiva de ~400 páginas sobre todas las tensiones cosmológicas actuales. Sería el paper de referencia primario para cualquier discusión de tensiones.
- ACT DR6 (`2503.14452`) publicado en marzo 2025 es la actualización CMB más importante desde Planck 2018.
- El argumento de Linde/Starobinsky sobre inflación: el modelo R² (Starobinsky 1980) es el más favorecido observacionalmente de todos los modelos inflacionarios. Vale la pena nombrarlo explícitamente en la sección de inflación.
