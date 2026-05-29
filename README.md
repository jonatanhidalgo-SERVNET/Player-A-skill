<p align="center">
  <img src="https://5115875.fs1.hubspotusercontent-na1.net/hubfs/5115875/servnet-home/images/servnet-logo.png" alt="Servnet México" width="180"/>
</p>

<h1 align="center">Player A</h1>

<p align="center">
  <strong>Skill de desarrollo para Claude Code · Powered by Servnet México</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Claude_Code-skill-blueviolet?style=flat-square" />
  <img src="https://img.shields.io/badge/Toolkit-ROL·CONTEXTO·TAREA·FORMATO-orange?style=flat-square" />
  <img src="https://img.shields.io/badge/Idioma-Español-green?style=flat-square" />
</p>

---

## ¿Qué es Player A?

Player A es una skill para Claude Code que convierte el
[Toolkit de IA de Servnet] en feedback accionable dentro
de tu flujo de desarrollo.

La mayoría del retrabajo en proyectos de software no viene del código — viene
de instrucciones mal estructuradas. Un prompt vago genera supuestos. Los
supuestos generan iteraciones. Las iteraciones consumen tiempo y tokens.

**Player A interrumpe ese ciclo.**

Cada vez que interactúas con Claude Code, Player A evalúa la calidad de tu
prompt en tiempo real, identifica qué falta, sugiere la versión estructurada
y registra tus patrones entre sesiones para que mejores con el tiempo.

---

## El framework: ROL · CONTEXTO · TAREA · FORMATO

Basado en el Toolkit de IA de Servnet México, Player A evalúa 4 ingredientes
en cada prompt:

| Ingrediente | Qué significa | Puntos |
|---|---|---|
| **ROL** | ¿Le dijiste a Claude qué perfil adoptar? | 0–2 |
| **CONTEXTO** | ¿Explicaste la situación sin asumir conocimiento previo? | 0–3 |
| **TAREA** | ¿Usaste un verbo concreto: genera, analiza, redacta, audita? | 0–3 |
| **FORMATO** | ¿Especificaste cómo quieres la respuesta? | 0–2 |

Un prompt con los 4 ingredientes llega al resultado en el primer intento.
Uno sin ellos genera 2–4 iteraciones adicionales.

---

## ¿Qué hace Player A en la práctica?

### 🔍 Prueba de escritorio del prompt
Cuando detecta un prompt incompleto, Player A lo evalúa automáticamente:
muestra qué se asumió, el score del prompt y una versión estructurada lista
para usar.

```
Prueba de escritorio del prompt

📝 Prompt recibido:
   "Necesito ver el gráfico de cambios de grupo de clientes"

📊 Score: 2/10  ████░░░░░░░░░░░░░░░░

   ❌ Rol      — no definido
   ❌ Contexto — módulo y tabla fuente sin especificar
   ❌ Tarea    — "ver" no es un verbo concreto
   ❌ Formato  — sin especificar

✅ Versión estructurada:
   "Actúa como desarrollador PHP/MySQL. En el módulo
    grupo_clientes de CAPA 8, genera un componente PHP
    con Chart.js que muestre cambios por mes en gráfica
    de línea."
```

### 📋 Plan de pruebas antes de escribir código
Antes de generar o modificar una función, Player A propone un plan de pruebas
y solicita aprobación. Esto evita el ciclo write → fail → fix.

### ✅ Reporte de resultados post-prueba
Después de ejecutar tests, muestra solo lo relevante: qué falló, dónde y por
qué — sin output crudo.

### 📈 Seguimiento de mejora entre sesiones
Player A guarda un historial local (`.player_a_memory.json`) que registra:
- Score de prompts por sesión
- Ingredientes que más se omiten
- Racha de mejora consecutiva

Al iniciar una nueva sesión, te muestra tus patrones y en qué mejorar.

### 🎯 Reconocimiento de las 5 fórmulas del toolkit
Cuando aplicas correctamente una de las 5 fórmulas del toolkit de Servnet
(El consultor, El revisor, El generador, El transformador, El coach), Player A
lo confirma y lo registra.

---

## Instalación

### Opción A — Desde GitHub (recomendado)

```bash
claude skill add --url https://raw.githubusercontent.com/jonatanhidalgo-SERVNET/Player-A-skill/skill/SKILL.md
```

### Opción B — Local

```bash
git clone https://github.com/jonatanhidalgo-SERVNET/Player-A-skill.git
cd Player-A-skill
claude skill add skill/
```

---

## Comandos disponibles

| Comando | Acción |
|---|---|
| `/player` | Lista de comandos disponibles |
| `/player plan` | Plan de pruebas de la función actual |
| `/player test` | Ejecuta pruebas y presenta reporte |
| `/player review` | Prueba de escritorio del último prompt |
| `/player score` | Score acumulado de la sesión |

---

## Memoria persistente

Player A crea automáticamente `.player_a_memory.json` en la raíz de tu
proyecto al iniciar la primera sesión. Este archivo es **personal** — no
se comparte entre el equipo.

Asegúrate de tenerlo en tu `.gitignore`:

```
.player_a_memory.json
```

---

## ¿Por qué Player A reduce tokens y retrabajo?

La reducción no ocurre por respuesta — ocurre por conversación completa.

Un prompt sin estructura genera 3–5 turnos de aclaración e iteración.
Un prompt con los 4 ingredientes llega al resultado en 1–2 turnos.

Player A no reemplaza tu criterio — lo amplifica desde el primer mensaje.

---

<p align="center">
  Desarrollado por el equipo de TI · <strong>Servnet México</strong> · 2026<br/>
  <a href="https://servnet.mx">servnet.mx</a>
</p>
