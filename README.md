# Sistema de Gestión para Refugio de Animales de Compañía (SG-RAC)

Aplicación de escritorio en C# (Windows Forms) desarrollada para gestionar los procesos internos del Refugio de Animales de Compañía (RAC).

## Integrantes
* Jeff Alejandro Limones Chachapoya
* [Nombre] Angos
* [Nombre] Urrea

## Problemática
El refugio realiza el control de rescates, historiales médicos, solicitudes de adopción, seguimientos y donaciones de forma manual. Esto dificulta llevar un seguimiento ordenado de los animales entregados en adopción temporal o definitiva, verificar su estado de salud y controlar el inventario de insumos o aportes recibidos.

## Solución
Implementar una aplicación de escritorio local (monousuario) administrada por el encargado del refugio, que permita:
* Registrar los animales rescatados junto con los datos de las personas involucradas y su estado inicial.
* Mantener un historial médico básico por cada animal (identificación por chip o collar, edad y revisiones veterinarias).
* Gestionar solicitudes de adopción temporal o definitiva, validando los datos del solicitante y generando un comprobante de registro.
* Llevar un seguimiento de los animales adoptados para verificar su cuidado y registrar retiros en caso de incumplimiento.
* Registrar los donativos recibidos (comida, dinero en efectivo o transferencia, juguetes, medicinas y ayuda veterinaria).

## Tecnologías
* **Lenguaje:** C#
* **Interfaz:** Windows Forms (.NET)
* **Base de datos:** Local (SQL Server / SQLite)
* **Control de versiones:** Git y GitHub

## Estructura del repositorio
```text
PPE_Limones_Angos_Urrea/
├── SG_RAC/
├── Documentacion/
│   ├── 01_Gestion_y_Alcance/
│   │   ├── 01_Vision_y_Alcance.md
│   │   └── 02_Matriz_Interesados.md
│   └── 02_Adquisicion_e_Interesados/
│       └── 01_Adquisicion_Requerimientos.md
├── .gitignore
└── README.md
