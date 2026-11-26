# 02. Resultados de Validación
## Sistema de Gestión para Refugio de Animales de Compañía (SG-RAC)

### 1. Objetivo
Definir el checklist para validar que el SG-RAC satisfaga los requerimientos funcionales, no funcionales y de dominio establecidos en el SRS.

### 2. Alcance de la validación
Se consideran los 16 requerimientos del catálogo: RF-01 a RF-10, RNF-01 a RNF-04 y RD-01 a RD-02. La validación debe realizarse sobre una versión ejecutable del sistema y con participación del Administrador del refugio.

### 3. Checklist de validación

| ID | Comprobación | Resultado | Observaciones / evidencia |
|---|---|---|---|
| RF-01 | El Administrador puede autenticarse y se rechazan credenciales incorrectas | Pendiente | Registrar capturas o evidencia de pruebas |
| RF-02 | Se registra fecha, lugar, rescatista y condición inicial del animal | Pendiente | Registrar identificador del animal de prueba |
| RF-03 | Se crea y consulta la ficha de identificación | Pendiente | Comprobar campos de identificación |
| RF-04 | Se registra y consulta el historial médico | Pendiente | Utilizar datos clínicos de prueba |
| RF-05 | Se registran datos personales y socioambientales del solicitante | Pendiente | Comprobar validación de campos |
| RF-06 | Se procesa adopción temporal y definitiva y se asigna titular | Pendiente | Probar ambas modalidades |
| RF-07 | Se genera el acta PDF con datos y firmas | Pendiente | Guardar PDF generado |
| RF-08 | Se registran y consultan seguimientos post-adopción | Pendiente | Adjuntar evidencia de bitácora |
| RF-09 | Se registra revocatoria con causa objetiva y reintegro | Pendiente | Probar escenario válido y sin justificación |
| RF-10 | Se registran donaciones clasificadas | Pendiente | Probar categorías disponibles |
| RNF-01 | La aplicación opera localmente sin Internet obligatorio | Pendiente | Ejecutar con conexión desactivada |
| RNF-02 | El PDF se genera en menos de 3 segundos | Pendiente | Registrar tiempo medido |
| RNF-03 | Se realiza respaldo manual en USB | Pendiente | Comprobar existencia e integridad de copia |
| RNF-04 | Las credenciales se protegen con hashing seguro | Pendiente | Revisar implementación y almacenamiento |
| RD-01 | El titular legal coincide con el solicitante titular | Pendiente | Intentar registrar titular diferente |
| RD-02 | Se bloquea adopción definitiva de animal crítico sin alta médica | Pendiente | Ejecutar escenario de restricción |

### 4. Registro de incidencias

| ID de incidencia | Requerimiento relacionado | Descripción | Severidad | Acción correctiva | Estado |
|---|---|---|---|---|---|
| INC-01 | Por asignar | Completar durante la ejecución de pruebas | Por determinar | Por definir | No registrada |

Si no se detectan incidencias durante la ejecución, reemplazar esta fila por una declaración de que no se encontraron defectos, indicando la versión y fecha de prueba.

### 5. Criterios de aceptación
- **Aprobado:** la prueba se ejecutó y el resultado cumple el criterio.
- **Rechazado:** la prueba se ejecutó y el resultado no cumple el criterio.
- **Pendiente:** no se ha ejecutado o no existe evidencia suficiente.
- **No aplica:** solo puede utilizarse con justificación documentada.

### 6. Participantes y aprobación

| Participante | Rol | Resultado de revisión | Fecha | Firma / evidencia |
|---|---|---|---|---|
| Administrador del refugio | Interesado principal | Pendiente | Por definir | Por registrar |
| Equipo de desarrollo | Responsable técnico | Pendiente | Por definir | Por registrar |

### 7. Conclusión
Este documento establece las comprobaciones necesarias para validar el SG-RAC. No se declara que los requerimientos estén aprobados ni implementados, porque esa conclusión requiere ejecutar las pruebas y conservar evidencia. Una vez completado el checklist, deben registrarse las correcciones y la aprobación de los interesados.
