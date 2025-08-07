---
title: "Mi primer proyecto: Calculadora en JavaScript"
date: 2025-08-08
author: "Andrea"
categories: [proyectos, javascript]
tags: [javascript, html, css, principiante]
---

# 🧮 Creando mi primera calculadora web

¡Hoy quiero compartir mi primer proyecto "serio" en JavaScript! Una calculadora web que, aunque simple, me ayudó a consolidar conceptos fundamentales.

## 🎯 ¿Por qué una calculadora?

Elegí este proyecto porque me permite practicar:

- **JavaScript básico**: Variables, funciones, eventos
- **DOM manipulation**: Seleccionar y modificar elementos
- **CSS**: Hacer que se vea decente
- **HTML**: Estructura semántica

## 🛠️ Lo que aprendí

### 1. Event Listeners

```javascript
// Escuchar clicks en los botones
document.querySelectorAll(".number").forEach((button) => {
  button.addEventListener("click", () => {
    appendNumber(button.textContent);
  });
});
```

### 2. Manejo del DOM

```javascript
// Actualizar la pantalla
function updateDisplay() {
  display.textContent = currentInput || "0";
}
```

### 3. Lógica de operaciones

```javascript
function calculate() {
  try {
    const result = eval(currentInput);
    currentInput = result.toString();
    updateDisplay();
  } catch (error) {
    currentInput = "Error";
    updateDisplay();
  }
}
```

## 🎨 El diseño

Usé CSS Grid para organizar los botones:

```css
.calculator {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  max-width: 300px;
  margin: 0 auto;
}
```

## 🚧 Desafíos que enfrenté

1. **Manejo de decimales**: Evitar múltiples puntos
2. **División por cero**: Mostrar error apropiado
3. **Botón AC (Clear)**: Resetear todo correctamente
4. **Responsive design**: Que se vea bien en móvil

## 🎉 Resultados

- ✅ Operaciones básicas funcionando
- ✅ Interfaz limpia y usable
- ✅ Manejo básico de errores
- ✅ Responsive en móviles

## 📚 Próximas mejoras

Para la versión 2.0 quiero agregar:

- Historial de operaciones
- Más funciones matemáticas (raíz, potencia)
- Themes de colores
- Keyboard support
- Animaciones en CSS

## 🔗 Ver el proyecto

El código está disponible en mi [GitHub](https://github.com/AndCarrillo) y puedes probarlo [aquí](#).

---

_Este proyecto me demostró que con lo básico se pueden crear cosas útiles. ¡El siguiente paso es una to-do list!_

**¿Cuál fue tu primer proyecto de programación?** Me encantaría conocer tu experiencia.
