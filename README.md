# Arduino Bartender - Proyecto de Bar Automatizado 🍸
###### Adaptation existing code of Arduino based bartender to MARLIN code.

![alt text](https://i.ytimg.com/vi/hJIkJ9x0-JQ/maxresdefault.jpg)

Este proyecto consiste en un prototipo funcional de un bar automatizado capaz de realizar mezclas de bebidas de forma autónoma. El sistema utiliza una estructura de raíles y un carrito motorizado que se desplaza para recolectar diferentes ingredientes (bebidas alcohólicas y refrescos) según la configuración deseada.

Desarrollado como proyecto para la asignatura de **Arquitecturas Específicas y Empotradas** en la **Universidad de León**.

## 🚀 Características
* **Movimiento en ejes X/Y:** Sistema de raíles con motores paso a paso para posicionamiento preciso del vaso.
* **Dispensado mixto:** * 3 Dispensadores mecánicos para bebidas alcohólicas.
    * 2 Bombas impulsoras para mezclas (con/sin gas).
* **Electrónica Robusta:** Migración de Arduino Uno a **ESP32** (o Arduino Mega con RAMPS 1.4 según la fase del proyecto) para un control más eficiente.
* **Interfaz de Control:** Comandos vía puerto serie (con soporte futuro para App móvil vía Bluetooth).

## 🛠️ Hardware Utilizado
| Componente | Descripción |
| :--- | :--- |
| **Controlador** | Arduino Mega 2560 (Base para RAMPS) |
| **Shield** | RAMPS 1.4 |
| **Drivers** | A4988 (para motores paso a paso) |
| **Motores** | 3x Nema 17 |
| **Bombas** | 2x Bombas de líquidos 12V |
| **Alimentación** | Fuente de alimentación 12V DC |
| **Estructura** | Madera y piezas impresas en 3D (PLA) |

## 💻 Software y Librerías
* **Framework:** Arduino IDE.
* **Firmware:** Adaptación de **Marlin** (optimizado para movimientos precisos de impresoras 3D).
* **Librerías principales:** * `AF_Stepper.h` (versiones iniciales).
    * Gestión de G-code nativa de Marlin.
* **Diseño 3D:** Repetier / Slic3r para la laminación de piezas.

## 📂 Estructura del Repositorio
* `/src`: Código fuente del firmware (basado en Marlin).
* `/3D_Models`: Archivos STL de las piezas impresas (Base, soporte motor, tensor, etc.).
* `/Schematics`: Diagramas de conexión eléctrica.
* `/Docs`: Memoria técnica detallada del proyecto.

## 🔧 Instalación y Configuración
1.  **Carga del Firmware:** Abre el proyecto en Arduino IDE y carga el código en tu placa.
2.  **Calibración:** Antes de servir, es necesario calibrar los finales de carrera (Home) para establecer las coordenadas `(0,0)`.
3.  **Conexión:** Conecta el sistema vía USB a un PC.
4.  **Operación:** Envía los comandos de movimiento y activación de bombas a través del monitor serie.

## 🚧 Problemas Conocidos y Soluciones
* **Sobrecalentamiento:** Se recomienda el uso de disipadores activos (ventiladores) en los drivers A4988 para evitar la pérdida de pasos.
* **Polaridad:** ¡Cuidado! Invertir la polaridad en la RAMPS puede dañar permanentemente la electrónica.
* **Fricción:** Se recomienda aplicar vaselina en los raíles impresos para movimientos más fluidos.

## 📈 Próximas Mejoras
- [ ] Implementación completa de conectividad Bluetooth (HC-05).
- [ ] Desarrollo de una App Android dedicada.
- [ ] Interfaz gráfica en pantalla LCD.
- [ ] Dispensador de hielos automático.

## 👥 Autores
* Andrés García Álvarez
* Pablo González de la Iglesia
* Eduardo Juárez Robles
* Santiago Peláez Peláez
