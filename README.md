# HP-ProBook-440-G9-eGPU-Desktop-Mod
> **Status:** Functional / In Optimization

## 1. La Tesis del Proyecto
Este proyecto consiste en la transformación de un laptop empresarial (HP ProBook 440 G9) en una estación de trabajo de escritorio compacta, integrando una eGPU a través de la interfaz NVMe para superar las limitaciones gráficas de fábrica.

## 2. Hardware: Especificaciones "Frankenstein"
| Componente | Detalle |
| :--- | :--- |
| **CPU** | Intel Core i5-1235u (10 Cores, 12 Threads) |
| **RAM** | 16GB DDR4 3200MHz |
| **GPU Externa** | RTX 5050 |
| **Interfaz** | NVMe M.2 a PCIe ADT-Link |
| **Fuente de Poder** | DeepCool DA500 |

## 3. Desafíos Técnicos y Soluciones
* **Gestión de Energía:** La salida americana de la fuente de poder fue adaptada con un enchufe europeo para las tomas de corriente en Chile. 500W fueron suficientes para la RTX 5050.
* **Bypass de Chasis:** Se extrajo el almacenamiento NVME, el cual (utilizando un adaptador de carcasa NVME a USB) se conectó a un puerto USB 3.2 gen 2. Sacrificando velocidad de almacenamiento por la implementación de una eGPU.
* **Estabilidad del Sistema:** Una serie de ajustes debieron de ser utilizados primero para instalar windows desde un disco NVME conectado por USB. Los otros ajustes corresponden a cambios en la BIOS como opciones de energía para priorizar rendimiento y el uso de aplicaciones como ThrottleStop para aumentar también el rendimiento del notebook y no generar cuellos de botella entre CPU y eGPU.

## 4. Próximos Pasos (Roadmap)
- [ ] Implementar un sistema de refrigeración externa dedicado, actualmente un ventilidar de notebook ha sido satisfactorio.
- [ ] Optimización de drivers para evitar el cuello de botella (bottleneck) de la CPU. Esto ha sido realizado con ThrottleStop
- [ ] Experimentación con LLMs locales (IA) aprovechando la VRAM de la eGPU. Aún no se realiza este paso
