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

Player A es una skill para Claude Code que lleva el
[Toolkit de IA de Servnet] a la práctica dentro del
flujo de desarrollo.

La mayor fuente de retrabajo en proyectos no es el código — son las
instrucciones mal estructuradas. Un prompt vago genera supuestos. Los
supuestos generan iteraciones. Las iteraciones consumen tiempo y recursos.

**Player A interrumpe ese ciclo.**

Evalúa la calidad de cada prompt en tiempo real, identifica exactamente
qué ingrediente falta, sugiere la versión estructurada y registra los
patrones del usuario entre sesiones para medir la mejora con el tiempo.

---

## El framework: ROL · CONTEXTO · TAREA · FORMATO

Basado en el Toolkit de IA de Servnet México:

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

### Prueba de escritorio del prompt
Cuando detecta un prompt incompleto, Player A lo evalúa automáticamente:
muestra qué se asumió, el score del prompt y la versión estructurada lista
para usar.

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
```

### Contexto acumulado de sesión
Una vez que defines un ingrediente, Player A lo retiene durante toda la
sesión. No tienes que repetir el rol o el contexto en cada mensaje — solo
especifica lo que cambia.

### Plan de pruebas antes de escribir código
Antes de generar o modificar una función, Player A propone un plan de
pruebas y solicita aprobación. Esto elimina el ciclo write → fail → fix.

### Reporte de resultados post-prueba
Después de ejecutar tests, presenta solo lo relevante: qué falló, dónde
y por qué.

### Seguimiento de mejora entre sesiones
Player A guarda un historial en `.player_a_memory.json` que registra:
- Score de prompts por sesión
- Ingredientes que más se omiten
- Racha de mejora consecutiva

Al iniciar cada sesión, muestra el resumen y los patrones a mejorar.

### Reconocimiento de las 5 fórmulas del Toolkit
Cuando aplicas correctamente una de las 5 fórmulas del Toolkit de Servnet
(El consultor, El revisor, El generador, El transformador, El coach),
Player A lo confirma.

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
claude skill add .
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
| `/player reset` | Limpia el contexto acumulado de sesión |

---

## Memoria persistente

Player A crea `.player_a_memory.json` en la raíz del proyecto al iniciar
la primera sesión. Este archivo es personal — no debe compartirse entre
el equipo.

Agregar a `.gitignore`:

```
.player_a_memory.json
```

---

## ¿Por qué Player A reduce retrabajo?

La reducción no es por respuesta — es por conversación completa.

Un prompt sin estructura genera 3–5 turnos de aclaración e iteración.
Un prompt con los 4 ingredientes llega al resultado en 1–2 turnos.
Player A no reemplaza el criterio profesional — lo amplifica desde el
primer mensaje.

---

## Estructura del repositorio

```
Player-A-skill/
  SKILL.md                   ← Definición de la skill
  README.md                  ← Este archivo
  .gitignore                 ← Incluye .player_a_memory.json
```

---

<p align="center">
  Desarrollado por el equipo de TI · <strong>Servnet México</strong> · 2026<br/>
  <a href="https://servnet.mx">servnet.mx</a>
</p>
