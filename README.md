# HP-ProBook-440-G9-eGPU-Desktop-Mod
> **Status:** Functional / In Optimization

## 1. La Tesis del Proyecto
Este proyecto consiste en la transformación de un laptop empresarial (HP ProBook 440 G9) en una estación de trabajo de escritorio compacta, integrando una eGPU a través de la interfaz NVMe para superar las limitaciones gráficas de fábrica.

## 2. Hardware: Especificaciones "Frankenstein"
| Componente | Detalle |
| :--- | :--- |
| **CPU** | Intel Core i5-1235u (10 Cores, 12 Threads) |
| **RAM** | 16GB DDR4 3200MHz |
| **GPU Externa** | GEFORCE RTX 5050 |
| **Interfaz** | NVMe M.2 a PCIe ADT-Link |
| **Fuente de Poder** | DeepCool DA500 |

## 3. Desafíos Técnicos y Soluciones
* **Gestión de Energía:** Se validó que la PSU DeepCool DA500 entrega el amperaje necesario en el riel de 12V para la GPU. La salida americana de la fuente de poder fue adaptada con un enchufe europeo para las tomas de corriente en Chile. 500W fueron suficientes para la RTX 5050.
* **Bypass de Chasis:** Implementé una configuración de "OS Boot over USB 3.2 Gen 2 (Windows To Go)" para priorizar el ancho de banda PCIe hacia la eGPU. Para esto, utilicé un adaptador de carcasa NVME a USB el cual se conectó a un puerto USB 3.2 gen 2. Sacrificando velocidad de almacenamiento por la implementación de una eGPU.
* **Estabilidad del Sistema:** Ajuste de perfiles de energía y eliminación de Power Limit Throttling mediante ThrottleStop para maximizar el throughput de datos hacia la GPU externa.

## 4. Próximos Pasos (Roadmap)
- [ ] Implementar un sistema de refrigeración externa dedicado, actualmente un ventilador de notebook ha sido satisfactorio.
- [ ] Optimización de drivers para evitar el cuello de botella (bottleneck) de la CPU. Esto ha sido realizado con ThrottleStop.
- [ ] Experimentación con LLMs locales (IA) aprovechando la VRAM de la eGPU. Aún no se realiza este paso.
