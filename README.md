# 🧠 STM32-Laberinto

**Proyecto de Sistemas Digitales**  
Universidad Nacional de Mar del Plata – Área Electrónica y Computación

## 👥 Autores

Lucas Starita, Franco Rabini, Santiago Benjamin Loza, Santiago Mosler, Gian Dylan Pipoli.

## 📝 Descripción

Este proyecto consiste en el desarrollo de un robot autónomo que debe escapar de un laberinto en el menor tiempo posible utilizando un microcontrolador **STM32F407VGT6**.

El sistema fue implementado en lenguaje C utilizando **STM32CubeIDE**, e involucra control de motores, sensores infrarrojos, detección de celdas y un algoritmo de navegación. El objetivo es aplicar técnicas de diseño digital, manejo de periféricos (ADC, GPIO, PWM, DMA, UART) y lógica de control distribuida.

---

## 🎯 Objetivos del proyecto

- Navegar un laberinto de forma autónoma, evitando colisiones.
- Mantener trayectoria centrada entre paredes laterales.
- Detectar y realizar giros al encontrar obstáculos.
- Reconocer celdas atravesadas y transmitirlas por Bluetooth.
- Implementar un algoritmo de búsqueda (como Flood Fill) para optimizar el recorrido.

---

## 🧩 Arquitectura del sistema

El sistema se divide en los siguientes módulos:

### 🔸 Subsistema 1 – Desplazamiento en línea recta
Corrige la trayectoria utilizando sensores laterales y un control proporcional.

### 🔸 Subsistema 2 – Giros (90° / 180°)
Realiza maniobras mediante temporización al detectar paredes frontales.

### 🔸 Subsistema 3 – Detección de cuadrícula
Detecta líneas en el piso y cuenta las celdas atravesadas. Se transmite por UART/Bluetooth.

### 🔸 Subsistema 4 – Control general y navegación
Implementa la lógica de decisión y planificación de ruta en tiempo real.

---

## 🛠️ Hardware utilizado

- **Placa**: STM32F407G-DISC1  
- **Sensores**:
  - IR Frontal Digital (detección de obstáculos)
  - IR Laterales Analógicos (medición de distancia)
  - Sensor de línea inferior Digital (cuadrícula)
- **Actuadores**:
  - 2 motores DC controlados por driver (PWM + GPIO)
- **Comunicación**:
  - Módulo Bluetooth (UART)

