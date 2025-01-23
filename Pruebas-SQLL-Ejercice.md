# Ejercicios prácticos de SQL con teoría y ejemplos de resultados

## Ejemplo 1: Gestión de departamentos

**Crea una base de datos llamada 'departamentos' y una tabla con la información interna:** Recursos Humanos, Producción y Ventas.

- **Tabla:** `departamentos`
  - **Columnas:** `id_departamento` (PK), `nombre_departamento`.
- **Resultado esperado en la consola:**

```plaintext
| id_departamento | nombre_departamento |
|-----------------|---------------------|
| 1               | Recursos Humanos    |
| 2               | Producción          |
| 3               | Ventas              |
```

---

## Ejemplo 2: Gestión de empleados

**Crea una tabla `empleados` relacionada con `departamentos`, donde `id_departamento` es una clave foránea.**

- **Tabla:** `empleados`
  - **Columnas:** `id_empleado` (PK), `nombre`, `puesto`, `salario`, `id_departamento` (FK).
- **Relación:** `empleados.id_departamento` → `departamentos.id_departamento`.
- **Resultado esperado en la consola:**

```plaintext
Tabla: empleados
| id_empleado | nombre     | puesto       | salario | id_departamento |
|-------------|------------|--------------|---------|-----------------|
| 1           | Juan       | Administrador| 2500    | 1               |
| 2           | María      | Operario     | 1500    | 2               |
| 3           | Pedro      | Vendedor     | 1800    | 3               |
```

---

## Ejemplo 3: Gestión de productos y ventas

**Crea dos tablas relacionadas: `productos` y `ventas`. Cada venta está asociada a un producto.**

- **Tabla 1:** `productos`
  - **Columnas:** `id_producto` (PK), `nombre_producto`, `precio`, `stock`.
- **Tabla 2:** `ventas`
  - **Columnas:** `id_venta` (PK), `id_producto` (FK), `cantidad`, `fecha_venta`.
- **Relación:** `ventas.id_producto` → `productos.id_producto`.
- **Resultado esperado en la consola:**

```plaintext
Tabla: productos
| id_producto | nombre_producto | precio | stock |
|-------------|-----------------|--------|-------|
| 1           | Lápiz          | 1.00   | 100   |
| 2           | Cuaderno       | 2.50   | 50    |
| 3           | Borrador       | 0.80   | 75    |

Tabla: ventas
| id_venta | id_producto | cantidad | fecha_venta |
|----------|-------------|----------|-------------|
| 1        | 1           | 10       | 2025-01-20  |
| 2        | 2           | 5        | 2025-01-21  |
| 3        | 3           | 2        | 2025-01-22  |
```

---

## Ejemplo 4: Gestión de estudiantes y cursos

**Crea tres tablas: `estudiantes`, `cursos` e `inscripciones`. Registra qué estudiantes están inscritos en qué cursos.**

- **Tabla 1:** `estudiantes`
  - **Columnas:** `id_estudiante` (PK), `nombre`, `apellido`, `edad`.
- **Tabla 2:** `cursos`
  - **Columnas:** `id_curso` (PK), `nombre_curso`, `duracion`.
- **Tabla 3:** `inscripciones`
  - **Columnas:** `id_inscripcion` (PK), `id_estudiante` (FK), `id_curso` (FK), `fecha_inscripcion`.
- **Relaciones:**
  - `inscripciones.id_estudiante` → `estudiantes.id_estudiante`.
  - `inscripciones.id_curso` → `cursos.id_curso`.
- **Resultado esperado en la consola:**

```plaintext
Tabla: estudiantes
| id_estudiante | nombre  | apellido | edad |
|---------------|---------|----------|------|
| 1             | Ana     | Pérez    | 20   |
| 2             | Luis    | Gómez    | 22   |
| 3             | Marta   | López    | 19   |

Tabla: cursos
| id_curso | nombre_curso    | duracion |
|----------|-----------------|----------|
| 1        | Matemáticas     | 3 meses  |
| 2        | Inglés          | 4 meses  |
| 3        | Programación    | 6 meses  |

Tabla: inscripciones
| id_inscripcion | id_estudiante | id_curso | fecha_inscripcion |
|----------------|---------------|----------|-------------------|
| 1              | 1             | 1        | 2025-01-10        |
| 2              | 2             | 2        | 2025-01-15        |
| 3              | 3             | 3        | 2025-01-18        |
```

---

## Ejemplo 5: Gestión de bibliotecas y préstamos

**Crea tres tablas: `libros`, `usuarios` y `prestamos`. Controla qué libros han sido prestados y a quién.**

- **Tabla 1:** `libros`
  - **Columnas:** `id_libro` (PK), `titulo`, `autor`, `anio_publicacion`, `stock`.
- **Tabla 2:** `usuarios`
  - **Columnas:** `id_usuario` (PK), `nombre`, `apellido`, `telefono`.
- **Tabla 3:** `prestamos`
  - **Columnas:** `id_prestamo` (PK), `id_libro` (FK), `id_usuario` (FK), `fecha_prestamo`, `fecha_devolucion`.
- **Relaciones:**
  - `prestamos.id_libro` → `libros.id_libro`.
  - `prestamos.id_usuario` → `usuarios.id_usuario`.
- **Resultado esperado en la consola:**

```plaintext
Tabla: libros
| id_libro | titulo                | autor            | anio_publicacion | stock |
|----------|-----------------------|------------------|------------------|-------|
| 1        | Cien Años de Soledad | Gabriel García   | 1967             | 5     |
| 2        | Don Quijote          | Miguel de Cervantes | 1605          | 3     |
| 3        | El Principito        | Antoine de Saint | 1943             | 7     |

Tabla: usuarios
| id_usuario | nombre  | apellido | telefono    |
|------------|---------|----------|-------------|
| 1          | Laura   | Castillo | 111222333   |
| 2          | Mario   | López    | 444555666   |
| 3          | Elena   | Torres   | 777888999   |

Tabla: prestamos
| id_prestamo | id_libro | id_usuario | fecha_prestamo | fecha_devolucion |
|-------------|----------|------------|----------------|------------------|
| 1           | 1        | 2          | 2025-01-05     | 2025-01-15       |
| 2           | 3        | 1          | 2025-01-10     | 2025-01-20       |
| 3           | 2        | 3          | 2025-01-15     | 2025-01-25       |
```
