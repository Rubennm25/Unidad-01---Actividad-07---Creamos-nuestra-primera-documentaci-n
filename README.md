# Unidad-01---Actividad-07---Creamos-nuestra-primera-documentaci-n
# RPG UNREAL ENGINE 5


Este proyecto consiste en el desarrollo de un videojuego de acción y rol (ARPG) en tercera persona, centrado en el combate táctico, la gestión de inventario y el multijugador cooperativo.

##  Descripción del Proyecto
El software permite al jugador controlar un avatar en un entorno 3D, gestionando estadísticas, inventario y combate en tiempo real. [cite_start]El desarrollo sigue la **Metodología Ágil (Scrum)** para garantizar iteraciones rápidas y funcionales[cite: 27].

## Requisitos Funcionales (RF)
Comportamientos específicos que el sistema ejecuta en respuesta al usuario:

* **RF-01 Sistema de Combate:** Control de avatar en 3D con acciones complejas (desplazamiento, salto, esquiva, ataque). [cite_start]Cálculo de colisiones y daño en tiempo real basado en estadísticas[cite: 5, 6].
* **RF-02 Gestión de Inventario:** Base de datos para ítems con acciones de almacenar, equipar y soltar. [cite_start]Limitado por nivel de jugador y estadística de "carga máxima"[cite: 7, 8].
* [cite_start]**RF-03 Multijugador Cooperativo:** Módulo de red para hasta **5 usuarios simultáneos**, sincronizando posición, animaciones y estados[cite: 9, 10].
* [cite_start]**RF-04 Persistencia de Datos:** Serialización para autoguardado local y en la nube, permitiendo retomar la partida exactamente donde se dejó[cite: 11, 12].
* **RF-05 Inteligencia Artificial:** Control de PNJs y enemigos. [cite_start]La dificultad es intrínseca y no escala automáticamente con el nivel del jugador[cite: 13, 14].

---

##  Requisitos No Funcionales (RNF) - Métricas de Calidad
Restricciones técnicas y estándares de rendimiento cuantificables:

### 1. Rendimiento y Eficiencia Gráfica
* [cite_start]**Frame Rate:** El sistema debe mantener **60 FPS estables** (caídas <5%) en hardware equivalente a **NVIDIA RTX 3060 / 16GB RAM** a 1080p[cite: 17].
* **Tiempos de Carga:** La carga inicial del nivel no superará los **15 segundos** en almacenamiento SSD NVMe (vel. lectura >3500 MB/s).

### 2. Usabilidad (UI/UX)
* [cite_start]**Legibilidad:** Textos de menús y HUD deben cumplir un ratio de contraste mínimo de **4.5:1** (WCAG AA)[cite: 18].
* **Interacción:** Las acciones críticas (Salir, Guardar) no deben requerir más de **3 clics** desde la pantalla principal.

### 3. Fiabilidad de Red (Multijugador)
* [cite_start]**Latencia:** En conexiones de fibra óptica (100 Mbps simétricos), la latencia (ping) no debe superar los **50 ms**[cite: 19].
* **Sincronización:** El desfase de posición entre clientes no superará los **0.1 segundos** respecto al servidor.

### 4. Portabilidad y Compatibilidad
* [cite_start]**S.O.:** Ejecución estable (zero-crash) en **Windows 10 (Build 19041+)** y **Windows 11**[cite: 20].
* **Input:** Detección automática de mandos (XInput/DirectInput) en menos de **2 segundos** tras conexión.

### 5. Escalabilidad
* [cite_start]**Arquitectura:** Soporte para carga de DLCs mediante archivos `.pak` externos sin recompilar el `.exe`[cite: 21].
* **Base de Datos:** Capacidad para añadir +50 tipos de ítems sin degradar las consultas de inventario por encima de **200 ms**.

---

## Historias de Usuario Principales

### HU-01: Gestión de Peso y Movilidad
> [cite_start]"Como jugador táctico, quiero visualizar el impacto del peso en mi movilidad antes de recoger un objeto..."[cite: 29, 30].

* [cite_start]**Criterio A:** HUD muestra "Peso actual + Objeto / Peso Máximo" al apuntar al ítem[cite: 32].
* [cite_start]**Criterio B:** Superar el límite activa automáticamente animación de movimiento lento[cite: 33].
* [cite_start]**Criterio C:** Botón de "Soltar rápido" disponible para recuperar movilidad[cite: 34].

### HU-02: Conectividad Cooperativa (Hot-Join)
> [cite_start]"Como jugador invitado, quiero unirme a una partida en curso sin obligar al anfitrión a reiniciar..."[cite: 36, 37].

* [cite_start]**Criterio A:** Conexión en segundo plano sin pausar el juego del host[cite: 39].
* [cite_start]**Criterio B:** Spawn cerca del líder del grupo, no en el inicio del nivel[cite: 40].

---

##  Stack Tecnológico
* **Motor:** Unreal Engine 5
* **Lenguaje:** C++ / Blueprints
* **Plataformas:** PC (Windows)
