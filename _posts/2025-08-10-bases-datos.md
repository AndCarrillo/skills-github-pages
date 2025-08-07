---
title: "Gestión de bases de datos relacionales"
date: 2025-08-10
author: "Andrea Carrillo"
categories: [bases-datos, teoria]
tags: [sql, bases-datos, modelado-datos, normalizacion]
---

# Fundamentos de gestión de bases de datos relacionales

Estudio teórico y práctico de los principios fundamentales de bases de datos relacionales aplicados en proyectos de Ingeniería en Sistemas.

## Marco teórico

### Modelo relacional

Propuesto por Edgar F. Codd en 1970, el modelo relacional se basa en:

- **Relaciones** - Representadas como tablas
- **Tuplas** - Filas de las tablas
- **Atributos** - Columnas de las tablas
- **Dominios** - Conjunto de valores posibles para un atributo

### Propiedades ACID

Las transacciones en bases de datos deben cumplir:

- **Atomicidad** - La transacción se ejecuta completamente o no se ejecuta
- **Consistencia** - La base de datos pasa de un estado válido a otro estado válido
- **Aislamiento** - Las transacciones concurrentes no interfieren entre sí
- **Durabilidad** - Los cambios confirmados persisten permanentemente

## Diseño de bases de datos

### Proceso de diseño

#### 1. Análisis de requerimientos

- Identificación de entidades
- Determinación de atributos
- Establecimiento de relaciones
- Definición de restricciones

#### 2. Diseño conceptual

- Modelo Entidad-Relación (ER)
- Diagramas ER extendidos
- Especificación de cardinalidades
- Identificación de claves primarias

#### 3. Diseño lógico

- Conversión del modelo ER a esquema relacional
- Definición de claves foráneas
- Especificación de restricciones de integridad
- Aplicación de reglas de normalización

#### 4. Diseño físico

- Selección de tipos de datos
- Definición de índices
- Particionamiento de tablas
- Consideraciones de rendimiento

## Normalización de datos

### Primera Forma Normal (1FN)

- Eliminación de grupos repetitivos
- Cada atributo contiene valores atómicos
- Identificación de clave primaria única

### Segunda Forma Normal (2FN)

- Cumple 1FN
- Eliminación de dependencias parciales
- Todos los atributos no clave dependen completamente de la clave primaria

### Tercera Forma Normal (3FN)

- Cumple 2FN
- Eliminación de dependencias transitivas
- Los atributos no clave no dependen de otros atributos no clave

### Forma Normal de Boyce-Codd (FNBC)

- Versión mejorada de 3FN
- Eliminación de dependencias funcionales problemáticas
- Cada determinante es clave candidata

## Lenguaje SQL

### Definición de datos (DDL)

```sql
-- Creación de tabla
CREATE TABLE estudiantes (
    id_estudiante INT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    carnet VARCHAR(20) UNIQUE,
    fecha_ingreso DATE
);

-- Modificación de estructura
ALTER TABLE estudiantes
ADD COLUMN email VARCHAR(100);

-- Eliminación de tabla
DROP TABLE estudiantes;
```

### Manipulación de datos (DML)

```sql
-- Inserción de datos
INSERT INTO estudiantes (id_estudiante, nombre, carnet, fecha_ingreso)
VALUES (1, 'Ana García', 'EST001', '2023-03-15');

-- Actualización de datos
UPDATE estudiantes
SET email = 'ana.garcia@universidad.edu'
WHERE id_estudiante = 1;

-- Eliminación de datos
DELETE FROM estudiantes
WHERE fecha_ingreso < '2020-01-01';
```

### Consultas de datos (DQL)

```sql
-- Consulta básica
SELECT nombre, carnet, fecha_ingreso
FROM estudiantes
WHERE fecha_ingreso >= '2023-01-01'
ORDER BY nombre;

-- Consulta con joins
SELECT e.nombre, m.nombre_materia, n.calificacion
FROM estudiantes e
INNER JOIN notas n ON e.id_estudiante = n.id_estudiante
INNER JOIN materias m ON n.id_materia = m.id_materia
WHERE n.calificacion >= 80;
```

## Sistemas de gestión de bases de datos

### SGBD estudiados

#### MySQL

- **Ventajas**: Open source, amplia comunidad, buena documentación
- **Uso académico**: Proyectos web, aplicaciones pequeñas a medianas
- **Características**: ACID compliance, replicación, particionamiento

#### PostgreSQL

- **Ventajas**: Cumplimiento estricto de estándares SQL, extensibilidad
- **Uso académico**: Proyectos complejos, análisis de datos
- **Características**: Soporte JSON, arrays, funciones personalizadas

#### SQL Server

- **Ventajas**: Integración con ecosistema Microsoft, herramientas avanzadas
- **Uso académico**: Proyectos empresariales, inteligencia de negocios
- **Características**: Analysis Services, Integration Services, Reporting Services

## Optimización de consultas

### Índices

- **Clustered Index**: Organiza físicamente los datos
- **Non-clustered Index**: Punteros a ubicaciones de datos
- **Composite Index**: Múltiples columnas
- **Unique Index**: Garantiza unicidad

### Análisis de planes de ejecución

- Identificación de operaciones costosas
- Detección de table scans innecesarios
- Optimización de joins
- Uso apropiado de índices

## Aplicaciones académicas

### Proyectos desarrollados

- **Sistema de gestión académica**: Control de estudiantes y materias
- **Inventario de laboratorio**: Gestión de equipos y préstamos
- **Biblioteca digital**: Catálogo y préstamos de recursos

### Herramientas utilizadas

- **MySQL Workbench**: Diseño y administración visual
- **phpMyAdmin**: Interfaz web para MySQL
- **SQL Server Management Studio**: Administración integral
- **DBeaver**: Cliente universal multiplataforma

---

_Fundamentos de bases de datos relacionales aplicados en Ingeniería en Sistemas de Información_
