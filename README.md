# 🎭 Five Nights at Freddy's — Recreación Web

> Recreación completa de **Five Nights at Freddy's 1** jugable directamente en el navegador.  
> Sin instalaciones. Sin dependencias. Un solo archivo `.html`.

![FNAF Banner](https://img.shields.io/badge/FNAF-Recreaci%C3%B3n-orange?style=for-the-badge)
![HTML](https://img.shields.io/badge/HTML-5-red?style=for-the-badge&logo=html5)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-yellow?style=for-the-badge&logo=javascript)
![License](https://img.shields.io/badge/Fan%20Game-No%20Comercial-blue?style=for-the-badge)

---

## 🎮 Demo

Juega aquí → **[GitHub Pages Link]** *(actívalo en Settings → Pages)*

---

## 📋 Características implementadas

### Mecánicas principales
- **6 noches** seleccionables con dificultad progresiva
- **Sistema de energía** con drain dinámico según acciones activas
- **Puertas** izquierda y derecha bloqueables (toggle)
- **Luces** de pasillo para detectar amenazas (mantener presionado)
- **Sistema de cámaras** con 11 ubicaciones navegables

### IA de animatrónicos
| Animatrónico | Comportamiento | Camino de ataque |
|---|---|---|
| 🐻 Freddy | Pasivo, se activa sin energía | Escenario → Pasillo D → Oficina |
| 🐰 Bonnie | Agresivo desde N1 | Escenario → Backstage → Pasillo I → Oficina |
| 🐥 Chica | Agresiva desde N1 | Escenario → Sala Fiestas → Pasillo D → Oficina |
| 🦊 Foxy | Timer independiente, corre al pasillo | Bahía → Pasillo I → Oficina |

### Easter Eggs
- 👻 **Golden Freddy** — Alucinación a las 2 AM (7% de probabilidad)
- 🖼️ **Poster Raro** — Visita la Cam 7 por séptima vez
- 💬 **"IT'S ME"** — Aparece en Noche 6 a las 5 AM
- 📞 **Llamada telefónica** — Mensaje único al inicio de cada noche
- ⚡ **Corte de energía** — Freddy ataca al quedarte sin poder

---

## 🕹️ Controles

| Tecla | Acción |
|---|---|
| `A` / `←` | Puerta izquierda (toggle) |
| `D` / `→` | Puerta derecha (toggle) |
| `C` | Abrir/cerrar cámaras |
| `Q` *(mantener)* | Luz pasillo izquierdo |
| `E` *(mantener)* | Luz pasillo derecho |
| *Click tablet* | Abrir cámaras |

---

## ⚙️ Sistema de energía

La energía drena constantemente. Cada acción aumenta el consumo:

```
Base:        -0.028 / tick
Cámaras:     -0.025 / tick adicional
Cada puerta: -0.018 / tick adicional
Cada luz:    -0.010 / tick adicional
```

> ⚠️ A 0% de energía las puertas se abren y Freddy probablemente ataca.

---

## 🧠 Niveles de IA por noche

Los valores replicán exactamente la tabla del juego original:

| Noche | Freddy | Bonnie | Chica | Foxy |
|---|---|---|---|---|
| 1 | 0 | 3 | 3 | 1 |
| 2 | 1 | 4 | 4 | 2 |
| 3 | 2 | 5 | 6 | 3 |
| 4 | 3 | 7 | 8 | 5 |
| 5 | 4 | 9 | 9 | 6 |
| 6 ★ | 10 | 10 | 10 | 10 |

---

## 🚀 Instalación y uso

### Opción 1 — Uso directo
```bash
# Clona el repositorio
git clone https://github.com/TU_USUARIO/fnaf-recreacion.git

# Abre el archivo en tu navegador
open index.html
```

### Opción 2 — GitHub Pages
1. Ve a **Settings → Pages**
2. En *Source* selecciona `main` y carpeta `/ (root)`
3. Guarda y espera ~2 minutos
4. Disponible en `https://TU_USUARIO.github.io/fnaf-recreacion`

---

## 🗂️ Estructura del proyecto

```
fnaf-recreacion/
└── index.html      # Juego completo (HTML + CSS + JS en un solo archivo)
```

---

## 🔧 Arquitectura técnica

- **Motor**: JavaScript vanilla con loop de `setInterval` a 500ms
- **Estado**: Objeto global `G` como única fuente de verdad
- **IA**: Probabilidad de movimiento = `aiLevel / 20` por tick
- **Tiempo**: 16 ticks = 1 hora de juego (~8 segundos reales)
- **Render**: Dirigido por estado, sin polling redundante
- **Sin dependencias externas**: Funciona offline

---

## ⚖️ Aviso legal

Este proyecto es un **fan game no comercial** creado con fines educativos y de entretenimiento.  
Five Nights at Freddy's es propiedad de **Scott Cawthon / Steel Wool Studios**.  
Este repositorio no tiene afiliación oficial con los creadores originales.

---

## 🤖 Créditos

Recreado con [Claude](https://claude.ai) — Anthropic  
Basado en *Five Nights at Freddy's* de Scott Cawthon (2014)
