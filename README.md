<p align="center">
  <img src="https://5115875.fs1.hubspotusercontent-na1.net/hubfs/5115875/servnet-home/images/servnet-logo.png" alt="Servnet México" width="200"/>
</p>

<h1 align="center">Player A</h1>

<p align="center">
  <strong>Skill de Claude Code · Toolkit de IA · Servnet México</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Claude_Code-skill-blueviolet?style=flat-square" />
  <img src="https://img.shields.io/badge/Framework-ROL·CONTEXTO·TAREA·FORMATO-orange?style=flat-square" />
  <img src="https://img.shields.io/badge/Idioma-Español-green?style=flat-square" />
  <img src="https://img.shields.io/badge/Versión-1.0-lightgrey?style=flat-square" />
</p>

---

## ¿Qué es Player A?

Player A es una skill para Claude Code que lleva el Toolkit de IA de Servnet
a la práctica dentro del flujo de trabajo diario.

Está diseñada para dos cosas concretas:

1. **Mejorar la calidad de los prompts** — evalúa en tiempo real si tu
   instrucción tiene los 4 ingredientes necesarios para llegar al resultado
   en el primer intento.

2. **Orientar el uso del modelo correcto** — informa qué modelo de Claude
   se adapta mejor a cada tipo de tarea, con base en las áreas y puestos
   reales de Servnet. No prescribe — educa sobre buenas prácticas.

---

## El framework: ROL · CONTEXTO · TAREA · FORMATO

Basado en el Toolkit de IA de Servnet México, Player A evalúa 4 ingredientes
en cada prompt:

| Ingrediente | Criterio | Puntos |
|---|---|---|
| **ROL** | ¿Le indicaste a Claude qué perfil adoptar? | 0–2 |
| **CONTEXTO** | ¿Explicaste la situación sin asumir conocimiento previo? | 0–3 |
| **TAREA** | ¿Usaste un verbo concreto: genera, analiza, redacta, audita? | 0–3 |
| **FORMATO** | ¿Especificaste cómo quieres la respuesta? | 0–2 |

Un prompt con los 4 ingredientes llega al resultado en el primer intento.
Uno sin ellos genera 2–4 iteraciones adicionales.

---

## Funcionalidades

### 🔍 Prueba de escritorio del prompt
Cuando detecta un prompt incompleto, Player A lo evalúa automáticamente:
muestra qué se asumió, el score del prompt, la versión estructurada sugerida
y la referencia de modelo más adecuado para esa tarea.

```
Prueba de escritorio del prompt

📝 Prompt recibido:
   "Necesito ver el gráfico de cambios de grupo de clientes"

📊 Score: 2/10  ████░░░░░░░░░░░░░░░░

   ❌ Rol      — no definido
   ❌ Contexto — módulo, sistema y tabla sin especificar
   ❌ Tarea    — "ver" no es un verbo concreto
   ❌ Formato  — sin especificar

✅ Versión estructurada:
   "Actúa como desarrollador PHP/MySQL. En el módulo
    grupo_clientes de CAPA 8, genera un componente PHP
    con Chart.js que muestre cambios por mes en gráfica
    de línea."

🤖 Referencia de modelo: Sonnet 4.6
   Para generación de código con contexto técnico específico,
   Sonnet 4.6 ofrece el mejor balance entre calidad y costo.

   Haiku 4.5 → más rápido y económico, menor precisión en código
   Sonnet 4.6 → recomendado para esta tarea ✓
   Opus 4.7  → mayor capacidad, el costo no se justifica aquí
```

### 📐 Contexto acumulado de sesión
Una vez que defines un ingrediente, Player A lo retiene durante toda la
sesión. No tienes que repetir el rol o el contexto en cada mensaje — solo
especifica lo que cambia o falta.

### 📋 Plan de pruebas antes de escribir código
Antes de generar o modificar una función, Player A propone un plan de
pruebas y solicita aprobación. Esto elimina el ciclo write → fail → fix.

### ✅ Reporte de resultados post-prueba
Después de ejecutar tests, presenta solo lo relevante: qué falló, dónde
y por qué.

### 📈 Seguimiento de mejora entre sesiones
Player A guarda un historial en `.player_a_memory.json` que registra:
- Score de prompts por sesión
- Ingredientes que más se omiten
- Fórmulas del toolkit aplicadas
- Historial de referencias de modelo por tipo de tarea
- Racha de mejora consecutiva

Al iniciar cada sesión, muestra el resumen y los patrones a mejorar.

### 🤖 Guía de modelos por área y puesto
Player A incluye una guía de referencia basada en las áreas y puestos
reales de Servnet (tblAreas y tblPuesto de CAPA 8). Cubre desde
Planeación Estratégica y Contabilidad hasta NOC, Planta Externa y TI.

El objetivo no es prescribir — es informar sobre buenas prácticas para
que cada colaborador entienda qué modelo se adapta mejor a su tarea
y por qué.

### 🎯 Reconocimiento de las 5 fórmulas del Toolkit
Cuando aplicas correctamente una de las 5 fórmulas del Toolkit de Servnet,
Player A lo confirma en una línea.

---

## Referencia rápida de modelos

| Modelo | Cuándo usarlo |
|---|---|
| **Haiku 4.5** | Tareas repetitivas, clasificación, consultas rápidas, alto volumen |
| **Sonnet 4.6** | Desarrollo, análisis, redacción, reportes — punto de partida para la mayoría de tareas |
| **Opus 4.7** | Razonamiento complejo, decisiones críticas, arquitectura, auditorías |

> Sonnet 4.6 es el punto de partida. Sube a Opus cuando la complejidad
> lo justifique. Baja a Haiku cuando el volumen o la simplicidad lo permitan.

---

## Instalación

### Desde GitHub (recomendado)

```bash
claude skill add --url https://raw.githubusercontent.com/jonatanhidalgo-SERVNET/Player-A-skill/main/skill/SKILL.md
```

### Local

```bash
git clone https://github.com/jonatanhidalgo-SERVNET/Player-A-skill.git
cd Player-A-skill
claude skill add skill/
```

---

## Comandos

| Comando | Acción |
|---|---|
| `/player` | Lista de comandos disponibles |
| `/player plan` | Plan de pruebas de la función actual |
| `/player test` | Ejecuta pruebas y presenta reporte |
| `/player review` | Prueba de escritorio del último prompt |
| `/player score` | Score acumulado de la sesión |
| `/player modelos` | Guía de referencia de modelos por área y tarea |
| `/player reset` | Limpia el contexto acumulado de sesión |

---

## Memoria persistente

Player A crea `.player_a_memory.json` en la raíz del proyecto al iniciar
la primera sesión. Este archivo es personal — no debe compartirse.

Agregar a `.gitignore`:

```
.player_a_memory.json
```

---

## ¿Por qué Player A reduce retrabajo?

La reducción no es por respuesta — es por conversación completa.

Un prompt sin estructura genera 3–5 turnos de aclaración.
Un prompt con los 4 ingredientes llega al resultado en 1–2 turnos.

Usar el modelo adecuado para cada tarea reduce costos sin sacrificar
calidad. Player A no reemplaza el criterio profesional — lo informa
con contexto real de Servnet.

---

## Estructura del repositorio

```
Player-A-skill/
  skill/
    SKILL.md                   ← Definición de la skill
    README.md                  ← Este archivo
  .gitignore                   ← Incluye .player_a_memory.json
```

---

<p align="center">
  Desarrollado por el equipo de TI · <strong>Servnet México</strong> · 2026<br/>
  <a href="https://servnet.mx">servnet.mx</a>
</p>
