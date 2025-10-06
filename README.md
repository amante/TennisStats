# Tennis Match Win Probabilities — v1

Calculadora web para estimar la probabilidad de victoria entre dos jugadores de tenis combinando:
- Elo/Ranking (o pseudo-Elo derivado del ranking)
- Rendimiento por **superficie**
- **Forma reciente** (últimos 10 partidos)
- **Head-to-Head**
- **Saque + Resto** (juegos ganados al saque y al resto, en %)

## Uso local
1. Abre `index.html` con cualquier navegador moderno (Chrome, Edge, Safari, Firefox).
2. Completa los campos de ambos jugadores y presiona **Calcular probabilidad**.
3. Ajusta **pesos** si lo deseas (sección “Ajustes del modelo”).

## GitHub Pages
- Sube *todo el contenido* de este zip a la rama **main** de un repositorio público.
- Ve a **Settings → Pages → Build and deployment** y elige **Deploy from a branch**, Branch: `main` (root).
- La página quedará disponible en unos segundos/minutos.

## Notas del modelo
- La probabilidad se obtiene con una función logística sobre una combinación lineal de factores.
- Para **Best of 5**, se incrementa la ventaja del favorito elevando las *odds* a una potencia `f ≈ 1.35`.
- Puedes **Exportar/Importar JSON** del estado (útil para compartir enfrentamientos).

**Versión:** v1.0 — 2025-10-06
