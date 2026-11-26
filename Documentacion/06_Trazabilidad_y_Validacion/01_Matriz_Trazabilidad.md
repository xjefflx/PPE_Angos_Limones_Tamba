# 01. Matriz de Trazabilidad
## Sistema de Gestión para Refugio de Animales de Compañía (SG-RAC)

### 1. Objetivo
Relacionar cada requerimiento del SRS con su fuente, caso de uso, historia de usuario, criterio de aceptación y prueba propuesta. La matriz facilita comprobar que los requerimientos estén contemplados en el modelado y que puedan validarse.

### 2. Matriz

| ID | Fuente | Caso de uso | Historia | Criterio / prueba propuesta | Estado de implementación |
|---|---|---|---|---|---|
| RF-01 | Administrador | CU-01 | HU-01 | Ingresar credenciales válidas e inválidas y comprobar el resultado | Por verificar |
| RF-02 | Administrador | CU-02 | HU-02 | Registrar ingreso completo y comprobar persistencia; probar campos vacíos | Por verificar |
| RF-03 | Administrador | CU-03 | HU-03 | Crear y consultar ficha con microchip/placa, especie, raza, edad y estado | Por verificar |
| RF-04 | Veterinario / Administrador | CU-04 | HU-04 | Registrar vacunas, cirugías, desparasitaciones y medicación; consultar historial | Por verificar |
| RF-05 | Administrador | CU-05 | HU-05 | Registrar datos personales y socioambientales; validar campos obligatorios | Por verificar |
| RF-06 | Administrador | CU-06 | HU-06 | Registrar adopción temporal y definitiva; comprobar titularidad y fechas | Por verificar |
| RF-07 | Administrador | CU-07 | HU-07 | Generar PDF y comprobar datos del animal, adoptante y firmas | Por verificar |
| RF-08 | Administrador | CU-08 | HU-08 | Registrar visita, fotografía y evaluación; consultar bitácora | Por verificar |
| RF-09 | Administrador | CU-09 | HU-09 | Intentar revocatoria con y sin justificación objetiva | Por verificar |
| RF-10 | Administrador | CU-10 | HU-10 | Registrar las cinco categorías y validar los datos específicos de cada una | Por verificar |
| RNF-01 | Administrador / TI | Restricción transversal | — | Ejecutar la aplicación sin conexión a Internet | Por verificar |
| RNF-02 | Soporte TI | CU-11 | HU-11 | Crear respaldo en USB y comprobar que el archivo pueda recuperarse | Por verificar |
| RNF-03 | Administrador / TI | CU-01 | HU-01 | Verificar que las credenciales estén protegidas según el mecanismo definido en el diseño técnico | Por verificar |
| RD-01 | Reglamento RAC | CU-06 | HU-06 | Intentar asignar titular distinto al solicitante y verificar que se impida | Por verificar |
| RD-02 | Reglamento RAC | CU-04 / CU-06 | HU-04 / HU-06 | Intentar adopción definitiva con tratamiento crítico sin alta y verificar bloqueo | Por verificar |

### 3. Cobertura
- Requerimientos funcionales: RF-01 a RF-10.
- Requerimientos no funcionales: RNF-01 a RNF-03.
- Requerimientos de dominio: RD-01 y RD-02.
- Total trazado: 15 requerimientos.

### 4. Criterio de cierre
Un requerimiento podrá marcarse como implementado y validado cuando exista evidencia de ejecución de su prueba, el resultado sea satisfactorio y el interesado correspondiente haya revisado el comportamiento. Hasta disponer de esa evidencia, el estado se mantiene como **Por verificar**.

### 5. Observaciones
La matriz vincula el catálogo del SRS con los artefactos PPE07 y las pruebas propuestas para PPE08. Los resultados reales, defectos y aprobaciones deben completarse después de ejecutar las pruebas con la aplicación y revisar el sistema con el Administrador.
