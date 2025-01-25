## Ejemplo 1: Gestión de departamentos

**Crea una base de datos llamada 'departamentos' y una tabla con la información interna:** Recursos Humanos, Producción y Ventas.

- **Tabla:** `departamentos`
  - **Columnas:** `id_departamento` (PK), `nombre_departamento`.
- **Resultado esperado en la consola:**

>> CREATE TABLE departamento
(id_departamento INT AUTOINCREMENT PRIMARY KEY,
name_departamento VARCHAR (50));

INSERT INTO departamento(id_departamento, name_departamento)
VALUES (1, 'Recursos Humanos') 