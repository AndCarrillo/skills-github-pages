---
title: "Proyecto: Calculadora JavaScript"
date: 2025-08-08
author: "Andrea"
categories: [proyectos]
tags: [javascript, html, css]
---

# Calculadora web

Primer proyecto en JavaScript para consolidar conceptos fundamentales.

## Objetivos

Practicar:
- JavaScript básico
- Manipulación del DOM
- CSS para diseño
- HTML semántico

## Tecnologías utilizadas

- **HTML** - Estructura
- **CSS** - Estilos y layout
- **JavaScript** - Lógica e interactividad

## Características implementadas

- Operaciones básicas (+, -, *, /)
- Interfaz responsive
- Manejo de errores básico
- Botón de reset

## Aprendizajes clave

- Event listeners
- Manipulación del DOM
- CSS Grid para layout
- Validación de entrada

## Código principal

```javascript
function calculate() {
    try {
        const result = eval(currentInput);
        display.textContent = result;
    } catch (error) {
        display.textContent = 'Error';
    }
}
```

## Mejoras futuras

- Historial de operaciones
- Funciones matemáticas avanzadas
- Soporte para teclado
- Themes

---

*Proyecto disponible en [GitHub](https://github.com/AndCarrillo)*
