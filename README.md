# Tennis Match Win Probabilities — v2

Calculadora web con **modelo logístico** + **simulación Monte Carlo por sets**.
Incluye conversión a **odds** (decimal y americana) e **intervalos de confianza**.

## Novedades v2
- Simulación **por sets** (Best of 3 / Best of 5) usando `hold%` y `break%` para determinar la probabilidad de ganar cada juego según quién saca.
- Ajuste de **quién saca primero** (A / B / aleatorio).
- **Intervalo de confianza 95%** para la probabilidad de victoria de A, basado en Monte Carlo.
- **Odds equivalentes** (decimal/americana) a partir de la probabilidad final mostrada (por defecto, la simulación).
- Se mantiene el **modelo logístico** de v1 como referencia (contribuciones por factor).

## Uso
1. Abre `index.html` en tu navegador.
2. Rellena los datos de A y B (puedes usar Elo o solo ranking) + `hold%`/`break%`.
3. Ajusta el número de **simulaciones** (por defecto 5000) y quién **saca primero** si lo deseas.
4. Haz clic en **Calcular probabilidad**. Verás:
   - Probabilidad **logística** y por **Monte Carlo** con IC95%.
   - **Odds** equivalentes para ambos jugadores.
   - **Contribuciones** del modelo logístico.

## Detalles del modelo
- **Logístico (analítico):** combina 5 señales (Elo/Ranking, Superficie, Forma, Head‑to‑Head, Saque+Resto) con pesos ajustables y escala `k`.
  Para Bo5, se potencia la ventaja del favorito elevando las *odds*.
- **Monte Carlo (sets):** simula juegos alternando el servidor. El **tie‑break** se aproxima
  con una probabilidad basada en la media de probabilidad de ganar juego sin servidor (función logística con `c≈5`).

> Sugerencia: si tu `hold%`/`break%` ya consideran la **superficie actual**, la simulación reflejará mejor el contexto.

## Despliegue en GitHub Pages
- Sube los archivos a `main` (raíz), luego **Settings → Pages → Build and deployment** y selecciona `main`.
- La página quedará pública tras el deploy.

**Versión:** v2.0 — 2025-10-06
